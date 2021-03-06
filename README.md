# 如何定义题目的难度

## 前置条件 运行Before.py
1. DownLoad&Unzip.py，把代码文件下载下来，保存在data文件夹
2. DataCollecting，把收集到的所有Case对象序列化，保存在AllCaseObjs文件
3. SaveTrainingData，把对训练集pca后对结果，包括综合评分res，降维后对矩阵U，训练好对模型pcaModel序列化，保存在TrainingResult文件

## 说明
- averageTime的单位是分钟
- case对象转换成list，顺序为averageDeduction, averageLineNum, averageTime, averageUploadNum, cheatRatio, incompleteRatio
- utils.py中是工具函数
- 收集数据的函数在DataCollecting.py
- do_pca返回PcaModal，是训练好的模型
    - transform方法可以转换新数据
        - 返回降维后的矩阵和综合评分的list
        - 可传入List<Case>
        - 可传入6列矩阵X与case_id_list
    - 训练集返回的内容已序列化保存在文件中
    - 想要使用训练好的模型，调用SaveTrainingResult.py中的deserialize_training_result函数
        
- 题目的类型有
    - 字符串
    - 数组
    - 树结构
    - 图结构
    - 排序算法
    - 数字操作
    - 查找算法
    - 线性表
    
- 输入一道题，输出难度值、绝对难度、类型、相对难度
    - 注意要包装成list    
    
dict 键：类型 值：两个
overall 两个变量
