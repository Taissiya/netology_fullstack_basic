# netology_fullstack_basic
Домашнее задание к лекции 2.«Условные конструкции. Операции сравнения»
**Задача №1**
Ипотечный калькулятор В новом банке решили начать выдавать ипотеку. Появилась необходимость разработать для них ипотечный калькулятор. Нужно рассчитать финальную процентную ставку по ипотеке. От каких критериев зависит скидка на ипотеку:

Если клиент из Дальнего Востока(список регионов определить самостоятельно), то базовая ставка становится 2%.
Если количество детей больше 3, то базовая ставка уменьшается на 1%.
Если у клиента зарплатный проект в этом банке, то базовая ставка уменьшается на 0.5%.
Если в этом же банке будет оформлена страхование, то базовая ставка уменьшается на 1.5% Базовую процентную ставку выбрать самостоятельно.
Если клиент оформляет ипотеку по дальневосточной программе, то остальные скидки не применяются.

base_rate = 2
print("Hello!")
zero_condition = (input("Do you want to apply for a Far Eastern program?(yes/no)"))
if zero_condition == 'yes':
  print("Let's do it")
elif zero_condition == 'no':
  first_condition=(input('Are you from the Far East?(yes/no)'))
  if first_condition == 'yes':
    base_rate = 2
  elif first_condition == 'no':
    base_rate = 4
  else:
    print('pls check your answer :(')
  second_condition=(input('Enter the number of your children (0-10)'))
  if int(second_condition) > 3:
    base_rate = base_rate - 1
  third_condition=(input('Do you have any projects in this bank?(yes/no)'))
  if third_condition == 'yes':
    base_rate = base_rate - 0.5
  elif third_condition == 'no':
    base_rate = base_rate
  else: print('pls check your answer :(')
  forth_condition = (input('Do you waht to open insurance account in our bank?(yes/no)'))
  if forth_condition == 'yes':
    base_rate = base_rate - 1.5
  print(f'Ваша процентная ставка = {base_rate}')


  







**Задание №2**
Разработать приложение для определения знака зодиака по дате рождения.

list = ('Козерог', 'Водолей', 'Рыбы', 'Овен', 'Телец', 'Близнецы', 'Рак',
        'Лев', 'Дева', 'Весы', 'Скорпион', 'Стрелец')
list_month = ('январь', 'февраль', 'март', 'апрель', 'май', 'июнь', 'июль',
              'август', 'сентябрь', 'октябрь', 'ноябрь', 'декабрь')

month_of_birth = (input("Введите месяц рождения (март)"))
day_of_birth = (input("Введите день рождения (01)"))

month = list_month.index(month_of_birth)

if month == 0 and int(day_of_birth) < 20:
  print(list[month])

elif month == 0 and int(day_of_birth) >= 20:
  month = month + 1
  print(list[month])

elif month == 1 and int(day_of_birth ) < 20:
  month = month +1
  print(list[month])
elif month == 1 and int(day_of_birth ) >= 20:
  month = month +1
  print(list[month])
  else: print ('Мне надоело дальше писать')



  Задача 1
Мы делаем MVP dating-сервиса, и у нас есть список парней и девушек — их число может варьироваться:

boys = ['Peter', 'Alex', 'John', 'Arthur', 'Richard']
girls = ['Kate', 'Liza', 'Kira', 'Emma', 'Trisha']
Выдвигаем гипотезу: лучшие рекомендации мы получим, если просто отсортируем имена по алфавиту и познакомим людей с одинаковыми индексами после сортировки. «Познакомить» пары нам поможет функция zip. В цикле распакуем zip-объект и выведем информацию в виде:

Идеальные пары:
Alex и Emma
Arthur и Kate
John и Kira
Peter и Liza
Richard и Trisha
Внимание. Если количество людей в списках будет не совпадать, то мы никого знакомить не будем и выведем пользователю предупреждение, что кто-то может остаться без пары.

boys = ['Peter', 'Alex', 'John', 'Arthur', 'Richard']
girls = ['Kate', 'Liza', 'Kira', 'Emma', 'Trisha']
boys.sort()
girls.sort()
if len(boys) == len(girls):
  for boy, girl in zip(boys, girls): 
    print(f'{boy} + {girl}')
    print()
else: 
    print('кто-то может остаться без пары')


Задача 2
Есть структура данных cook_book, в которой хранится информация об ингредиентах блюд и их количестве в расчёте на одну порцию:

cook_book = [
  ['салат',
      [
        ['картофель', 100, 'гр.'],
        ['морковь', 50, 'гр.'],
        ['огурцы', 50, 'гр.'],
        ['горошек', 30, 'гр.'],
        ['майонез', 70, 'мл.'],
      ]
  ],
  ['пицца',  
      [
        ['сыр', 50, 'гр.'],
        ['томаты', 50, 'гр.'],
        ['тесто', 100, 'гр.'],
        ['бекон', 30, 'гр.'],
        ['колбаса', 30, 'гр.'],
        ['грибы', 20, 'гр.'],
      ],
  ],
  ['фруктовый десерт',
      [
        ['хурма', 60, 'гр.'],
        ['киви', 60, 'гр.'],
        ['творог', 60, 'гр.'],
        ['сахар', 10, 'гр.'],
        ['мед', 50, 'мл.'],  
      ]
  ]
]
и переменная, в которой хранится количество людей, на которых нужно приготовить эти блюда:

person = 5
Нужно вывести пользователю список покупок необходимого количества ингредиентов для приготовления блюд на определённое число персон в следующем виде:

Салат:
картофель, 500гр.
морковь, 250гр.
огурцы, 250гр.
горошек, 150гр.
майонез, 350мл.

Пицца:
сыр, 250гр.
томаты, 250гр.
тесто, 500гр.
бекон, 150гр.
колбаса, 150гр.
грибы, 100гр.

Фруктовый десерт:
хурма, 300гр.
киви, 300гр.
творог, 300гр.
сахар, 50гр.
мед, 250мл.
Внимание. Реализация не должна зависеть от количества блюд, их названий и количества ингредиентов в них.

cook_book = [
  ['салат',
      [
        ['картофель', 100, 'гр.'],
        ['морковь', 50, 'гр.'],
        ['огурцы', 50, 'гр.'],
        ['горошек', 30, 'гр.'],
        ['майонез', 70, 'мл.'],
      ]
  ],
  ['пицца',  
      [
        ['сыр', 50, 'гр.'],
        ['томаты', 50, 'гр.'],
        ['тесто', 100, 'гр.'],
        ['бекон', 30, 'гр.'],
        ['колбаса', 30, 'гр.'],
        ['грибы', 20, 'гр.'],
      ],
  ],
  ['фруктовый десерт',
      [
        ['хурма', 60, 'гр.'],
        ['киви', 60, 'гр.'],
        ['творог', 60, 'гр.'],
        ['сахар', 10, 'гр.'],
        ['мед', 50, 'мл.'],  
      ]
  ]
]

person = 5


for dish in cook_book:
  ingredients = dish[1]
  for ingredient in ingredients:
      name = ingredient[0]
      quantity = ingredient[1] * person
      unit = ingredient[2]
      print(f"{name}, {quantity}{unit}")
  


