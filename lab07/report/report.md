---
title: "Лабораторная работа №7"
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

Рассмотреть простейшую модель «эффективность рекламы». Построить модель и визуализировать и анализировать графики эффективности распространения рекламы для трех случаев.

# Задание
Вариант 47

Постройте график распространения рекламы, математическая модель которой описывается следующим уравнением:

    $\frac{dn}{dt} = (0.91+0.00005n(t))(N-n(t))$
    $\frac{dn}{dt} = (0.00001+0.81n(t))(N-n(t))$
    $\frac{dn}{dt} = (0.18t+0.31tn(t))(N-n(t))$

При этом объем аудитории $N = 1940$, в начальный момент о товаре знает $26$ человек. Для случая $2$ определите в какой момент времени скорость распространения рекламы будет иметь максимальное значение.

# Теоретическое введение

Организуется рекламная кампания нового товара или услуги. Необходимо, чтобы прибыль будущих продаж с избытком покрывала издержки на рекламу. Вначале расходы могут превышать прибыль, поскольку лишь малая часть потенциальных покупателей будет информирована о новинке. Затем, при увеличении числа продаж, возрастает и прибыль, и, наконец, наступит момент, когда рынок насытится, и рекламировать товар станет бесполезным.

Предположим, что торговыми учреждениями реализуется некоторая продукция, о которой в момент времени $t$ из числа потенциальных покупателей $N$ знает лишь $n$ покупателей. Для ускорения сбыта продукции запускается реклама по радио, телевидению и других средств массовой информации. После запуска рекламной кампании информация о продукции начнет распространяться среди потенциальных покупателей путем общения друг с другом. Таким образом, после запуска рекламных объявлений скорость изменения числа знающих о продукции людей пропорциональна как числу знающих о товаре покупателей, так и числу покупателей о нем не знающих.

Модель рекламной кампании описывается следующими величинами. Считаем, что
$$
\frac{\partial n}{\partial t}
$$
— скорость изменения со временем числа потребителей, узнавших о товаре и готовых его купить;

t — время, прошедшее с начала рекламной кампании;

n(t)— число уже информированных клиентов. Эта величина пропорциональна числу покупателей, еще не знающих о нем. Это описывается следующим образом:
$$
\alpha_1(t)(N-n(t)) 
$$
N — общее число потенциальных платежеспособных покупателей;
$$
\alpha_1(t)>0
$$
 — характеризует интенсивность рекламной кампании (зависит от затрат на рекламу в данный момент времени).

Помимо этого, узнавшие о товаре потребители также распространяют полученную информацию среди потенциальных покупателей, не знающих о нем (в этом случае работает т.н. сарафанное радио). Этот вклад в рекламу описывается величиной
$$
\alpha_2(t)n(t)(N-n(t))
$$
эта величина увеличивается с увеличением потребителей узнавших о товаре.

Математическая модель распространения рекламы описывается уравнением:
$$
\frac{\partial n}{\partial t} = (\alpha_1(t) + \alpha_2(t)n(t))(N - n(t))
$$

# Выполнение лабораторной работы

Код программы:

**Случай 1: a1>a2**

   ```
model lab07

constant Real N = 1940; 

Real a1; 
Real a2; 
Real n; 

initial equation
n = 26; 

equation
a1 = 0.91; 
a2 = 0.00005; 
der(n) = (a1+a2*n)*(N-n); 

end lab07;

   ```

<figure>
    <img src = img\1.PNG alt = "a1>>a2">
    <figcaption>рис.01</figcaption>
</figure>

**Случай 2: a1<a2**

   ```
model lab07

constant Real N = 1940;

Real a1; 
Real a2; 
Real n;

initial equation n = 26;

equation 
a1 = 0.00001; 
a2 = 0.81; 
der(n) = (a1+a2*n)*(N-n);

end lab07;

   ```

<figure>
    <img src = img\2.PNG alt = "a1<<a2">
    <figcaption>рис.02</figcaption>
</figure>


**Случай 3: a1≈a2**

   ```
model lab07
  constant Real N = 1940; 
  
  Real a1;
  Real a2; 
  Real n; 
  
initial equation
  a1 = 0.5; 
  a2 = 0.3; 
  n = 26;
  
equation
  a1 = 0.18*time;
  a2 = 0.31*time;
  der(n) = (a1+a2*n)*(N-n); 

end lab07;
   ```

<figure>
    <img src = img\3.PNG alt = "a1=a2">
    <figcaption>рис.03</figcaption>
</figure>


**Сравнение эффективности сарафанного радио и платной рекламы**

<figure>
    <img src = img\4.PNG alt = "a1=a2">
    <figcaption>рис.04</figcaption>
</figure>

# Вывод

Рассмотрел модель эффективности рекламы в разных случаях. Сравнил решения, учитывающее вклад только платной рекламы и учитывающее вклад только сарафанного радио.


# Вопросы

Записать модель Мальтуса (дать пояснение, где используется данная модель)
$$
 \frac{\partial N}{\partial t} = rN
$$
где

- N — исходная численность населения,
- r — коэффициент пропорциональности, для которого r = b - d, где
  - b — коэффициент рождаемости
  - d — коэффициент смертности
- t — время.

Модель используется в экологии для расчета изменения популяции особей животных.

Записать уравнение логистической кривой (дать пояснение, что описывает данное уравнение)
$$
\frac{\partial P}{\partial t} = rP(1 - \frac{P}{K})
$$


- r — характеризует скорость роста (размножения)
- K — поддерживающая ёмкость среды (то есть, максимально возможная численность популяции)

Исходные предположения для вывода уравнения при рассмотрении популяционной динамики выглядят следующим образом:

- скорость размножения популяции пропорциональна её текущей численности, при прочих равных условиях;
- скорость размножения популяции пропорциональна количеству доступных ресурсов, при прочих равных условиях. Таким образом, второй член уравнения отражает конкуренцию за ресурсы, которая ограничивает рост популяции.

На что влияет коэффициент 
$$
\alpha_1(t)
$$
**и** 
$$
\alpha_2(t)
$$
 в модели распространения рекламы
$$
\alpha_1(t)
$$
 — интенсивность рекламной кампании, зависящая от затрат
$$
\alpha_2(t)
$$
— интенсивность рекламной кампании, зависящая от сарафанного радио

# Список литературы

- <code>[Кулябов Д.С. *Лабораторная работа №7*](https://esystem.rudn.ru/mod/resource/view.php?id=831053)</code>
- <code>[Кулябов Д.С. *Задания к лабораторной работе №7 ( по вариантам )*](https://esystem.rudn.ru/mod/resource/view.php?id=831054)</code>
