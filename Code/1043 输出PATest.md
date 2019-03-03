## 1043 输出PATest （20 分）

给定一个长度不超过 10^​4^的、仅由英文字母构成的字符串。请将字符重新调整顺序，按 `PATestPATest....` 这样的顺序输出，并忽略其它字符。当然，六种字符的个数不一定是一样多的，若某种字符已经输出完，则余下的字符仍按 `PATest` 的顺序打印，直到所有字符都被输出。

**输入格式：**
输入在一行中给出一个长度不超过 10^​4^的、仅由英文字母构成的非空字符串。

**输出格式：**
在一行中按题目要求输出排序后的字符串。题目保证输出非空。

**输入样例：**

    redlesPayBestPATTopTeePHPereatitAPPT

**输出样例：**

    PATestPATestPTetPTePePee

**代码**

```c
//用数组a存储 PATest 每个字符的个数同时记录总字符数 sum 
//然后输出 每输出一个就是使其-1直到最后的字符sum的个数为0 
#include <cstdio>
#include <cstring>
int main() {
	char str[10010], map[6] = {'P', 'A', 'T', 'e', 's', 't'} ;
	int a[6]={0} ;
	scanf ("%s", str) ;
	int sum=0, len=strlen(str) ;
	for (int i=0; i<len; i++) {
		for (int j=0; j<6; j++) {
			if (str[i]==map[j]) {
				a[j]++ ;
				sum++ ;
			}
		}
	}
	while (sum>0) {
		for (int i=0; i<6; i++) {
			if (a[i]>0) {
				printf ("%c", map[i]) ;
				a[i]-- ;
				sum-- ;
			}	 
		}
	}
	return 0 ;
} 
```

