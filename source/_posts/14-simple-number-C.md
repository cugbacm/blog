title: CUGBACM 14级 简单数论 C题
date: 2015-3-22 17:24:32
tags: [大一, Training]
categories: Training
toc: true
---
# 前言
鉴于明天没空刷题，其他题也不可能第一个A了，于是先把那两道的题解做了。同志们加油。

# 讲解
可能有人会问为什么这道题是我写题解，= =。因为我的浏览器很挫，只好用路娇的账号A了它。
题意：给N个数，问有几个数的M次方能被K整除。
做法一：分解因式，具体做法可能有人能A，没尝试。做法二：快速求模，（mod)k=0则cnt++.
顺便附上一个讲解快速模幂的链接：http://blog.csdn.net/zmazon/article/details/8491301 

# 代码
```
#include<iostream>
#include<stdio.h>
#include<string.h>
#include<string>
#include<algorithm>
#include<math.h>
#include<iomanip>
#include<queue>
#include<map>
#include<set>
#include<vector>
using namespace std;
int solve(int x,int m,int k)
{
   x=x%k;
   int res=1;
    while(m){
        if(m&1)res=(res*x)%k;
        x=(x*x)%k;
        m>>=1;
    }
    return res;
}
int main()
{
    int n,m,k;
    int a[10010];
    scanf("%d%d%d",&n,&m,&k);
    for(int i=0;i<n;i++)
        scanf("%d",&a[i]);
        int tep,res=0;
        for(int i=0;i<n;i++)
        if(!(solve(a[i],m,k)))res++;

        printf("%d\n",res);
}
```

# 作者
14级 邹卓君