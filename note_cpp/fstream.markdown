# 文件读写
## fstream ifstream ofstream
| 命令     | 用法             |
| -------- | ---------------- |
| fstream  | 可读可写         |
| ifstream | 只读,前面有个in  |
| ofstream | 只写,前面有个out |
# 内部命令
## seekg:移动文件指针到指定位置
```cpp
seekg(<读取指针-相对于起始点的偏移量(字节数)>, <起始点>);
```
```cpp
seekg(<输出指针-相对于起始点的偏移量(字节数)>, <起始点>);
```
| 命令          | 解释                       |
| ------------- | -------------------------- |
| std::ios::beg | 从文件开头开始计算偏移量。 |
| std::ios::cur | 相对于当前位置计算偏移量。 |
| std::ios::end | 相对于文件末尾计算偏移量。 |

## tellg:获取当前文件指针位置
```cpp
std::streampos position = file.tellg(); //读取位置
std::cout << "当前文件读取指针位置： " << position << std::endl;
```
```cpp
std::streampos position = file.tellp(); //读取位置
std::cout << "当前文件输出指针位置： " << position << std::endl;
```

## read:从文件指针读取指定大小字节到缓冲区
注意:`read`命令,从`当前文件指针位置`开始读取
```cpp
file.read(<接收缓冲区>, <读取字节数>);
```