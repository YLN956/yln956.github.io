---
title: 信安数学基础C语言代码
tags:
  - C语言
  - 学习
categories: 信安数学基础C语言代码
abbrlink: 8120
date: 2020-12-03 19:43:13
---

信安数学部分使用代码解决的作业

<!-- more -->

## 模重复平方计算法



```C
#include <stdio.h>
#include <math.h> 
int main()
{
	int s=1,k,b=7,m=113,t;
	int num,n, c, i = 0;
    int a[32];
    printf("输入学号：");
    scanf("%d", &num);
    n = num;
    while (num>0)
    {
        c = (num % 2);
        a[i] = c;
        num = num / 2;
        i++;
    }
    k=i;
    printf("学号%d转换成二进制数是：", n);
    for (i--; i >= 0; i--)           
        printf("%d", a[i]);
    printf("\n");

	for(i=0;i<k;i++)
	{
		if(a[i]==1)
		{
			s=(s*b)%m;
		}
		t=pow(2,i);
		printf("7^%d = %d (mod %d)\n",t,b,m);
		b=(b*b)%m;
		
		
	}
	printf("\n7^%d = %d (mod %d)\n",n,s,m);
	return 0;
}


```

## Miller -Rabin素性检测算法

```c
#include <stdio.h>
#include <math.h>
int getmod(int b,int n,int m);//模重复平方
int main() {

	int n,sign=1,num;
	int s,t,i,j,h,h1;
	int b;
	printf("...........\n");
	printf("输入要检验的数：");
	scanf("%d",&n);
	printf("求模使用的第一题的模重复平方计算法\n");
	if(n%2==0) {
		printf("%d是合数",n);
		return 0;
	} else {
		num=(n-1)/2;
		while(num%2==0) {
			sign++;
			num=num/2;
		}
	}
	s=sign;
	t=num;
	printf("s=%d,t=%d\n",s,t);
	for(i=2; i<sqrt(n); i++) {

		h=getmod(i,t,n);
		printf("\n当b=%d，",i);
		for(j=0; j<s; j++) {
			h1=pow(2,j);
			b=getmod(h,h1,n);
			printf("b^%d^%d=%d，",t,j,b);
			if(b == 1 || b == n-1) {
				printf("是素数\n");
				break;
			}
			if(j==s-1&&b!=n-1) {
				printf("是合数\n");
				return 0;
			}
			if(b==n-1) {
				printf("是素数\n");
				break;
			}

		}
	}
	printf("结论：%d是素数\n",n);
	return 0;
}

int getmod(int b,int n,int m) {
	int s=1,k,t;
	int num, c, i = 0;
	int a[32];

	num=n;
	while (num>0) {
		c = (num % 2);
		a[i] = c;
		num = num / 2;
		i++;
	}
	k=i;

	for(i=0; i<k; i++) {
		if(a[i]==1) {
			s=(s*b)%m;
		}
		t=pow(2,i);
		b=(b*b)%m;

	}

	return s;
}
```





```java

import  java.util.*;

public class Main {
    static Vector<Integer> ax = new Vector<Integer>();
    static Vector<Integer> bx = new Vector<Integer>();
    static Vector<Integer> rx = new Vector<Integer>();
    public static void main(String[] args) {
        String a,b;
        //输入的数字转换成字符数组
        Scanner in = new Scanner(System.in);
        System.out.println("请输入域(输入2表示域F2[X]):");
    	int n =in.nextInt();
    	System.out.println("请输入ax(101011表示X^5+X^3+X+1):");

        a = in.next();
        char[] arraya = a.toCharArray();
        //转成数字数组
        for(int i=0;i<a.length();i++)
            ax.addElement(arraya[i]-'0');
        
    	System.out.println("请输入bx(1111表示X^3+X^2+X+1)");
        b = in.next();

        char[] arrayb = b.toCharArray();
        for(int i=0;i<b.length();i++)
            bx.addElement(arrayb[i]-'0');
        //输出ax，bx代表的多项式
        System.out.print("ax = ");  
        	Invert(ax);  
        	System.out.println();
        System.out.print("bx = ");  
        	Invert(bx);     
        	System.out.println();
        in.close();
        Euclidean(ax,bx,n);

        }
    
    public static void Euclidean(Vector<Integer> ax,Vector<Integer> bx,int n) {
        int al = ax.size();
        int bl = bx.size();
        Vector<Integer> cx = new Vector<Integer>();
        Vector<Integer> tx = new Vector<Integer>();
        int t = 0,count=1;
        
        Invert(ax);
        System.out.print(" = ");
        for(int i=0;i<al-bl+1;i++) {
        	int cx0=(ax.get(0)-count*bx.get(0)+n)%n;
        		while(cx0!=0) {
        			count++;
        			cx0=(ax.get(0)-count*bx.get(0)+n)%n;

            		
            	}
        		if(ax.get(0)==0) count=0;
        	
            cx.add(i, count);
            int ax0 = count;
            for(int j=0;j<bl;j++) {

            		if(ax0>0) {

                        	ax.set(j, (ax.get(j)-ax0*bx.get(j)+n)%n);
            		}

            }         
            ax.remove(0);
        }
   
        System.out.print("(");
        Invert(bx);
        System.out.print(")(");
        Invert(cx);
        System.out.print(") + (");
        Invert(ax);        
        System.out.println(") ");
    }
    
    //vector->多项式输出
    public static void Invert(Vector<Integer> a) {
        int asize = a.size();
        
        for(int i=0;i<asize;i++) {
        	if(a.get(i)>0) {
        		if(i==a.size()-1)
        		{
        			System.out.print(a.get(i));
        			break;
        		}
    			System.out.print(a.get(i)+"*x^"+(a.size()-i-1)+" + ");
        	}
        }

    }
}

```

