---
toc: true
comments: true
layout: post
description: Solusi dari problem-problem yang ada di tugas asistensi Alprognya aslab usa_Ida.
categories: [markdown]
title: Solusi Tugas Asistensi Alprog usa_Ida
---
# Solusi Tugas Asistensi Alprog usa_Ida

[Problem](https://gist.github.com/LordRonz/719a60c8bb77b051924bd991f55082fb)

Ini solusi dengan cara saya, mungkin kalian punya opini berbeda


## 1. Badak dan Ular

[Link](https://gist.github.com/LordRonz/719a60c8bb77b051924bd991f55082fb#1-badak-dan-ular-solved-by-neoptolemus)

```cpp
#include<bits/stdc++.h>

using namespace std;

int main() {
    int n, m;
    scanf("%d %d", &n, &m);
    for(int i = 1; i <= n; ++i) {
        for(int j = 1; j <= m; ++j) {
            if(!(i & 1) && i % 4 == 2 && j == m) {
                printf("#");
            }
            else if(!(i & 1) && i % 4 == 0 && j == 1) {
                printf("#");
            }
            else if(i & 1) {
                printf("#");
            }
            else printf(".");
        }
        printf("\n");
    }
    return 0;
}
```

## 2. File Nackal

[Link](https://gist.github.com/LordRonz/719a60c8bb77b051924bd991f55082fb#2-file-nackal)

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
    int n, xcnt = 0, res = 0;
    char s[105];
    scanf("%d\n", &n);
    scanf("%s", s);
    for(int i = 0; i < n; ++i) {
        if(s[i] == 'x') {
            ++xcnt;
        }
        else {
            xcnt = 0;
        }
        if(xcnt > 2) ++res;
    }
    printf("%d\n", res);
    return 0;
}
```

## 3. Belanja Tissue

[Link](https://gist.github.com/LordRonz/719a60c8bb77b051924bd991f55082fb#3-belanja-tissue-solved-by-triton)

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
    int t, s;
    scanf("%d", &t);
    while(t--) {
        scanf("%d", &s);
        int res = 0, tmp;
        while(s / 10) {
            tmp = s / 10;
            res += tmp * 10;
            s -= tmp * 10;
            s += tmp;
        }
        res += s;
        printf("%d\n", res);
    }
    return 0;
}
```

## 4. ALERTA ALERTA

[Link](https://gist.github.com/LordRonz/719a60c8bb77b051924bd991f55082fb#4-alerta-alerta)

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
    int t, n, a[101];
    int freq[101];
    scanf("%d", &t);
    while(t--) {
        scanf("%d", &n);
        memset(freq, 0, sizeof(freq));
        for(int i = 0; i < n; ++i) {
            scanf("%d", &a[i]);
            ++freq[a[i]];
        }
        int trgt = 0;
        for(int i = 1; i < 101; ++i) {
            if(freq[i] == 1) {
                trgt = i;
                break;
            }
        }
        for(int i = 0; i < n; ++i) {
            if(a[i] == trgt) {
                printf("%d\n", i + 1);
                break;
            }
        }
    }
    return 0;
}
```
