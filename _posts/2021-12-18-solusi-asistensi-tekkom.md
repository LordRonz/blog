---
toc: true
comments: true
layout: post
description: Solusi dari problem-problem yang ada di tugas asistensi Alprognya aslab usa_Ida yang versi tekkom.
categories: [markdown]
title: Solusi Tugas Asistensi Alprog usa_Ida (Tekkom ver.)
---
# Solusi Tugas Asistensi Alprog usa_Ida (Tekkom Version)

[Problem](https://gist.github.com/LordRonz/c6a477739bb820dafaff39958b6d33a7)

Ini solusi dengan cara saya, mungkin kalian punya opini berbeda


## 1. Hephaestus berIQ over 9000

[Link](https://gist.github.com/LordRonz/c6a477739bb820dafaff39958b6d33a7#1-hephaestus-beriq-over-9000-solved-by-cepheus)

```c
#include <stdio.h>

int main(void)
{
    int n, even = 0, odd = 0, num, eindex, oindex;
    scanf("%d", &n);
    for(int i = 1; i <= n; ++i) {
        scanf("%d", &num);
        if(num & 1) {
            ++odd;
            oindex = i;
        }
        else {
            ++even;
            eindex = i;
        }
    }
    printf("%d\n", odd < even ? oindex : eindex);
    return 0;
}
```

## 2. Dukun Olympus [SOLVED By Cepheus]

[Link](https://gist.github.com/LordRonz/c6a477739bb820dafaff39958b6d33a7#2-dukun-olympus-solved-by-cepheus)

```cpp
#include <bits/stdc++.h>
 
using namespace std;
#define MAX(a,b,c) max(a,max(b,c))
#define MIN(a,b,c) min(a,min(b,c))
typedef pair<int, int> pii;
//0xACCE97ED

int main()
{
    int n, res = -1;
    string a;
    unordered_map<string, int> mp;
    scanf("%d", &n);
    while(n--) {
        cin >> a;
        if(mp.find(a) == mp.end()) {
            mp[a] = 1;
        }
        else ++mp[a];
    }
    for(auto& it: mp) {
        if(it.second > res) {
            res = it.second;
            a = it.first;
        }
    }
    cout << a << '\n';
    return 0;
}
```

## 3. Atlet lari pecinta matekmatika

[Link](https://gist.github.com/LordRonz/c6a477739bb820dafaff39958b6d33a7#3-atlet-lari-pecinta-matekmatika)

```cpp
#include <bits/stdc++.h>

using namespace std;
#define MAX(a,b,c) max(a,max(b,c))
#define MIN(a,b,c) min(a,min(b,c))
#define MP make_pair
#define FOR(x, a, b) for(int x = a; x < b; ++x)
typedef pair<int, int> pii;
//0xACCE97ED;

int main() {
    int t;
    long long a, b, x, y, n;
    scanf("%d", &t);
    while(t--) {
        scanf("%lld %lld %lld %lld %lld", &a, &b, &x, &y, &n);
        int tmp;
        long long a1 = a, b1 = b, n1 = n, a2 = a, b2 = b, n2 = n;
        tmp = min(a1 - x, n1);
        a1 -= tmp;
        n1 -= tmp;
        tmp = min(b1 - y, n1);
        b1 -= tmp;
        tmp = min(b2 - y, n2);
        b2 -= tmp;
        n2 -= tmp;
        tmp = min(a2 - x, n2);
        a2 -= tmp;
        printf("%lld\n", min(a1 * b1, a2 * b2));
    }
    return 0;
}
```

## 4. Kang dayung

[Link](https://gist.github.com/LordRonz/c6a477739bb820dafaff39958b6d33a7#4-kang-dayung)

```cpp
#include <bits/stdc++.h>

using namespace std;
#define MAX(a,b,c) max(a,max(b,c))
#define MIN(a,b,c) min(a,min(b,c))
#define MP make_pair
#define FOR(i, a, b) for(int i = a; i < b; ++i)
#define gcd __gcd
typedef pair<int, int> pii;
typedef long long ll;
const int MAX_N = 1e5 + 1;
//0xACCE97ED;

int main() {
    int t, n, w, cnt[55];
    scanf("%d", &t);
    while(t--) {
        scanf("%d", &n);
        memset(cnt, 0, sizeof(cnt));
        for(int i = 0; i < n; ++i) {
            scanf("%d", &w);
            ++cnt[w];
        }
        int ans = 0;
        for (int s = 2; s <= 2 * n; ++s) {
            int cur = 0;
            for (int i = 1; i < (s + 1) / 2; ++i) {
                if (s - i > n) continue;
                cur += min(cnt[i], cnt[s - i]);
            }
            if (s % 2 == 0) cur += cnt[s / 2] / 2;
            ans = max(ans, cur);
        }
        printf("%d\n", ans);
    }
    return 0;
}
```
