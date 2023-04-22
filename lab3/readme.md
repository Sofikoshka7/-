# Третья практическая работа по ТМП

## Выполнила: Семёнова С.А. БИСО-03-20

Стратегия:
```
import random
from abc import ABC, abstractmethod

class Variant(ABC):
    @abstractmethod
    def selection(self) -> None:
        pass
class one(Variant):
    def selection(self) -> str:
        return "один"
class two(Variant):
    def selection(self) -> str:
        return "два"
class three(Variant):
    def selection(self) -> str:
        return "три"
class four(Variant):
    def selection(self) -> str:
        return "четыре"
class five(Variant):
    def selection(self) -> str:
        return "пять"
class Random(Variant):
    def selection(self) -> str:
        options = [ "один", "два", "три", "четыре", "пять"]
        return random.choice(options)

class Game:
    strategy: Variant
    def __init__(self, strategy: Variant = None) -> None:
        if strategy is not None:
            self.strategy = strategy
        else:
            self.strategy = Random()
    def play(self, sec2) -> None:
        s1 = self.strategy.selection()
        s2 = sec2.strategy.selection()
        if s1 == s2:
            print("ничья!")
        elif s1 == "один":
            if s2 == "два":
                print("побеждает второй игрок!", s1, '<', s2)
            elif s2 == ("три"):
                print("побеждает второй игрок!", s1, '<', s2)
            elif s2 == ("четыре"):
                print("побеждает второй игрок!", s1, '<', s2)
            elif s2 == ("пять"):
                print("Побеждает второй игрок!", s1, '<', s2)
        elif s1 == "два":
            if s2 == "один":
                print("побеждает первый игрок!", s1, '>', s2)
            elif s2 == ("три"):
                print("побеждает второй игрок!", s1, '<', s2)
            elif s2 == ("четыре"):
                print("побеждает второй игрок!", s1, '<', s2)
            elif s2 == ("пять"):
                print("побеждает второй игрок!", s1, '<', s2)
        elif s1 == "три":
            if s2 == "один":
                print("побеждает первый игрок!", s1, '>', s2)
            elif s2 == ("два"):
                print("побеждает первый игрок!", s1, '>', s2)
            elif s2 == ("четыре"):
                print("побеждает второй игрок!", s1, '<', s2)
            elif s2 == ("пять"):
                print("Побеждает второй игрок!", s1, '<', s2)
        elif s1 == "четыре":
            if s2 == "один":
                print("побеждает первый игрок!", s1, '>', s2)
            elif s2 == ("два"):
                print("побеждает первый игрок!", s1, '>', s2)
            elif s2 == ("три"):
                print("побеждает первый игрок!", s1, '>', s2)
            elif s2 == ("пять"):
                print("побеждает второй игрок!", s1, '<', s2)
        elif s1 == "пять":
            if s2 == "один":
                print("побеждает первый игрок!", s1, '>', s2)
            elif s2 == ("два"):
                print("побеждает первый игрок!", s1, '>', s2)
            elif s2 == ("три"):
                print("побеждает первый игрок!", s1, '>', s2)
            elif s2 == ("четыре"):
                print("побеждает первый игрок!", s1, '>', s2)
def playtime(vibor):
    if vibor == "один":
        return Game(one())
    elif vibor == "два":
        return Game(two())
    elif vibor == "три":
        return Game(three())
    elif vibor == "четыре":
        return Game(four())
    elif vibor == "пять":
        return Game(five())
    elif vibor == "случайно":
        return Game(Random())
n=1
while n==1:
    print("первый игрок:\nсделайте выбор: один, два, три, четыре, пять, случайно")
    vibor=input()
    while vibor not in ("один", "два", "три", "четыре", "пять", "случайно"):
        print("повторите ввод")
        vibor=input()
    player1 = playtime(vibor)
    
    print("второй игрок:\nсделайте выбор: один, два, три, четыре, пять, случайно")
    vibor = input()
    while vibor not in ("один", "два", "три", "четыре", "пять", "случайно"):
        print("повторите ввод")
        vibor=input()
    player2 = playtime(vibor)
    player1.play(player2)
    print("желаете повторить? 1-да")
    n=int(input())
print("конец!")
```
![alt text](https://github.com/Sofikoshka7/TMP/blob/main/lab3/Screenshot_2.png)


Шаблонный метод:
```
from abc import ABC, abstractmethod


class Algorithm(ABC):

    def template_method(self):

        self.flagstock()
        self.draw_1()
        self.draw_2()
        self.draw_3()
        self.final()
        self.printer()

    def flagstock(self):
        print("Флагшток нарисован")

    @abstractmethod
    def draw_1(self):
        pass

    @abstractmethod
    def draw_2(self):
        pass

    @abstractmethod
    def draw_3(self):
        pass

    def final(self):
        print('Флаг готов!')

    def printer(self):
        n = 50
        print("-" * n)

class colors:
    def painwhitef(self):
        print("белый фон нарисован")

    def painredf(self):
        print("красный фон нарисован")

    def painbluef(self):
        print("синий фон нарисован")

    def painyellowf(self):
        print("жёлтый фон нарисован")

    def painwhitek(self):
        print("белый крест нарисован")

    def painbluek(self):
        print("синий крест нарисован")

    def painyellowk(self):
        print("жёлтый крест нарисован")

    def painredk(self):
        print("красный крест нарисован")

    def painwhiteo(self):
        print("белая окантовка креста нарисована")

    def painblueo(self):
        print("синяя окантовка креста нарисована")

    def painyellowo(self):
        print("жёлтая окантовка креста нарисована")

    def painredo(self):
        print("красная окантовка креста нарисована")

    def painnoo(self):
        print("у креста нет окантовки")


class NorwayFlag(Algorithm):
    def draw_1(self):
        z = colors()
        z.painredf()

    def draw_2(self):
        z = colors()
        z.painbluek()

    def draw_3(self):
        z = colors()
        z.painwhiteo()

    def final(self):
        print('Флаг Норвегии готов!')

class SwedenFlag(Algorithm):
    def draw_1(self):
        z = colors()
        z.painbluef()

    def draw_2(self):
        z = colors()
        z.painyellowk()

    def draw_3(self):
        z = colors()
        z.painnoo()

    def final(self):
        print('Флаг Швеции готов!')

class IslandFlag(Algorithm):
    def draw_1(self):
        z = colors()
        z.painbluef()

    def draw_2(self):
        z = colors()
        z.painredk()

    def draw_3(self):
        z = colors()
        z.painwhiteo()

    def final(self):
        print('Флаг Исландии готов!')

print("Рисуем флаг Норвегии")
a=NorwayFlag()
a.template_method()

print("Рисуем флаг Швеции")
b=SwedenFlag()
b.template_method()

print("Рисуем флаг Исландии")
c=IslandFlag()
c.template_method()
```
![alt text](https://github.com/Sofikoshka7/TMP/blob/main/lab3/Screenshot_3.png)
