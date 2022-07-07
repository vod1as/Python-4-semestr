#### Задача 1

Реализовать функцию.

[Условие задачи](http://kispython.ru/docs/0/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

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

[Условие задачи](http://kispython.ru/docs/1/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

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

[Условие задачи](http://kispython.ru/docs/2/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

<img src="https://user-images.githubusercontent.com/6759207/169617721-bd496f38-2f08-47e3-8ab4-3a4d193272b6.png" width="500" />

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

[Условие задачи](http://kispython.ru/docs/3/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

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

[Условие задачи](http://kispython.ru/docs/4/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

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

[Условие задачи](http://kispython.ru/docs/5/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

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

> Для генерации [битовых масок](https://jakevdp.github.io/WhirlwindTourOfPython/04-semantics-operators.html#Bitwise-Operations) может быть полезно написать функцию `generate_mark(begin, end)`.

[Условие задачи](http://kispython.ru/docs/6/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

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

> Для отладки [регулярных выражений](https://docs.python.org/3/library/re.html) можно воспользоваться сервисом [regexr.com](http://regexr.com) или [regex101.com](https://regex101.com/)

[Условие задачи](http://kispython.ru/docs/7/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

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

[Условие задачи](http://kispython.ru/docs/8/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

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

[Условие задачи](http://kispython.ru/docs/9/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

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

Реализовать разбор двоичного формата данных.

> Перед решением задачи полезно ознакомиться с [документацией](https://docs.python.org/3/library/struct.html#byte-order-size-and-alignment) модуля `struct`.

[Условие задачи](http://kispython.ru/docs/10/%D0%98%D0%9D%D0%91%D0%9E-15-20.html#%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-40)

##### Способ решения 1

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

##### Способ решения 2

> Приведенный способ решения вдохновлён типом [BinaryReader](https://docs.microsoft.com/ru-ru/dotnet/api/system.io.binaryreader?view=net-6.0) из стандартной библиотеки .NET.

```python
from struct import unpack_from, calcsize
from typing import Any, Callable


class BinaryReader:
    def __init__(self, source, offset=0):
        self.offset = offset
        self.source = source

    def read_uint64(self):
        return self.read('Q')

    def read_int64(self):
        return self.read('q')

    def read_uint32(self):
        return self.read('I')

    def read_int32(self):
        return self.read('i')

    def read_uint16(self):
        return self.read('H')

    def read_int16(self):
        return self.read('h')

    def read_uint8(self):
        return self.read('B')

    def read_int8(self):
        return self.read('b')

    def read_float(self):
        return self.read('f')

    def read_char(self):
        return self.read('c')

    def read(self, pattern: str):
        size = calcsize(pattern)
        data = unpack_from(pattern, self.source, self.offset)
        self.offset += size
        return data[0]


def read_array(
    source: str,
    size: int,
    address: int,
    read: Callable[[BinaryReader], Any],
    structure_size: int = 1,
):
    reader = BinaryReader(source=source, offset=address)
    values = []
    while address + (size * structure_size) > reader.offset:
        values.append(read(reader))
    return values


def read_e(reader: BinaryReader):
    e1 = reader.read_uint32()
    e2 = reader.read_int16()
    e3 = reader.read_int64()
    e4 = reader.read_uint32()
    e5 = read_array(
        source=reader.source,
        size=reader.read_uint32(),
        address=reader.read_uint16(),
        read=lambda reader: reader.read_uint8()
    )
    e6 = reader.read_int16()
    return dict(E1=e1, E2=e2, E3=e3, E4=e4, E5=e5, E6=e6)


def read_d(reader: BinaryReader):
    d1 = reader.read_uint16()
    d2 = reader.read_int32()
    d3 = reader.read_uint64()
    return dict(D1=d1, D2=d2, D3=d3)


def read_c(reader: BinaryReader):
    c1 = reader.read_uint64()
    c2 = reader.read_uint32()
    c3 = reader.read_int16()
    c4 = [reader.read_uint16(), reader.read_uint16()]
    return dict(C1=c1, C2=c2, C3=c3, C4=c4)


def read_b(reader: BinaryReader):
    b1 = read_array(
        source=reader.source,
        size=reader.read_uint16(),
        address=reader.read_uint32(),
        read=lambda reader: read_c(reader),
        structure_size=18,
    )
    b2 = read_d(reader)
    b3 = reader.read_int8()
    return dict(B1=b1, B2=b2, B3=b3)


def read_a(reader: BinaryReader):
    a1 = reader.read_float()
    a2 = reader.read_uint64()
    a3 = read_b(reader)
    a4 = ''.join(
        read_array(
            source=reader.source,
            size=reader.read_uint32(),
            address=reader.read_uint16(),
            read=lambda reader: reader.read_char().decode('ascii')
        )
    )
    a5 = read_e(reader)
    return dict(A1=a1, A2=a2, A3=a3, A4=a4, A5=a5)


def main(source):
    reader = BinaryReader(source)
    reader.read('cccc')
    return read_a(reader)
```
