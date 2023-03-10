# Анализ и сегментация пользователей регионального банка 

## Цель исследования
Проанализировать клиентов регионального банка и сегментировать их по количеству потребляемых продуктов.

## Данные
В наличии были следующие данные о клиентах банка:
* user_id - уникальный номер клиента
* score - скоринговая оценка клиента
* Age - возраст
* Objects - количество объектов в собственности у клиента
* Products - количество банковских продуктов у клиента
* CreditCard - наличие кредитной карты у клиента (да/нет)
* Loyalty - текущая активность клиента (есть/нет)
* Churn - отток клиента (закрыл свои счета / нет)
* Balance - баланс по счетам клиента
* estimated_salary - заработная плата
* City - город проживания
* Gender - пол

## Этапы исследования
1. Изучение и предобработка данных
2. Исследовательский анализ данных
3. Сегментация клиентов
4. Кластеризация (методом K-means)
5. Статистические гипотезы и их проверка
6. Выводы и предложения по маркетинговой активности

## Выводы

Исходя из средних значений числовых характеристик можно отметить следующие закономерности, которые мы наблюдаем у 'отточных' клиентов:
- более зрелые (средний возраст почти 45 лет против 37 лет у тех, кто остается)
- менее активно пользуются услугами банка (36% активных пользователей против 55% среди тех, кто остается)
- чаще проживают в городе Ростов Великий
- чаще женского пола

### Сегментация пользователей

#### Дерево принятия решений

Последовательность проверки клиентов на возможность 'уйти':

**Возраст клиента меньше или равен 31 году.**

**Если да**, то следующий вопрос касается **количества продуктов: меньше 2 или больше 2**.
- Если два и меньше, то велика вероятность того, что клиент останется в банке.
- Если больше двух, то такой клиент склонен уйти.

**Если нет**, то следующий вопрос касается **текущей активности клиента**.
- Если активности нет, то велика вероятность того, что клиент уйдет.
- Если активность есть, то велика вероятность того, что клиент останется.

#### Сегментация пользователей на основе количества используемых продуктов:
- c 1 продуктом банка (5084 клиента, средний уровень оттока - 27,7%) 
- c 2 продуктами банка (4590 клиентов, минимальный уровень оттока - 7,6%) 
- с несколькими продуктами банка (326 клиентов, высокий уровень оттока - 86%) 

### Статистические гипотезы и их проверка
1. Средний доход клиентов с одним продуктом такой же, как у клиентов с 2 продуктами или клиентов с более 2 продуктами
2. Средний доход клиента, который остается в банке, аналогичен доходу клиента, который уйдет.
3. Доля мужчин, которые остаются в банке выше, чем доля мужчин, которые уходят.<br>
4. Доля женщин, которые уходят из банка выше, чем доля женщин, которые остаются<br>
5. Возраст клиента, который уходит из банка, выше, чем возраст клиента, который останется.
6. Количество продуктов у клиента, который уходит из банка, выше, чем количество продуктов у клиента, который останется.<br>
7. Cкоринговая оценка клиента, который уйдет, будет ниже, чем скоринговая оценка клиента, который останется.
8. Cредняя активность клиента, который уйдет, ниже, чем клиента, который останется.<br>

### Предложения по маркетинговой активности

**Целевая аудитория 1**<br>
- 1 продукт банка
- возраст 38-65 лет
- 0 уровень активности

1) предлагать оформить второй продукт (особенно кредитную карту, если еще нет у клиента)
2) у тех, у кого есть кредитная карта, - стимулировать ее использование: подарки за определенное количество транзакций/сумму, кэш-бек
3) посмотреть у активных зрелых клиентов, какие у них есть особенности использования карты, и предложить акции на этой основе зрелым, но неактивным.

**Целевая аудитория 2**<br>
- 3 и более продуктов банка

1) если большое количество кредитов и клиент выразил желание уйти, то предложить рефинансирование
2) если высокий доход у клиента и мало кредитных продуктов, то предложить интересные условия по вкладам

## Используемые бибилиотеки
pandas, matplotlib, numpy, scipy, seaborn, sklearn
