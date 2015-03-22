# Vim

cheatsheet -> http://www.viemu.com/vi-vim-cheat-sheet.gif

## Super extra mega pluginy
https://github.com/carlhuda/janus

ja dodatkowo instaluje sobie temacik monokai

`git clone https://github.com/sickill/vim-monokai ~/.janus/`

## O co loto?
Na vim trzeba patrzeć jak na jezyk, podstawą jest poznanie normal mode,
gdyż większość czasu właśnie w nim się spędza.

# Motion
Wyedytujmy pierwszy plik `vim 1`

Tutaj poznamy zakres ruchów jakie możemy robić w vim'ie

`M` - środek ekranu

`h` - kursor w lewo

`j` - kursor w dol

`k` - kursor do gory

`l` - kursor w prawo

`L` - koniec ekranu

`H` - początek ekranu

`{` - początek/poprzedni akapit

`}` - koniec/następny akapit

`(` - początek/poprzednie zdanie

`)` - koniec/następne zdanie

`w` `W` - następne słowo

`b` `B` - poprzednie słowo

`e` `E` - koniec słowa

`*` - następne słowo pod kursorem

`#` - poprzednie słowo pod kursorem

`0` - początek linijki

`^` - początek tekstu w linijce

`$` - koniec linijki

`G` - koniec pliku

`gg` - początek pliku

`:q` - wyjście bez zapisu jeśli nie było zmian

`:q!` - wyjście bez zapisu

`:wq` - wyjście z zapisem

`ZQ` - wyjście bez zapisu

`ZZ `- wyjście z zapisem

Spróbujmy nawigować po kodzie i wykorzystajmy wszystkie powyższe komendy
`vim 2`

`gg`

`13gg`

`*`

`*`

`w`

`3*`

`G`

`40gg`

`#`

`2(`

`M`

`{`

`}`

`{`

`{`

`L`

`10B`

`10k`

`3l`

`6k`

`15E`

`e`

`2#`

etc etc etc

akcja w vimie poprzedzona liczbą zostanie powtórzona odpowiednią ilość
razy np:

`10j` - dziesięć linijek w dół

`10k` - dziesięć linijek w górę

`2l` - dwa znaki w prawo

`7h` - siedem znaków w lewo

`4w` - czwarte słowo

`5E` - koniec piątego SŁOWA

`3}` - koniec trzeciego akapitu

ale

`12gg`- przeniesie kursor do odpowiedniej linijki

## Operatory
`y` - kopiuj

`d` - usuń

`c` - change

`<` - indent w lewo

`>` - indent w prawo

powielenie operatora spowoduje wykonanie go na danej linijce

`yy` - kopiuj linjke

`dd` - usun linjke

etc

Zaraz po operatorze używamy motion mówimy co chcemy zrobić np:

`cw` - zamień słowo

`d10gg` - usuń wszystko od tej linijki do 10

`yG` - kopiuj wszystkie linjki stąd do końca pliku

`d$` - usuń znaki od kursora do końca linijki

## Commands
Komenda różni się od operatora, że nie potrzebuje modyfikatora zaraz za
nią

`i` - wbija w tryb insert

`R` - wbija w tryb replace

`x` - usuwa znak (delete)

`X` - usuwa znak poprzedni (backspace)

`I` - insert na początku linii (^i)

`S` - kasuje linijkę i wbija w insert (ddi)

`s` - kasuje znak i wbija w insert (xi)

`A` - idzie na koniec linijki i wbija w tryb insert ($i)

`a` - znak w prawo i insert (li)

`p` - wstawia z bufora linijke niżej

`P` - wstawia z bufora linijke wyżej

`o` - nowa linijka poniżej

`O` - nowa linijka powyżej

`u` - undo

Naciskając `d` vim poczeka na motion, naciskając `x` usunie od razu jeden
znak.

`vim 3`

Możemy wykorzystać naszą wiedzę i zacząć walić kombosy!

Chcemy zmienić słowo Python na np: Java, jest na to wiele

sposobów spróbujemy różnych ucząc sie przy tym kolejnych vimowym zwrotów

`fPRJava<Del><Del><Esc>`

po każdym wykonaniu komend można przywrócić stan pliku z początku
komendą `:e!` lub komendą `u` (undo)

`5ecwJava<Esc>`

`4wdwiJava<Esc>`

`}dbiJava<Esc>`

`f!dbiJava<Esc>`

`29l6xiJava<Esc>`

Przywrócmy stan pierwotny `:e!`

`yy3p` - skopiuje linijke i powieli ją poniżej 3 razy

`d3d` - przesunie 3 linijki do bufora

`p` - wklei zawartość bufora

`.` - powtórzy poprzednią akcję czyli `p`

## SED
