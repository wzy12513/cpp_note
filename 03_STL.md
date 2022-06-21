# std::string



```c++
#include<string>
```

C++风格的字符串，不用担心内存，做到自动分配和释放内存

## C风格字符串转换为C++风格字符串 

```c++
std::string s1 = "hello"; 
std::string s2("world");
```



## 求取字符串长度

```c++
cout << s1.size() << endl; 
cout << s1.length() << endl;
```



## 字符串的遍历

```c++
for(size_t idx = 0; idx != s1.size(); ++idx) 
{ 
    cout << s1[idx] << " "; 
}
cout << endl;
```



## 字符串拼接

```c++
std::string s3 = s1 + s2; 
cout << "s3 = " << s3 << endl;
```



## 查找子串

```c++
size_t pos = s1.find("world");
```



## 截取子串

```c++
std::string substr = s1.substr(pos); 
cout << "substr = " << substr << endl;
```



# std::ector
