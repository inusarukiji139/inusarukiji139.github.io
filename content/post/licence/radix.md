---
title: "基数変換　サンプルプログラム"
date: 2023-07-30
categories: ["資格"]
tags: ["基本情報"]
---
## 10進数 → 2進数

`Python`

```c
# 変数
num = 20
answer = ''

# 10進数 → 2進数
while True:
    # ①10進数を2進数の基数2で割る
    if num % 2 == 0:
        # ②余りを取り出し、前に並べる
        answer = "0" + answer
    elif num % 2 == 1:
        answer = "1" + answer
    # ③商が0になるまで繰り返す
    num = num // 2
    if num == 0:
        break

print(answer)
```
## 10進数 → 2進数(小数)

`Python`

```c
# 変数
num = 0.005
answer = ''
# 無限小数対策
count = 0

# 10進数 → 2進数(小数)
while True:
    # ①10進数に2進数の基数2をかける
    num = num * 2
    # ②整数部だけ取り出し、後ろに並べる
    if num < 1:
        answer = answer + "0"
    elif num > 1:
        answer = answer + "1"
        num = num - 1
    # ③小数部が0になるまで繰り返し
    if num == 1:
        answer = answer + "1"
        break
    # 無限小数対策
    count = count + 1
    if count > 30:
        break

print("0."+ answer)

```

## 2進数→10進数

`Python`

```c
# 変数
binary = "11111111"
index = 0
result = 0

# 2進数→10進数
while True:
    # ①桁の重みを求める
    # ex. 8-0(最初の桁) -1
    # 1の位が起点になるので、8の位の重みは8-1=7になる
    base = len(binary) - index - 1
    # ②各桁に重みを掛け、合計する
    result = result + int(binary[index]) * 2 ** base
    # 次の桁がなくなるまで繰り返し
    index = index + 1
    if index < len(binary):
        break
    
print(result)

```