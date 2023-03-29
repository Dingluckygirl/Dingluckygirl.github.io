# Matplotlib库

    import matplotlib.pyplot as plt

    # 准备数据
    x = [1, 2, 3, 4]
    y = [1, 4, 9, 16]

    # 绘制折线图
    plt.plot(x, y)

    # 添加标题和标签
    plt.title('Simple Line Plot')
    plt.xlabel('x')
    plt.ylabel('y')

    # 显示图形
    plt.show()
    
# 

    import matplotlib.pyplot as plt
    import numpy as np

    # 准备数据
    x = np.linspace(0, 10, 100)
    y1 = np.sin(x)
    y2 = np.cos(x)

    data = {'apples': 10, 'pears': 5, 'oranges': 15}

    labels = list(data.keys())
    values = list(data.values())

    # 创建一个1行3列的子图
    fig, axs = plt.subplots(1, 3, figsize=(12, 4))

    # 在第一个子图中绘制线图
    axs[0].plot(x, y1, label='sin(x)')
    axs[0].plot(x, y2, label='cos(x)')
    axs[0].set_xlabel('x')
    axs[0].set_ylabel('y')
    axs[0].set_title('Line Plot')
    axs[0].legend()

    # 在第二个子图中绘制柱状图
    axs[1].bar(labels, values)
    axs[1].set_xlabel('Fruit')
    axs[1].set_ylabel('Quantity')
    axs[1].set_title('Bar Chart')

    # 在第三个子图中绘制散点图和饼图
    axs[2].scatter(x, y1)
    axs[2].pie(values, labels=labels, autopct='%1.1f%%')
    axs[2].set_title('Scatter Plot and Pie Chart')

    # 调整子图之间的间距
    plt.subplots_adjust(wspace=0.3)

    # 显示图形
    plt.show()
    
# plot  简单的绘制
    plt.plot(x, y, fmt, ...)
    fmt是一个字符串参数，用于指定线型、颜色和标记类型等参数。例如，'ro-'表示红色圆形实心线条，'g^--'表示绿色三角形空心线条。

