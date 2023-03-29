# 数据处理相关库

# OS库

os.getcwd()：返回当前工作目录的路径。

os.chdir(path)：改变当前工作目录到指定的路径。

os.listdir(path)：返回指定目录下的所有文件和子目录的名称列表。

os.mkdir(path)：创建一个指定名称的目录。

os.makedirs(path)：递归地创建多层目录。

os.rename(src, dst)：将src重命名为dst。

os.remove(path)：删除指定路径的文件。

os.rmdir(path)：删除指定路径的目录（只能删除空目录）。

os.removedirs(path)：递归地删除多层空目录。

    import os

    # 获取当前工作目录
    current_dir = os.getcwd()
    print("Current Directory:", current_dir)

    # 创建新目录
    new_dir = "example_dir"
    os.mkdir(new_dir)
    print("New directory created:", new_dir)

    # 更改当前工作目录
    os.chdir(new_dir)
    print("Current directory changed to:", os.getcwd())

    # 列出当前目录下的文件和子目录
    contents = os.listdir()
    print("Contents of current directory:", contents)

    # 删除目录
    os.chdir("..")
    os.rmdir(new_dir)
    print("Directory deleted:", new_dir)

# zipfile库(r表示只读）

    import zipfile

    with zipfile.ZipFile('example.zip', 'r') as zip_file:
    
    # 提取单个文件
    zip_file.extract('file1.txt')

    # 提取整个ZIP文件到目标目录
    zip_file.extractall('/path/to/target/dir')
    
# 解压文件

    def unzip_data(src_path,target_path):

        # 解压原始数据集，将src_path路径下的zip包解压至data/dataset目录下

        if(not os.path.isdir(target_path)):    
            z = zipfile.ZipFile(src_path, 'r')
            z.extractall(path=target_path)
            z.close()
        else:
            print("文件已解压")
