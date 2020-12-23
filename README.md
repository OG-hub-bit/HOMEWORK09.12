# HOMEWORK16.12

def ex1(point1, point2):
    assert type(point1) == tuple or type(point2) == tuple, "не правильный тип входных данных"
    assert type(point1[0]) == (int or float) and type(point1[1]) == (int or float), "неправильный тип данных второй точки"
    assert type(point2[0]) == (int or float) and type(point2[1]) == (int or float), "неправильный тип данных второй точки"
    assert len(point1) == 2 and len(point2) == 2, "неправильная длина картежа" 
    k = (point2[1] - point1[1]) / (point2[0] - point1[0])
    b = (point1[0] * point2[1] - point2[0] * point2[1]) / (point2[0] - point1[0])
    if b > 0:
        return f"y = {k}x + {b}"
    else:
        return f"y = {k}x + {-b}"

def ex2(p, n, Boolean = False, ms = None):    
    if type(Boolean) == int:
        ms = Boolean
        Boolean = False
    assert type(ms) == int, "Недостаточно данных"
    try:
        if Boolean:
            return (12 * ms * (1 + p) ** (n - 1)) / (p * (1 + p) ** n)
        else:
            return (ms * p * (1 + p) ** n) / (12 * (1 + p) ** (n - 1))
    except TypeError:
        return "некорректный ввод данных"

def ex3_1(lst1, lst2):
    lst3 = []
    for i in lst1:
        if i in lst2:
            lst3.append(i)
    return lst3
    
def ex3_2(lst1, lst2):
    lst3 = [i for i in lst1 if i in lst2]
    return lst3

ex3_3 = lambda lst1, lst2: [i for i in lst1 if i in lst2]

def ex4(string):
    lst = sorted(string.split(), key=lambda s: len(s))
    resault = ""
    for i in lst:
        resault += i + " "
    return resault[:-1]

ex5 = lambda lst: {i: lst.count(i)  for i in set(lst) if lst.count(i) > 1}

print(ex1((2, 1), (1, 0)))
y = 1.0x + 0.0
