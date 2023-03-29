# 数据简单操作
    
    import torch
    # 张量 tensor  一个数值组成的数组。
    x = torch.arange(12)
    x.shape
    x.numel()  # 元素个数
    x.reshape(3,4)   $ 3行4列
    x = torch.tensor([1,2,3,4])
    torch.exp()
    torch.cat((X,Y),dim=0)  # dim=0是竖着排列，=1是横着 
    X.sum()  # 只求一个和
    # 广播机制   复制矩阵  不同维度也可以相加了。
    X[-1] #最后一行访问
    X[1,2] =12  #修改
    
    
    
    # Numpy张量的转换
    A = X.numpy()
    B = torch.tensor(A)
    type(A)  type(B)


# 数据预处理
    import os
    os.makedirs(os.path.join('..','data'),exist_ok=True)  # 创建新目录
    data_file = (os.path.join('..','data','house_tiny.csv')
    with open(data file，'w') as f:
        f.write('NumRooms,Alley,Price\n')  # 列名
        f.write('NA,Pave，127500\n') # 每行表示一个数据样本
        f.write('2,NA,106000\n')
        f.write('4,A,178100\n')
        f.write('NA,NA,140000\n')
      
    # 读取文件
    import pandas as pd
    data = pd.read_csv(data_file)
    print(data)
    
    
    # 处理缺失数据
    inputs, outputs = data.iloc[:, 0:2], data.iloc[:，2]
    inputs = inputs.fillna(inputs.mean())
    print(inputs)
    
    X,y = torch.tensor(inputs.values), torch.tensor(outputf.values)   # 默认为64位浮点数，但我们一般使用32就够了
    
