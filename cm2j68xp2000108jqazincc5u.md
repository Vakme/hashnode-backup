---
title: "Badge: Pochwal się przed światem, że ci działa!"
datePublished: Tue Nov 20 2018 12:35:36 GMT+0000 (Coordinated Universal Time)
cuid: cm2j68xp2000108jqazincc5u
slug: badge-pochwal-sie-przed-swiatem-ze-ci-dziala
canonical: https://basement-code.pl/2018/11/badge-pochwal-sie-przed-swiatem-ze-ci-dziala/
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1729524525455/b927b2d8-0db2-413c-91a4-f01c09adda19.png
tags: github, cicd, geeklife, badge, shield

---

Wiemy, dawno nie pisaliśmy. Dopadły nas studia. Tymczasem licznik polubień na Facebooku powolutku, acz stale się _inktrementował_. Postanowiliśmy – tak nie może być! Trzeba dokończyć te wszystkie rozpoczęte szkice. A w międzyczasie postanowiliśmy podrzucić wam ciekawostkę, która wzbogaci wasze publiczne repozytoria. Dobrej zabawy!

* * *

Na pewno kiedyś je widzieliście. Znajdują się w README w każdym profesjonalnym repozytorium. Stanowią gwarancję jego profesjonalizmu i wskazują na jakość znajdującego się tam kodu. Abyście nie musieli domyślać się, o co chodzi, oto i one:

![badge vue.js](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524479373/ebbc3023-7d47-4a65-b0ac-0c79589d42ca.png)

Tak wygląda fragment README repozytorium [Vue.js](https://github.com/vuejs/vue). Znajdują się na nim tak zwane badge, z których możemy odczytać między innymi, że:

*   **projekt działa**: _build passing_ pokazuje pozytywny stan najnowszego buildu. Stan ten pobierany jest z narzędzia do CI/CD. Po najechaniu na badge widzimy, że twórcy Vue używają [CircleCI](https://circleci.com/)
*   **kod jest naprawdę dobrze pokryty testami**: 99% funkcjonalności jest przetestowane. Również możemy sprawdzić użyte do tego narzędzie: [codecov.io](https://codecov.io/)
*   **Vue jest popularny**: 2 miliony pobrań w miesiącu. Łał. Serio, łał.
*   **jest na bieżąco aktualizowany** w repozytorium NPM-a
*   jest tworzony na [**licencji MIT**](https://opensource.org/licenses/mit-license.php)
*   w razie problemów i pytań możemy pogadać na specjalnym tematycznym **Discordzie**
*   **testy _cross-browser_ przechodzą** – status z [Sauce Labs](https://saucelabs.com/) świeci się na zielono

#### No fajnie, mogę sobie pokazać, że mój build przechodzi, ale chce mi się za każdym razem zmieniać takiego obrazka.

No, nie.

Badge są powiązane z konkretną usługą i zmieniają swój wygląd automatycznie. Przykładowo: badge pokazujący, czy dana strona jest online, czy nie, ma status:

*   dla BC (musi mieć, skoro to czytasz): ![Website](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524481648/493a9af1-6269-4504-bd45-55bae62bd79c.svg)
*   dla mojego starego, nieistniejącego już bloga [femdev.pl](https://femdev.pl): ![Website](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524493072/9a9d1ae6-1631-44c0-b451-7bee0126f3fb.svg)

#### No dobrze, super, że wielcy świata kodu mają takie znaczki, ale jak to się ma do moich projektów? Nie współtworzę Open Source, moje repozytoria są malutkie. Nie potrzebuję chwalić się swoim kodem.

Też nie.

Wysoki code coverage oraz znajomość CI/CD to umiejętności niezbędne w pracy programisty. Podobnie znajomość licencji. Badge stanowią potwierdzenie twojej znajomości dobrych praktyk. Kod tylko dla siebie? Też tak myślałam, dopóki nie zaczęłam dostawać gwiazdek na Githubie od kompletnie obcych ludzi.

To skoro wątpliwości mamy z głowy, możemy przejść do sedna.

Jak mogę umieścić badge w swoim repo?
-------------------------------------

Wiele usług, na przykład CircleCI, udostępnia kod badge do ściągnięcia. Dla przykładu, badge ukazujący najnowszy stan mojego projektu [dragomon](https://github.com/Vakme/dragomon):

![CircleCI](https://circleci.com/gh/Vakme/dragomon.svg?style=svg)

    [![CircleCI](https://circleci.com/gh/Vakme/dragomon.svg?style=svg)](https://circleci.com/gh/Vakme/dragomon)
    

Jednakże, najpopularniejszymi _badżami_ używanymi w sieci są te ze [Shields.io](https://shields.io/). Znajdziemy tam do dyspozycji setki przykładów w wielu stylach. Poniżej kod na kilka z nich:

*   Znacznik stanu buildu na CircleCI (to samo, co wyżej, tylko w wersji Shields.io): ![CircleCI (all branches)](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524495548/96916c1e-3d20-44d9-b13d-231a04606f89.svg)
    
        ![CircleCI (all branches)](https://img.shields.io/circleci/project/:platforma:/:użytkownik:/:repozytorium:.svg)
    
*   Podziękuj mi (wymaga konta na [saythanks](https://saythanks.io/)): [![saythanks](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524497281/e5d27bc5-0f80-447f-bda8-158b9e59b938.svg)](https://saythanks.io/to/vakme)
    
        [![saythanks](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524497963/219edc7c-4a17-4e77-aed9-3c3628e7f267.svg)](https://saythanks.io/to/:użytkownik:)
    
*   Typ licencji (Github): ![GitHub](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524498872/c0d1a82d-6bde-45ec-9860-0275dc78d0c6.svg)
    
        ![GitHub](https://img.shields.io/github/license/:użytkownik:/:repozytorium:.svg)
    
    `   `
    
*   Ilość zamkniętych pull requestów: ![GitHub closed pull requests](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524501470/161c688b-4a39-45fc-bbea-0512d7b5c2d9.svg)
    
        ![GitHub closed pull requests](https://img.shields.io/github/issues-pr-closed/:użytkownik:/:repozytorium:.svg)
    
    `   `
    

Jak widzicie, format jest prosty do zastosowania. Czasem tylko wymagana jest integracja z odpowiednią usługą. Takich badży jest mnóstwo i osobiście zachęcam do eksploracji Shields.io. Najpopularniejsze możecie też znaleźć [tutaj](https://devhints.io/badges) i [tutaj](https://github.com/Naereen/badges).

Możecie również przedstawić historyczny stan waszej aplikacji, chociaż już bardziej w formie widgetu niż badge, dzięki usłudze [BuildStats.info](https://buildstats.info/). Przykładowo status z CircleCI dla dragomona:

![enter image description here](https://buildstats.info/circleci/chart/Vakme/dragomon)

    https://buildstats.info/:platforma:/chart/:użytkownik:/:repozytorium:
    

Istnieją również epickie badge z [ForTheBadge.com](https://forthebadge.com/) (dostępne również jako styl na Shields.io). Przykładowe:

![Build with <3](https://forthebadge.com/images/badges/built-with-love.svg)

![Uses cat gifs](https://forthebadge.com/images/badges/contains-cat-gifs.svg)

![Uses badges](https://forthebadge.com/images/badges/uses-badges.svg)

![Made with Vue](https://forthebadge.com/images/badges/made-with-vue.svg)

![You didn't ask for this](https://forthebadge.com/images/badges/you-didnt-ask-for-this.svg)

I z dedykacją dla Dominiki:

![Compatibility Club Penguin](https://forthebadge.com/images/badges/compatibility-club-penguin.svg)

Czy mogę stworzyć własny badge?
-------------------------------

Tak, na przykład poprzez [Shields.io](https://shields.io/#/). Zarówno statyczny, jak i dynamiczny. Wzór na badge statyczne jest stosunkowo prosty:

    https://img.shields.io/badge/<SUBJECT>-<STATUS>-<COLOR>.svg
    

Przykładowe badge BC(do dowolnego użytku!):

![Created by BC](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524520776/1b6fe18a-d725-4d53-b073-5062fd1a3681.svg) ![Approved by BC](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524521980/7a100519-40db-4e3b-b7de-54cc668468f6.svg) ![Rejected by BC](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524523034/ea0ae2c0-fb99-4805-b3be-89b3819eae7e.svg)

Oprócz tego, możecie zmieniać parametry istniejących już badży, dodając w query stringu (po `?` i oddzielone `&`) do adresu obrazka odpowiednie wartości:

*   styl: `style=[plastic|flat|flat-square|for-the-badge|popout|popout-square|social]`
*   tekst: `label=healthinesses` (spacje i znaki specjalne wymagają [kodowania procentowego](https://developer.mozilla.org/en-US/docs/Glossary/percent-encoding))
*   dodanie logo: `logo=github`
*   zmiana koloru: `colorA=ff0000`, `colorB=ffff00`

* * *

Na dziś tyle z mojej strony. Jeszcze raz zachęcam was do szperania po Shields.io. Mam nadzieję, że będziecie się bawić przy tym równie dobrze jak ja. Jeśli chcecie poznać możliwości CircleCI i dowiedzieć się więcej o CI/CD, dajcie znać w komentarzach.

Zostawiam was z epickim badgem w stylu ForTheBadge i do następnego!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729524524122/63e2c461-8d21-42ea-bb75-e7e932521fb5.svg)

Artykuł [Badge: Pochwal się przed światem, że ci działa!](https://basement-code.pl/2018/11/badge-pochwal-sie-przed-swiatem-ze-ci-dziala/) pochodzi z serwisu [BasementCode](https://basement-code.pl).