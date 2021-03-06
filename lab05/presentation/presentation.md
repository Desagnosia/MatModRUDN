---
## Front matter
lang: ru-RU
title: Лабораторная работа №5
author: Юхнин Илья Андреевич
documentclass: article
papersize: a4
toc: false
slide_level: 2
aspectratio: 20
section-titles: true
##Fonts
fontsize: 12pt
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
---







# <p style="text-align: center;">Лабораторная работа №5</p>



**Автор: Юхнин Илья Андреевич**

**Группа: НКНбд-01-19**

<div style="page-break-after: always;">

## Прагматика выполнения

- Знакомство с простейшей моделью взаимодействия двух видов типа «хищник — жертва» — **модель Лотки-Вольтерры**.
- Визуализация результатов моделирования путем построения фазовых портретов и графиков.
  </div>

  <div style="page-break-after: always;">

## Goal


- Построить график зависимости численности хищников от численности жертв

- Построить графики изменения численности хищников и численности жертв при заданных начальных условиях

- Получение новых знаний в ходе выполнения лабораторной работы</div>

  <div style="page-break-after: always;">

## Модель Лотки-Вольтерры

 - Модель Лотки-Вольтерры — модель взаимодействия двух видов типа «хищник — жертва», названная в честь её авторов, которые предложили модельные уравнения независимо друг от друга. Такие уравнения можно использовать для моделирования систем «хищник — жертва», «паразит — хозяин», конкуренции и других видов взаимодействия между двумя видами.</div> 

  <div style="page-break-after: always;">

## Задание

- В лесу проживают $х$ число волков, питающихся зайцами, число которых в этом же лесу $у$. Пока число зайцев достаточно велико, для прокормки всех волков, численность волков растет до тех пор, пока не наступит момент, что корма перестанет хватать на всех. Тогда волки начнут умирать, и их численность будет уменьшаться. В этом случае в какой-то момент времени численность зайцев снова начнет увеличиваться, что повлечет за собой новый рост популяции волков. Такой цикл будет повторяться, пока обе популяции будут существовать. Помимо этого, на численность стаи влияют болезни и старение. 

Для модели «хищник — жертва»:

$$\begin{cases} \frac{dx}{dt} = -0.7x(t) + 0.044x(t)y(t) \\ \frac{dy}{dt} = 0.6y(t) - 0.022x(t)y(t) \end{cases}$$

Постройте график зависимости численности хищников от численности жертв, а также графики изменения численности хищников и численности жертв при следующих начальных условиях: $x_0 = 6$, $y_0 = 19$. Найдите стационарное состояние системы.</div>

  <div style="page-break-after: always;">

## Результат лабораторной работы


 - Научились строить график зависимости численности хищников от численности жертв

 - Научились строить графики изменения численности хищников и численности жертв при заданных начальных условиях 

 - Научились находить стационарное состояние системы

 - Изучили Модель Лотки-Вольтерры
   </div>
  
    <div style="page-break-after: always;">
    
   
    
   
    
   
  
    ### <p style="text-align: center;">Спасибо за внимание!</p></div>