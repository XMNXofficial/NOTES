# Cmake学习
## 搜索文件
### 0x01.如何搜索一个文件夹下的cpp文件?
将搜索到的cpp文件放入迭代器`CPP_SOURCES`中
```cmake
file(GLOB CPP_SOURCES "*.cpp")
```
### 0x02.如何搜索一个文件夹下的所有cpp文件(包括子文件夹)?
```cmake
file(GLOB_RECURSE  CPP_SOURCES "*.cpp")
```
### 0x03.file命令的选项
在 CMake 的 `file` 命令中，第一个参数可以选择以下选项之一：

- `COPY`: 复制文件或目录到指定位置。
- `REMOVE`: 移除指定的文件或目录。
- `RENAME`: 重命名文件或目录。
- `MAKE_DIRECTORY`: 创建目录。
- `TOUCH`: 创建空文件或设置文件的访问和修改时间戳。
- `WRITE`: 创建文件并写入指定的内容。
- `APPEND`: 在文件末尾追加内容。
- `READ`: 读取文件的内容。
- `GLOB`: 根据模式匹配搜索文件，并将结果存储在变量中。
- `GLOB_RECURSE`: 递归地根据模式匹配搜索文件，并将结果存储在变量中。
- `SHA1`: 计算指定文件的 SHA1 哈希值。
- `SHA256`: 计算指定文件的 SHA256 哈希值。
- `MD5`: 计算指定文件的 MD5 哈希值。
- `COMPARE`: 比较两个指定文件的内容是否相同，并将结果存储在变量中。
- `IS_DIRECTORY`: 判断指定路径是否为目录，并将结果存储在变量中。
- `IS_SYMLINK`: 判断指定路径是否是符号链接，并将结果存储在变量中。
- `IS_ABSOLUTE`: 判断指定路径是否是绝对路径，并将结果存储在变量中。
- `EXISTS`: 判断指定文件或目录是否存在，并将结果存储在变量中。
- `SIZE`: 获取指定文件的大小，并将结果存储在变量中。

### 获取文件名/拓展名/目录
```cmake
    get_filename_component(<接收文件名用的变量> <全路径> NAME_WE) #文件名
    get_filename_component(<接收拓展名用的变量> <全路径> EXT) #拓展名
    get_filename_component(<接收目录用的变量> <全路径> DIRECTORY) #目录
```

## 循环
### foreach命令(for循环)
```cmake
foreach(<每次循环的变量名> <列表(类似迭代器)>) #开始循环
循环执行的命令1()
循环执行的命令2()
循环执行的命令3()
endforeach() #结束循环
```

## 测试命令
### message命令
相当于打印
```cmake
message("你好")
```