# -第二次作业
1.第一版本程序Prog1：
+ 给定一个数组，实现数组元素求和；，具体要求：实现对一维数组(a[100])的所有元素相加运算。
+ 数据准备：a）数组长度：100；b）数组数据来源：实验数据A列：1~100，CSV 格式则填充 前100个数据。
程序如下：
#include<iostream>
 
#include<fstream>
 
using namespace std;
 
 
 
int main()
 
{
 
         int a[100];//定义一个数组
 
         int sum=0;//总和变量初始化
 
         ifstream Data("D:\\data.txt");
 
         if(!Data)
 
         {cout<<"不能打开文件";exit(1);}//判断文件是否能被打开
 
         for(int i=0;Data>>a[i],i<100;i++)
 
         {
 
                   sum+=a[i];//做加法
 
         }
 
         cout<<sum;
 
 
 
         return 0;
 
}
2.第二版本程序Prog2：
+ 改写成一个函数（函数名称为ArraySum)，能实现任意长度数组所有元素求和；
+ 数据准备：a）数组长度：任意； b）数组数据来源：实验数据A列.
源程序：
 
#include<iostream>
 
#include<fstream>
 
using namespace std;
 
 
 
void ArraySum(int n)
 
{
 
         int *a=new int[n];
 
         int sum=0;
 
        
 
         if(a==0)
 
         {
 
                   cout<<"没有申请到动态内存";exit(3);}
 
         ifstream Data("D:\\data.txt");
 
         if(!Data)
 
         {
 
                   cout<<"不能打开文件";exit(1);
 
         }
 
        
 
         for(int i=0;Data>>a[i],i<n;i++)
 
         {       
 
                   sum+=a[i];
 
         }
 
         cout<<sum;
 
         delete []a;
 
 
 
}
 
 
 
int main()
 
{
 
         int n;
 
         cout<<"请输入数组长度：";
 
         cin>>n;
 
         cout<<"所求和为：";
 
         ArraySum(n);
 
         return 0;
 
}
3.第三版本程序Prog3：
+ 将Prog2改写成能从文件中读取数据，实现任意长度数组，指定范围内元素相加。
+ 数据准备：a）数组长度：任意； b）数组数据来源：从文件中读取.
源程序如下：
 
#include<iostream>
 
#include<fstream>
 
using namespace std;
 
 
 
void ArraySum(int n,int min,int max)
 
{
 
         int *a=new int[n];
 
         int sum=0;
 
        
 
         if(a==0)
 
         {
 
                   cout<<"没有申请到动态内存";exit(3);}
 
         ifstream Data("D:\\data.txt");
 
         if(!Data)
 
         {
 
                   cout<<"不能打开文件";exit(1);
 
         }
 
        
 
         for(int i=0;Data>>a[i],i<n;i++)
 
         {       
 
                   if(min<a[i]&&a[i]<max)
 
                   sum+=a[i];
 
         }
 
         cout<<sum;
 
         delete []a;
 
 
 
}
 
 
 
int main()
 
{
 
         int n,min,max;
 
         cout<<"请依次输入数组长度，最小值和最大值：";
 
         cin>>n>>min>>max;
 
 
 
         cout<<"所求和为：";
 
         ArraySum(n,min,max);
 
         return 0;
 
}

