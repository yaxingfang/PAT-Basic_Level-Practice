﻿## 1002 写出这个数 （20 分）

读入一个正整数 n，计算其各位数字之和，用汉语拼音写出和的每一位数字。

**输入格式：**
每个测试输入包含 1 个测试用例，即给出自然数 n 的值。这里保证 n 小于 10
​100
​​ 。

**输出格式：**
在一行内输出 n 的各位数字之和的每一位，拼音数字间有 1 空格，但一行中最后一个拼音数字后没有空格。

**输入样例：**
1234567890987654321123456789
**输出样例：**
yi san wu

**代码**

```c
#include <cstdio>
#include <cstring> 
char map[10][20] = { "ling","yi","er","san","si","wu","liu","qi","ba","jiu" }; //二维数组表示字符串集合 
char str[110] = {0} ;						//将数字当成字符串进行处理								
int main () {
	scanf ("%s", str) ;
	int sum = 0;
	for (int i=0; str[i]!='\0'; i++) {
		sum += str[i]-'0' ;
	}										//得到各位之和 
	char a[10] = {0} ;
	sprintf (a, "%d", sum) ;				//将该数转变成字符串形式 
	int len ;	
	len = strlen(a) ;
	for (int i=0; i<len-1; i++) {			//从字符串第一位开始进行映射
		printf ("%s ", map[a[i]-'0']) ;
	}										
	printf ("%s", map[a[len-1]-'0']) ;		//最后没有空格
	return 0 ;
}
```

