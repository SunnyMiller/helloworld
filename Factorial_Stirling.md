/*链接：https://www.nowcoder.net/acm/contest/75/A
来源：牛客网

时间限制：C/C++ 1秒，其他语言2秒
空间限制：C/C++ 32768K，其他语言65536K
64bit IO Format: %lld
题目描述 
夫夫有一天对一个数有多少位数感兴趣，但是他又不想跟凡夫俗子一样，
所以他想知道给一个整数n，求n！的在8进制下的位数是多少位。
输入描述:
第一行是一个整数t(0<t<=1000000)(表示t组数据)
接下来t行，每一行有一个整数n(0<=n<=10000000)
输出描述:
输出n！在8进制下的位数。
示例1
输入
3
4
2
5
输出
2
1
3*/
/*
  求一个数n的阶乘，当n足够大的时候会超过数的表示范围，为了能成功输出正确的n！可以用一个一维数组来存储n！，在这个题当中，并不需要求出具体的n！的值，因为当n足够大的时候，每乘上一个数会让当前这个数发生很大的变化，因此可以引用Stirling公式来求出n！的大概值——Stirling公式：n！~sqrt(2*Pi*n)*(n/e)^n；
  
  求一个数n的位数可以用log来求，当求该数十进制数的位数时可以用log10（n），当需要求该数八，十六进制数等的位数的时候可以换底公式——logm(n)=ln(n)/ln(m)；
*/

#include <cstdio>
#include <iostream>
#include <cmath>

using namespace std;
#define PI 3.1415926
#define e 2.71828182
int main()
{
	int t;
	scanf("%d",&t);
	while(t--){
		int n;
		scanf("%d",&n);
		if(n==1||n==0)
		{
			printf("1\n");
		}else {
			printf("%d\n",(int)(log(2*PI*n)/log(8)/2+n*log(n/e)/log(8))+1);
		}
		
	}
	return 0;
}

/*
注：PI=acos(-1)
*/
