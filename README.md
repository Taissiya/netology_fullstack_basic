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



  Задание 1
Дан список с визитами по городам и странам. Напишите код, который возвращает отфильтрованный список geo_logs, содержащий только визиты из России."
geo_logs = [
    {'visit1': ['Москва', 'Россия']},
    {'visit2': ['Дели', 'Индия']},
    {'visit3': ['Владимир', 'Россия']},
    {'visit4': ['Лиссабон', 'Португалия']},
    {'visit5': ['Париж', 'Франция']},
    {'visit6': ['Лиссабон', 'Португалия']},
    {'visit7': ['Тула', 'Россия']},
    {'visit8': ['Тула', 'Россия']},
    {'visit9': ['Курск', 'Россия']},
    {'visit10': ['Архангельск', 'Россия']}
]


geo_logs = [geo for geo in geo_logs for value in geo.values() if value[1] == 'Россия']
print(geo_logs)

Задание 2
Выведите на экран все уникальные гео-ID из значений словаря ids.
Т.е. список вида [213, 15, 54, 119, 98, 35]

ids = {'user1': [213, 213, 213, 15, 213],
       'user2': [54, 54, 119, 119, 119],
       'user3': [213, 98, 98, 35]}


set_a = set(ids.get('user1'))
set_b = set(ids.get('user2'))
set_c = set(ids.get('user3'))
set_d = set_a | set_b | set_c
print(set_d)

Задание 3
Дан список поисковых запросов. Получить распределение количества слов в них. Т.е. поисковых запросов из одного - слова 5%, из двух - 7%, из трех - 3% и т.д.
from collections import Counter

queries = [
  'смотреть сериалы онлайн',
  'новости спорта',
  'афиша кино',
  'курс доллара',
  'сериалы этим летом',
  'курс по питону',
  'сериалы про спорт'
  ]

word_count = [len(query.split()) for query in queries]
print (word_count)

word_count_distribution = Counter(word_count)
print (word_count_distribution)

total_queries = len(queries)
for count, num_queries in word_count_distribution.items():
  percentage = (num_queries / total_queries) * 100
  print(f'Запросов из {count} слов: {percentage:.2f}%')

  Задание 4
Дана статистика рекламных каналов по объемам продаж.
Напишите скрипт, который возвращает название канала с максимальным объемом.
Т.е. в данном примере скрипт должен возвращать 'yandex'.

stats = {'facebook': 55, 'yandex': 120, 'vk': 115, 'google': 99, 'email': 42, 'ok': 98}

max_stat = max(stats, key=stats.get)
print(max_stat)


Домашнее задание к лекции 5.«Функции — использование встроенных и создание собственных»
Я работаю секретарем и мне постоянно приходят различные документы. Я должен быть очень внимателен чтобы не потерять ни один документ. Каталог документов хранится в следующем виде:

      documents = [
        {"type": "passport", "number": "2207 876234", "name": "Василий Гупкин"},
        {"type": "invoice", "number": "11-2", "name": "Геннадий Покемонов"},
        {"type": "insurance", "number": "10006", "name": "Аристарх Павлов"}
      ]
Перечень полок, на которых находятся документы хранится в следующем виде:

      directories = {
        '1': ['2207 876234', '11-2'],
        '2': ['10006'],
        '3': []
      }
Задача №1
Необходимо реализовать пользовательские команды, которые будут выполнять следующие функции:

p – people – команда, которая спросит номер документа и выведет имя человека, которому он принадлежит;
s – shelf – команда, которая спросит номер документа и выведет номер полки, на которой он находится;
Правильно обработайте ситуации, когда пользователь будет вводить несуществующий документ.
l– list – команда, которая выведет список всех документов в формате passport "2207 876234" "Василий Гупкин";
a – add – команда, которая добавит новый документ в каталог и в перечень полок, спросив его номер, тип, имя владельца и номер полки, на котором он будет храниться. Корректно обработайте ситуацию, когда пользователь будет пытаться добавить документ на несуществующую полку.
Внимание: p, s, l, a - это пользовательские команды, а не названия функций. Функции должны иметь выразительное название, передающие её действие.


documents = [
    {"type": "passport", "number": "2207 876234", "name": "Василий Гупкин"},
    {"type": "invoice", "number": "11-2", "name": "Геннадий Покемонов"},
    {"type": "insurance", "number": "10006", "name": "Аристарх Павлов"}
]

directories = {
    '1': ['2207 876234', '11-2'],
    '2': ['10006'],
    '3': []
}

def getPeopleByNum(number):
    for doc in documents:
        if doc["number"] == number:
            print(doc["name"])
            return
    print("Документ не найден")

def getShieldNumByNum(number):
    for shelf, numbers in directories.items():
        if number in numbers:
          print(shelf)
          return
    print("Документ на найден на полках")

def getAllDocs():
    for document in documents:
      value = list(document.values())
      formatted_string = f"{value[0]}, '{value[1]}' '{value[2]}'"
      print(formatted_string)
      return
    print("У вас нет документов на полках")

def addDoc(number, doc_type, doc_name, folder_number):
    new_document = {
        "type": doc_type,
        "number": number, 
        "name": doc_name
    }
    documents.append(new_document)
    directories[folder_number].append(number) 
    return


command = input("Введите команду: ")


if command == 'p':
   number = input("Введите номер документа: ")
   getPeopleByNum(number)
elif command == 's':
     number = input("Введите номер документа: ")
     getShieldNumByNum(number)
elif command == 'l':
     getAllDocs()
if command == 'a':
    number = input("Введите номер документа: ")
    doc_type = input("Введите тип документа: ")
    doc_name = input("Введите наименование документа: ")
    folder_number = input("Введите номер папки: ")

    if folder_number not in directories.keys():
        print('Неверный номер папки')
    else:
        addDoc(number, doc_type, doc_name, folder_number)
else:
    print('Неверная команда')

