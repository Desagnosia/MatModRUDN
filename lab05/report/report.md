---
title: "Лабораторная работа №5"
subtitle: "Математическое моделирование"
author: "Юхнин Илья Андреевич"
lang: ru-RU
toc-title: "Содержание"
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl
toc: true 
toc_depth: 2
lof: true 
lot: true 
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text

---



# Цель работы

Рассмотреть простейшую модель взаимодействия двух видов типа «хищник — жертва» — модель **Лотки-Вольтерры**. Построить модель и визуализировать фазовые портреты.

# Задание
Вариант 47

В лесу проживают $х$ число волков, питающихся зайцами, число которых в этом же лесу $у$. Пока число зайцев достаточно велико, для прокормки всех волков, численность волков растет до тех пор, пока не наступит момент, что корма перестанет хватать на всех. Тогда волки начнут умирать, и их численность будет уменьшаться. В этом случае в какой-то момент времени численность зайцев снова начнет увеличиваться, что повлечет за собой новый рост популяции волков. Такой цикл будет повторяться, пока обе популяции будут существовать. Помимо этого, на численность стаи влияют болезни и старение. 

Для модели «хищник — жертва»:

$$\begin{cases} \frac{dx}{dt} = -0.7x(t) + 0.044x(t)y(t) \\ \frac{dy}{dt} = 0.6y(t) - 0.022x(t)y(t) \end{cases}$$

Постройте график зависимости численности хищников от численности жертв, а также графики изменения численности хищников и численности жертв при следующих начальных условиях: $x_0 = 6$, $y_0 = 19$. Найдите стационарное состояние системы.

# Теоретическое введение

Данная двувидовая модель основывается на следующих предположениях: 

1. Численность популяции жертв x и хищников y зависят только от времени (модель не учитывает пространственное распределение популяции на занимаемой территории).
2. В отсутствии взаимодействия численность видов изменяется по модели Мальтуса, при этом число жертв увеличивается, а число хищников падает.
3. Естественная смертность жертвы и естественная рождаемость хищника считаются несущественными.
4. Эффект насыщения численности обеих популяций не учитывается. 
5. Скорость роста численности жертв уменьшается пропорционально численности хищников.

$$\begin{cases}\frac{dx}{dt} = ax(t) - bx(t)y(t) \\ \frac{dy}{dt} = -cy(t) + dx(t)y(t)\end{cases}\;\;\;\;(1)$$       

В этой модели:

- $x$ — число жертв. 
- $y$ — число хищников. 
- $a$ — коэффициент, который описывает скорость естественного прироста числа жертв в отсутствие хищников.
- $с$ — коэффициент, который описывает естественное вымирание хищников, лишенных пищи в виде жертв.  
- $b$ — коэффициент, который уменьшает популяцию жертв при каждом акте взаимодействия.
- $d$ — коэффициент, который увеличивает популяцию хищников при каждом акте взаимодействия.

Математический анализ этой (жесткой) модели показывает, что имеется стационарное состояние $A$, всякое же другое начальное состояние $B$ приводит к периодическому колебанию численности как жертв, так и хищников, так что по прошествии некоторого времени система возвращается в состояние $B$.

# Выполнение лабораторной работы

1. Код программы с комментариями:

   ```
   model lab5
     constant Real a = 0.7; 
     constant Real b = 0.044; 
     constant Real c = 0.6; 
     constant Real d = 0.022; 
     Real x; // число хищников
     Real y; // число жертв
   initial equation
     x = 6;
     y = 19; 
   equation
     der(x)=-a*x+b*x*y;
     der(y)=c*y-d*x*y;
   end lab5;
   ```

2. График изменения численности хищников от изменения численности жертв (рис. [-@fig:003]):
   
   ![Рис. 1: Зависимости численности хищников от изменения численности жертв](img/1.png)
   


3. График изменения численности хищников и численности жертв от времени (рис. [-@fig:004]):

   ![Рис. 2: Зависимости изменения численности хищников и жертв от времени](img/2.png)


# Выводы

Благодаря данной лабораторной работе познакомился с простейшей моделью взаимодействия двух видов типа "хищник-жертва" - моделью **Лотки-Вольтерры**, а именно научился:

- строить модель "хищник-жертва".
- строить фазовые портреты системы "хищник-жертва".
- находить стационарное состояние системы "хищник-жертва".


# Список литературы

- <code>[Кулябов Д.С. *Лабораторная работа №5*](https://esystem.rudn.ru/mod/resource/view.php?id=831045)</code>
- <code>[Кулябов Д.С. *Задания к лабораторной работе №5 ( по вариантам )*](https://esystem.rudn.ru/mod/resource/view.php?id=831046)</code>