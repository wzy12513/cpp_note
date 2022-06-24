# std::string



```c++
#include<string>
```

C++风格的字符串，不用担心内存，做到自动分配和释放内存

## C++风格字符串 

```c++
std::string s1 = "hello"; 
std::string s2("world");
```



## 求取字符串长度

```c++
cout << s1.size() << endl; 
cout << s1.length() << endl;
```

```c++
#include <iostream>
#include <string>

using namespace std;

void test()
{
    string s1;
    cout << "s1.size() : " << s1.size() << endl
         << "s1.empty() : " << s1.empty() << endl;

    string s2("hello");
    cout << "s2.size() : " << s2.size() << endl
         << "s2.empty() : " << s2.empty() << endl;
}

int main()
{

    test();

    return 0;
}
```

![image-20220624213836314](pages/image-20220624213836314.png)

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

## 示例

```c++
#include <iostream>
#include <string>
using std::cout;
using std::endl;
using std::string;
 
void test0() 
{
	string s1;
	cout << "s1:" << s1 << endl;
	cout << "s1.size():" << s1.size() << endl;
	cout << "s1.empty():" << s1.empty() << endl << endl;

	//将C风格字符串转换成C++风格字符串
	string s2("hello");
	cout << "s2:" << s2 << endl;
	cout << "s2.length():" << s2.length() << endl;
	cout << "s2.empty():" << s2.empty() << endl << endl;

	string s3("worldaaa", 5);
	cout << "s3:" << s3 << endl;

	cout << (s2 == s3) << endl;
	cout << (s2 != s3) << endl;

	cout << endl << "执行加法操作 " << endl;
	//字符串拼接操作
	//string s4 = s2 + "wuhan" + s3;
	string s4 = "wuhan" + s3 + s2 + 'X';
	cout << "s4:" << s4 << endl << endl;

	//字符串附加操作
	cout << endl << "执行append操作 " << endl;
	s2.append(s3);
	s2.append(3, 'a');
	s2.append(",wuhan");
	cout << "s2:" << s2 << endl;

	//将C++风格的字符串转换成C风格的字符串
	cout << endl << "转换成C风格字符串操作 " << endl;
	printf("s4:%s\n", s4.c_str());
	printf("s4:%s\n", s4.data());

	//遍历元素
	cout << endl << "C++风格字符串用下标访问某一个字符 " << endl;
	for(size_t idx = 0; idx < s4.size(); ++idx) {
		cout << s4[idx] << " ";
	}
	cout << endl;
	
    cout << endl << "C++风格字符串增强for循环 " << endl;
	//auto关键字表示自动进行推导
	//& 引用符号，直接操作元素本身；
	//如果没有使用引用，就会进行复制
	//冒号左边的是表示任一元素，右边的表示容器
	//    ch : s4
	for(auto & ch : s4) {
		cout << ch << " ";
	}
	cout << endl;

	//迭代器简单理解，就是指针
	cout << endl << "C++风格字符串迭代器访问 " << endl;
	auto it = s4.begin();
	while(it != s4.end()) {
		cout << *it << " ";
		++it;
	}
	cout << endl;

	cout << endl << "C++风格字符串进行子串截取操作" << endl;
	string s5 = s4.substr(5, 5);
	cout << "s5:" << s5 << endl;

	auto pos = s4.find("world");
	cout << "pos:" << pos << endl;
	pos = s4.find(s5);
	cout << "pos:" << pos << endl;



} 
 
int main(void)
{
	test0();
	return 0;
}

```

![image-20220624214458163](pages/image-20220624214458163.png)

# std::vector
