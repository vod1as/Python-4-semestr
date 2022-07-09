# python4semestr
#### Задача 1

Реализовать функцию.

![image](https://user-images.githubusercontent.com/91833762/177773923-32db8fa2-95e3-4671-a7c0-82e65854feb7.png)

```python
import math


def main(y, x, z):
    a = math.atan(5 * z ** 3 + y ** 2) ** 5
    b = 78 * (x ** 2 - 24) ** 6
    c = 84 * (72 * z ** 2 - y ** 3 - z) ** 7 - 26 * x
    d = 69 * (x / 70 - (z ** 2) / 80) ** 6 - 49 * (72 + 36 * y) ** 5
    return a + b + c / d
```

#### Задача 2

Реализовать кусочную функцию.

![image](https://user-images.githubusercontent.com/91833762/177773985-120118a4-65fd-4cf8-83fc-ae19f1859a3c.png)

```python
import math


def main(z):
    if z < 175:
        return (z ** 3 + 24 * z ** 2 + 22 * z) ** 5 - z ** 2 - 54 * z ** 2
    if 175 <= z < 272:
        return 50 * z ** 7
    if 272 <= z < 290:
        return (17 * z ** 2 - z) ** 6 - math.exp(z) - z ** 2
    return (math.ceil(z) ** 5) / 7 - 25
```

#### Задача 3

Реализовать итерационную функцию.

![image](https://user-images.githubusercontent.com/91833762/177774045-cf45a90b-6202-4228-a865-0fc61c63bace.png)

```python
import math


def main(a, m, n):
    total = 0
    for c in range(1, n + 1):
        for i in range(1, m + 1):
            for k in range(1, a + 1):
                left = math.log2(c ** 3 + i ** 2) ** 2
                right = 78 * k ** 3
                total += left + right
    return total
```

#### Задача 4

Реализовать функцию по рекуррентной формуле.

![image](https://user-images.githubusercontent.com/91833762/177774102-30829111-3ccb-4bef-9fa4-b2e503628656.png)

```python
def main(n):
    if n == 0:
        return -0.24
    if n == 1:
        return -0.65
    return main(n - 2) ** 3 + main(n - 1) ** 2 / 48 + 0.2
```

#### Задача 5

Реализовать функцию, оперирующую векторами длины n.

![image](https://user-images.githubusercontent.com/91833762/177774164-b701ef33-f2a1-4703-beb5-5bbdceb1f4c2.png)

```python
import math


def main(y, x, z):
    n = len(y)
    y.insert(0, 0)
    x.insert(0, 0)
    z.insert(0, 0)
    total = 0
    for i in range(1, n + 1):
        left = 2 * y[math.ceil(i / 2)]
        middle = 17 * x[n + 1 - math.ceil(i / 4)] ** 2
        right = 56 * z[math.ceil(i / 2)] ** 3
        total += 88 * (left + middle + right) ** 6
    return 69 * total
```

#### Задача 6

Реализовать функцию для вычисления дерева решений.

![image](https://user-images.githubusercontent.com/91833762/177774229-221f12eb-65b6-402d-bade-0a267f75199a.png)

```python
def zero(items, left, right):
    if items[0] == 'E':
        return left
    if items[0] == 'HAXE':
        return right


def four(items, left, middle, right):
    if items[4] == 1999:
        return left
    if items[4] == 2017:
        return middle
    if items[4] == 1989:
        return right


def three(items, left, right):
    if items[3] == 1989:
        return left
    if items[3] == 1973:
        return right


def two(items, left, right):
    if items[2] == 'MQL5':
        return left
    if items[2] == 'JFLEX':
        return right


def one(items, left, middle, right):
    if items[1] == 1986:
        return left
    if items[1] == 2007:
        return middle
    if items[1] == 2002:
        return right


def main(items):
    return one(
        items,
        three(
            items,
            four(items, 0, 1, zero(items, 2, 3)),
            four(items, 4, 5, zero(items, 6, 7))
        ),
        three(items, two(items, zero(items, 8, 9), 10), 11),
        12
    )
```

#### Задача 7

Реализовать функцию для преобразования битовых полей.

![image](https://user-images.githubusercontent.com/91833762/177774333-1ad31431-c81a-47a5-8c16-f93767fa2fb0.png)

```python
def main(input):
    a = (input & 0b00000000000000000000011111111111) << 15
    b = (input & 0b00000000000000000001100000000000) << 18
    c = (input & 0b00000000000000111110000000000000) >> 13
    d = (input & 0b00000111111111000000000000000000) >> 13
    e = (input & 0b00111000000000000000000000000000) >> 1
    f = (input & 0b01000000000000000000000000000000) << 1
    g = (input & 0b10000000000000000000000000000000) >> 17
    return a | b | c | d | e | f | g
```

#### Задача 8

Реализовать функцию для разбора строки, содержащей данные в текстовом формате.

![image](https://user-images.githubusercontent.com/91833762/177774431-abdbae5e-3174-44c7-a636-b4d5a68f04a9.png)

```python
import re


def main(example):
    exr = r'\s*declare\s*q\(([^)]*)\)\s*:=\s*\[([^\]]*)\]'
    d = {}
    matches = re.findall(exr, example)
    for match in matches:
        s = []
        for j in match[1].split(','):
            j = j.strip().strip("'")
            s.append(j)
        key = match[0]
        d[key] = s
    return d
```

#### Задача 9

Реализовать конечный автомат Мили в виде класса.

![image](https://user-images.githubusercontent.com/91833762/177774710-2dc6425e-7c4d-4455-818a-71e01fcfb13d.png)

```python
from enum import Enum


class State(Enum):
    A = 0
    B = 1
    C = 2
    D = 3
    E = 4
    F = 5
    G = 6
    H = 7


class StateMachine:
    state = State.A

    def fork(self):
        return self.update({
            State.A: [State.B, 0],
            State.E: [State.G, 7],
            State.F: [State.G, 8],
            State.H: [State.B, 11],
        })

    def log(self):
        return self.update({
            State.A: [State.G, 1],
            State.B: [State.C, 2],
            State.D: [State.E, 4],
        })

    def peep(self):
        return self.update({
            State.C: [State.D, 3],
            State.D: [State.A, 5],
            State.E: [State.F, 6],
            State.G: [State.H, 10],
            State.F: [State.B, 9],
        })

    def update(self, transitions):
        self.state, signal = transitions[self.state]
        return signal


def main():
    return StateMachine()
```

#### Задача 10

Реализовать функцию преобразования табличных данных. 

![image](https://user-images.githubusercontent.com/91833762/177774927-2f8280eb-ba78-4ab5-9b4b-49fe0fbd707b.png)

```python
def transpose(table):
    response = []
    for i in range(len(table[0])):
        response.append([])
        for j in range(len(table)):
            response[i].append(table[j][i])
    return response


def delete_empty_rows(table):
    return [row for row in table if row[0] is not None]


def delete_duplicate_columns(table):
    for row in table:
        del row[2]
    return table


def transformer(i, value):
    if i == 0:
        replaced = value \
            .replace(' ', '') \
            .replace('-', '') \
            .replace('+', '')
        return replaced[1:]
    if i == 1:
        digit_str = value.replace('%', '')
        digit = float(digit_str) / 100
        return f'{digit:.2f}'
    if i == 2:
        name = value.split()
        return f'{name[1]} {name[0]}'
    if i == 3:
        return "Выполнено" if value == "Y" else "Не выполнено"


def transform(table):
    for i in range(len(table)):
        for j in range(len(table[i])):
            table[i][j] = transformer(i, table[i][j])
    return table


def main(table):
    return transform(
        transpose(
            delete_duplicate_columns(
                delete_empty_rows(table)
            )
        )
    )
```

#### Задача 11

Реализовать разбор двоичного формата данных. Данные начинаются с сигнатуры 0xf8 0x55 0x51 0x4a, за которой следует структура A. Порядок байт: от младшего к старшему. Адреса указаны в виде смещений от начала данных. В решении предлагается использовать модуль struct.

![image](https://user-images.githubusercontent.com/91833762/177775199-8c4e1318-63f4-4a6d-a8e6-50d4e523e2ad.png)

```python
from struct import *


FMT = dict(
    char='c',
    int8='b',
    uint8='B',
    int16='h',
    uint16='H',
    int32='i',
    uint32='I',
    int64='q',
    uint64='Q',
    float='f',
)


def parse(buf, offs, ty):
    return unpack_from(FMT[ty], buf, offs)[0], offs + calcsize(FMT[ty])


def parse_a(buf, offs):
    a1, offs = parse(buf, offs, 'float')
    a2, offs = parse(buf, offs, 'uint64')
    a3, offs = parse_b(buf, offs)
    a4_size, offs = parse(buf, offs, 'uint32')
    a4_offs, offs = parse(buf, offs, 'uint16')
    a4 = []
    for _ in range(a4_size):
        val, a4_offs = parse(buf, a4_offs, 'char')
        a4.append(val.decode())
    a5, offs = parse_e(buf, offs)
    return dict(A1=a1, A2=a2, A3=a3, A4=''.join(a4), A5=a5), offs


def parse_b(buf, offs):
    b1_size, offs = parse(buf, offs, 'uint16')
    b1_offs, offs = parse(buf, offs, 'uint32')
    b1 = []
    for _ in range(b1_size):
        val, b1_offs = parse_c(buf, b1_offs)
        b1.append(val)
    b2, offs = parse_d(buf, offs)
    b3, offs = parse(buf, offs, 'int8')
    return dict(B1=b1, B2=b2, B3=b3), offs


def parse_c(buf, offs):
    c1, offs = parse(buf, offs, 'uint64')
    c2, offs = parse(buf, offs, 'uint32')
    c3, offs = parse(buf, offs, 'int16')
    c4 = []
    for _ in range(2):
        val, offs = parse(buf, offs, 'uint16')
        c4.append(val)
    return dict(C1=c1, C2=c2, C3=c3, C4=c4), offs


def parse_d(buf, offs):
    d1, offs = parse(buf, offs, 'uint16')
    d2, offs = parse(buf, offs, 'int32')
    d3, offs = parse(buf, offs, 'uint64')
    return dict(D1=d1, D2=d2, D3=d3), offs


def parse_e(buf, offs):
    e1, offs = parse(buf, offs, 'uint32')
    e2, offs = parse(buf, offs, 'int16')
    e3, offs = parse(buf, offs, 'int64')
    e4, offs = parse(buf, offs, 'uint32')
    e5_size, offs = parse(buf, offs, 'uint32')
    e5_offs, offs = parse(buf, offs, 'uint16')
    e5 = []
    for _ in range(e5_size):
        val, e5_offs = parse(buf, e5_offs, 'uint8')
        e5.append(val)
    e6, offs = parse(buf, offs, 'int16')
    return dict(E1=e1, E2=e2, E3=e3, E4=e4, E5=e5, E6=e6), offs


def main(buf):
    return parse_a(buf, 4)[0]
```
