# Задание 2

## Шаг 1. Импортируйте необходимые библиотеки

```python
import pandas as pd
```

## Шаг 2. Импортируйте набор данных с этого [адреса](https://raw.githubusercontent.com/guipsamora/pandas_exercises/master/02_Filtering_%26_Sorting/Euro12/Euro_2012_stats_TEAM.csv)

```python
tmp = pd.read_csv('https://raw.githubusercontent.com/guipsamora/pandas_exercises/master/02_Filtering_%26_Sorting/Euro12/Euro_2012_stats_TEAM.csv')
```

## Шаг 3. Сохраните его в переменной с именем euro12

```python
euro12 = tmp
del tmp
```

## Шаг 4. Выведите только столбец Goal

```python
print(euro12['Goals'])
```

```txt
0      4
1      4
2      4
3      5
4      3
5     10
6      5
7      6
8      2
9      2
10     6
11     1
12     5
13    12
14     5
15     2
Name: Goals, dtype: int64
```

## Шаг 5. Как много команд участовало в Euro2012?

```python
print(len(euro12['Team']))

# или:
# print(len(euro12))
# print(len(euro12.index))
# print(euro12.shape[0])
```

```txt
16
```

## Шаг 6. Сколько столбцов в наборе данных?

```python
print(len(euro12.keys()))

# или:
# print(len(euro12.dtypes))
```

```txt
35
```

## Шаг 7. Столбцы Team, Yellow Cards и Red Cards сохранить в dataframe. Переменную назвать discipline

```python
discipline = pd.DataFrame({
    "Team": euro12["Team"],
    "Yellow Cards": euro12["Yellow Cards"],
    "Red Cards": euro12["Red Cards"]
})
```

## Step 8. Отфильтровать только команды, которые забили больше 6 голов

```python
print(
    euro12.loc[euro12["Goals"] > 6]["Team"]
)

# если надо вывести все данные этих команд:
# print( euro12.loc[euro12["Goals"] > 6] )
```

```txt
5     Germany
13      Spain
Name: Team, dtype: object
```
