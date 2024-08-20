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

