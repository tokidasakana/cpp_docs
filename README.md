<script type="text/x-mathjax-config">MathJax.Hub.Config({tex2jax:{inlineMath:[['\$','\$'],['\\(','\\)']],processEscapes:true},CommonHTML: {matchFontHeight:false}});</script>
<script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML"></script>
## 準備

C++で `Hello World` を出力するコードを書く．

```cpp
#include<iostream>
using namespace std;
int main(){
    cout<<"Hello World"<<'\n';
}

```

実行する．エラーが出たらプログラムを修正する．

```bash
$ g++ a.cpp

$ ./a.out
Hello World

$ 
```

## 1. 変数

|変数名|意味|
|----|----|
|`int`|整数|
|`double`|実数|
|`char`|文字|
|`string`|文字列|

### 例

整数 $N$ と文字列 $S$ を受け取り，その順に出力するプログラム

```cpp
#include<iostream>
using namespace std;
int main(){
  int N;
  string S;
  cin>>N>>S;
  cout<<N<<S<<'\n';
}
```

### 問題1.1

整数 $a,b$ が与えられるので， $a+b$ を出力するプログラムを書く．

#### 入力例1

```bash
1 2
```
#### 出力例1
```bash
3
```
