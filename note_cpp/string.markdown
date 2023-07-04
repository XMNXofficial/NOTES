# std::string
## 函数和属性
### find
```cpp
find(<被寻找的字符串>)
```
```cpp
find(<被寻找的字符串>,<起始搜索位置>)
```
### std::string::npos
用于表示`搜索不到字符串`,数值为`-1`

### replace
用于替换字符串,`备注,用来替换的字符串的长度,可以大于,被替换的字符串的长度`
```cpp
replace(<起始位置>,<被替换目标的长度>,<用来替换的字符串>);
```
### 实战:批量替换字符串
```cpp
#include <iostream>
int main()
{
    std::string a = "hello XMNX1599 XMNX";
    std::string b = "XMNX";
    std::string c = "XMNXofficial";
    size_t pos=0;
    while((pos=a.find(b,pos))!=std::string::npos)
    {
        a.replace(pos++,b.length(),c);
    }
    std::cout<<a<<std::endl;
    return 0;
}
```