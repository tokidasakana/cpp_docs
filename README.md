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
またこれ以降入力と出力が必ず存在するものとする．

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

<details>
<summary>解答例</summary>
    
```cpp
#include<iostream>
using namespace std;
int main(){
  int a,b;cin>>a>>b;
  cout<<a+b<<'\n';
}

```
</details>

## 2. 条件式

`if`文を使えるようにする．

```cpp
if(条件式){
    処理1
    処理2
    ...
}else{
    処理1
    処理2
    ...
}
```

処理が1つのときは，`{}`で囲う必要なし．

| $=$ | `=` |
|----|----|
| $<$ | `<` |
| $>$ | `>` |
| $\leq$ | `<=` |
| $\geq$ | `>=` |
| $\neq$ | `!=` |

条件が複数ある場合

- 条件式1と条件式2を両方満たさなければいけない：`条件式1 && 条件式2`
- 条件式1と条件式2のどちらかを満たせばよい：`条件式1 || 条件式2`

例えば，
- $N$ が4の倍数：`if(N%4==0)`
- $N$ が100の倍数でない：`if(N%100!=0)`
- $N$ が400の倍数：`if(N%400==0)`
- $N$が4の倍数である かつ ( $N$ が100の倍数ではない または $N$ が400の倍数である)：`if(N%4==0||(N%100!=0&&N%400==0))`

ちなみにこれだけでうるう年の判定ができる．

### 例1

与えられた整数 $N$ が $0$ 以上なら `Yes`，そうでなければ`No`を返す．
```cpp
#include<iostream>
using namespace std;
int main(){
  int N;cin>>N;
  if(N>=0)cout<<"Yes"<<'\n';
  else cout<<"No"<<'\n';
}

```

### 問題2.1

整数 $N$ が与えられるので，偶数なら`Even`，奇数なら`Odd`を返すプログラムを書く．

#### 入力例1
```bash
4
```

#### 出力例1
```bash
Yes
```

#### 入力例2
```bash
3
```

#### 出力例2
```bash
No
```

<details>
<summary>解答例1</summary>

```cpp
#include<iostream>
using namespace std;
int main(){
  int N;cin>>N;
  if(N%2==0)cout<<"Yes"<<'\n';
  else cout<<"No"<<'\n';
}

``` 
</details>

<details>
<summary>解答例2</summary>

実はこんな書き方もある．使えたらかっこいい．

`条件式 ? 条件を満たすときの処理 : 満たさないときの処理`

```cpp
#include<iostream>
using namespace std;
int main(){
  int N;cin>>N;
  cout<<(N%2==0?"Even":"Odd")<<'\n';
}

```

ただし，この二つが同様の処理でないとこの書き方はできない．
例えばこの問題が， $N$ が偶数のとき`Even`を，奇数のときは $N$ をそのまま出力する，というような問題のとき，次のように書いてしまうとエラーがでる．

```cpp
#include<iostream>
using namespace std;
int main(){
  int N;cin>>N;
  cout<<(N%2==0?"Even":N)<<'\n';
}

```
これは`"Even"`は文字列型に対し， `N`は整数型であり，型が異なる処理であるためできない．

</details>
