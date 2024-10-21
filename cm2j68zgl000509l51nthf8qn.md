---
title: "CSS dla początkujących: flexbox"
datePublished: Tue Feb 20 2018 20:42:13 GMT+0000 (Coordinated Universal Time)
cuid: cm2j68zgl000509l51nthf8qn
slug: css-dla-poczatkujacych-flexbox
canonical: https://basement-code.pl/2018/02/css-dla-poczatkujacych-flexbox/
tags: tutorial, flexbox, webdevelopment, css

---

_Ola, opisz flexbox na swoim blogu._

_Napisz coś u siebie o flexboxie._

Kiedy przyznałam się wśród znajomych, że tworzę serię poświęconą CSS-owym sztuczkom, dostałam dużo próśb o to, żeby w najbliższym odcinku pojawił się flexbox. Postanowiłam więc odłożyć na przyszły raz transformacje i animacje i ową prośbę spełnić.

Czym jest flexbox?
------------------

Pełna nazwa to _flexible boxes_. Jest to nowy sposób tworzenia layoutu w CSS3, który pozwala na wygodne i elastyczne zarządzanie elementami na stronie.

No dobra, to niewiele mówi. No to jaśniej:

> Flexbox wyróżnia podział elementów na stronie na pojemniki (_containers_), w obrębie których znajdują się elementy (_items_). Pozwala na formatowanie zarówno kontenerów, jak i pojedynczych itemów, ustawianie kolumn, wierszy, rozmieszczenia… Dzięki temu możemy dowolnie rozmieszczać elementy na stronie i tworzyć choćby system kafelków.

W porównaniu do używania _float_ (`#Titanic { float: none; }` hue hue hue) czy nawet niezbędnych w RWD tzw. _media queries_ postęp jest na tyle duży, że na stronach branżowych pojawiało się gdzieniegdzie słowo _rewolucja_.

Flexbox krok po kroku
---------------------

Aby zaprezentować większość możliwości flexboxa, zdecydowałam się na stworzenie układu 4 kolumn.

Najpierw potrzebowałam kontenera z 4 itemami. Ich kod wygląda następująco:

<div class="flex-container">
  <div class="flex-item"></div>
  <div class="flex-item"></div>
  <div class="flex-item"></div>
  <div class="flex-item"></div>
</div>

CSS:

.flex-container {
  background-color: gray;
  padding: 10px;
}
.flex-item {
  width: 50px;
  height: 50px;
  background-color: red;
  border: 1px black solid;
}

Obecnie całość wygląda tak:

.flex-container { background-color: gray; padding: 10px; } .flex-item { width: 50px; height: 50px; background-color: red; border: 1px black solid; }<br />

Niezbyt widowiskowo, prawda? Ponieważ `.flex-item` to elementy typu `<div>` domyślnie będą jeden pod drugim. Nie przypominają kolumn w ogóle.

### 1\. Zmiana kontenera

Zdefiniujmy kontener:

.flex-container {
  background-color: gray;
  padding: 10px;
  display: flex;
}

W ten sposób określiliśmy, że chcemy użyć flexa. Od razu widać zmianę w naszym przykładzie:

.flex1a-container { background-color: gray; padding: 10px; display: flex; } .flex1a-item { width: 50px; height: 50px; background-color: red; border: 1px black solid; }

### 2\. Pozycjonowanie w poziomie

Mamy 4 kolumny, które są skupione z lewej strony (domyślnie). Możemy teraz użyć  `justify-content` do zmiany ich pozycji.

.flex-container {
  ...
  justify-content: flex-end;
}

.flex1aa-container{display:flex;background-color:gray;padding:10px;justify-content:flex-end}.flex1aa-item{width:50px;height:50px;background-color:red;border:1px<br /> black solid}<br />

Wyrównanie do prawej.

.flex-container {
  ...
  justify-content: center;
}

.flex1ab-container{display:flex;background-color:gray;padding:10px;justify-content:center}.flex1ab-item{width:50px;height:50px;background-color:red;border:1px black solid}<br />

Wyśrodkowanie.

.flex-container {
  ...
  justify-content: space-around;
}

.flex1ac-container{display:flex;background-color:gray;padding:10px;justify-content:space-around}.flex1ac-item{width:50px;height:50px;background-color:red;border:1px black solid}<br />

Rozmieszczenie równomierne z dodaniem miejsca wokół skrajnych elementów.

.flex-container {
  ...
  justify-content: space-between;
}

.flex1ad-container{display:flex;background-color:gray;padding:10px;justify-content:space-between}.flex1ad-item{width:50px;height:50px;background-color:red;border:1px black solid}<br />

Rozmieszczenie równomierne z zachowaniem oryginalnego marginesu.

Jak widać, możliwości jest sporo.

### 3\. Pozycjonowanie w pionie grup i pojedynczych elementów

W tym momencie dostrzega się zaletę flexboxa. Jeśli pamiętacie męczenie się z `vertical-align`, które _zazwyczaj_ _działa, ale…_ docenicie łatwość i dowolność, z jaką można ustawiać elementy w kontenerze.

Do wyboru mamy: `align-items`, które rozmieszcza wiersz podobnie jak `justify-content` kolumny, z dodaną możliwością rozciągnięcia zawartości w pionie na cały kontener (+ jest opcja ustawienia elementów zgodnie z linią tekstu wewnątrz, tzw. `baseline`), `align-content`, które działa podobnie, ale dla kilku wierszy (brak efektu dla jednego wiersza) oraz `align-self`, które zastosowane dla poszczególnego elementu lub grupy elementów zmienia ich położenie.

Poniżej kilka przykładów:

.flex-container {
  ...
  align-items: flex-end;
  height: 100px;
}

.flex2aa-container{display:flex;background-color:gray;padding:10px;align-items:flex-end;height:100px}.flex2aa-item{width:50px;height:50px;background-color:red;border:1px black solid}<br />

Wyrównanie wiersza w dół.

.flex-container {
  ...
  align-items: stretch;
  height: 100px;
}
.flex-item {
  width: 50px;  /\* bez wysokości \*/
  background-color: red;
  border: 1px black solid;
}

.flex2ab-container{display:flex;background-color:gray;padding:10px;align-items:stretch;height:100px}.flex2ab-item{width:50px;background-color:red;border:1px black solid}<br />

Rozciągnięcie (bez nie należy określać wysokości)

.flex-container {
  ...
  align-content: center;
  height: 200px;
  flex-wrap: wrap; /\* dodałam łamanie linii, o nim za chwilę \*/
}
.flex-item {
  width: 150px; /\* zwiększyłam ilość i szerokość elementów \*/
  ...
}

.flex2ac-container{display:flex;background-color:gray;padding:10px;align-content:center;height:200px;flex-wrap:wrap}.flex2ac-item{width:150px;height:50px;background-color:red;border:1px black solid}<br />

Wyśrodkowanie kilku wierszy

.flex-container {
  ...
  align-content: space-around;
  height: 200px;
  flex-wrap: wrap;
}
.flex-item {
  width: 150px;
  ...
}

.flex2ad-container{display:flex;background-color:gray;padding:10px;align-content:space-around;height:200px;flex-wrap:wrap}.flex2ad-item{width:150px;height:50px;background-color:red;border:1px black solid}<br />

Rozłożenie wierszy równomiernie

.green-flex { /\* stworzyłam nową klasę i dodałam ją do kilku kwadratów \*/
    background-color: green;
    align-self: flex-start; /\* wyrównanie do góry \*/
}
.blue-flex { /\* stworzyłam nową klasę i dodałam ją do jednego kwadratu \*/
    background-color: blue;
    align-self: center; /\* wyśrodkowanie \*/
}

.green-flex{background-color:green;align-self:flex-start}.blue-flex{background-color:blue;align-self:center}<br />

Pozycjonowanie poszczególnych elementów względem wiersza wyrównanego w dół.

### 4\. Kolejność, orientacja i łamanie linii

Możemy określać kolejność elementów we flexie dodając do nich atrybut `order`. Można używać liczb ujemnych, co jest sporym ułatwieniem.

<br>
<div class="flex-container">
<div class="flex-item">1</div>
<div class="flex-item">2</div>
<div class="flex-item flex-order">3</div>
<div class="flex-item">4</div>
</div>

.flex-order {
    order: -1;
}

.flex-order{order:-1}

1

2

3

4

Kwadraty z ujemną wartością atrybutu będą lądowały na początku.

Dodatkowo mamy wybór, czy chcemy zorientować nasze elementy w poziomie czy w pionie (kolumny). Służy do tego atrybut `flex-direction`. Mamy do wyboru: wiersz, wiersz odwrócony, kolumnę i odwróconą kolumnę. Uwaga: w momencie zmiany kierunku, razem z nim _obracają się_ również pozycje w pionie i w poziomie. Więcej na przykładzie:

.flex-container {
    ...
  flex-direction: column;
  align-items: center;
}

.flex3a-container{display:flex;background-color:gray;padding:10px;flex-direction:column;align-items:center}.flex3a-item{width:50px;height:50px;background-color:red;border:1px black solid}

1

2

3

4

Atrybut, który pozycjonuje wiersze poziomo, zmienia kolumny… pionowo.

Możemy także ustalić, czy chcemy przenosić elementy do następnej linii czy nie (w tym przypadku zostaną one “ściśnięte”, by zmieścić się w jednej linii). Służy do tego `flex-wrap`.

.flex-container {
  ...
  height: 200px;
  flex-wrap: no-wrap; /\* przykład z elementami niemieszczącymi się w jednym wierszu \*/
}
.flex-item {
  width: 150px; 
  ...
}

.flex3ac-container{display:flex;background-color:gray;padding:10px;height:200px;flex-wrap:no-wrap}.flex3ac-item{width:150px;height:50px;background-color:red;border:1px black solid}<br />

Bez łamania linii kolumny zmniejszają się, by dopasować do szerokości kontenera.

.flex-container {
  ...
  height: 200px;
  flex-wrap: wrap; /\* przykład z łamaniem linii \*/
}
.flex-item {
  width: 150px; 
  ...
}

.flex3ad-container{display:flex;background-color:gray;padding:10px;height:200px;flex-wrap:wrap}.flex3ad-item{width:150px;height:50px;background-color:red;border:1px black solid}

Tutaj przejdą do następnego wiersza.

Ponieważ `flex-direction` i `flex-wrap` są używane razem bardzo często, stworzono dla nich specjalny atrybut `flex-flow`.

flex-flow: flex-direction flex-wrap;

### 5\. Wielkość elementu

Często elementy we flexie mają ten sam rozmiar. Co wtedy, jeśli planujemy zrobić trzykolumnowy układ z kilkukrotnie większą kolumną środkową? Możemy użyć kilku poleceń:

*   `flex-grow` określa, ile miejsca _może_ zająć pojedynczy element. Przykładowo, jeśli nadamy itemowi wartość 3, będzie domagał się przynajmniej trzykrotnie większej przestrzeni niż pozostałe itemy w wierszu – czyli w praktyce będzie co najmniej 3 razy większy.

.flex-grow {
    flex-grow: 3;
}

.flex-grow{color:white;text-align:center;flex-grow:3}

„Urośnięty”

*   `flex-shrink` – odwrotność `flex-grow`. Określa zdolność elementu do kurczenia się (w stosunku do pozostałych elementów w wierszu), jeśli to konieczne.

.flex-shrink {
    flex-shrink: 3;
}

.flex-shrink{color:white;text-align:center;flex-shrink:3}.bigflex{width:200px}

„Zmalały”

*   `flex-basis` – nadaje elementom domyślną wartość. Może być to ściśle określona wartość (px, %, em) lub słowo kluczowe.

Podobnie jak w poprzednim punkcie połączono te trzy atrybuty w jeden, określany słowem `flex`.

flex: flex-grow flex-shrink flex-basis;

Podsumowanie
------------

Mam nadzieję, że powyższe przykłady rozjaśnią Wam trochę ideę flexboxa i pomogą, gdy będziecie tworzyć swoje strony internetowe.

Jeśli chcecie poćwiczyć, zapraszam was do zagrania we [Flexbox Froggy](http://flexboxfroggy.com/), a jeśli potrzebujecie więcej przykładów, to CSS Tricks przygotowało [kompletny poradnik](https://css-tricks.com/snippets/css/a-guide-to-flexbox/).

Artykuł [CSS dla początkujących: flexbox](https://basement-code.pl/2018/02/css-dla-poczatkujacych-flexbox/) pochodzi z serwisu [BasementCode](https://basement-code.pl).