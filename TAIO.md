
### #Język maszyny Turinga
Język MT $M=(Q,\Sigma, \Gamma, \delta, B, F)$ będzie MT, wtedy: $L(M) = \{w \in \Sigma^{*}: q_0 w \to \alpha p \beta : \alpha,\beta \in \Gamma^{*}, p \in F \}$
### #Język #RekurencyjniePrzeliczlny 
Język rekurencyjnie przeliczalny lub język PR to język maszyny Turinga

### #Język #Rekurencyjny 
Język MT, która zatrzymuje się niezależnie od tego czy akceptuje wejście nazywamy językiem rekurencyjnym. 
Tzn. Język L nazywamy rekurencyjnym jeżeli $L=L(M)$ dla pewnej MT takiej, że:
1. Jeżeli $w \in L(M)$ to M akceptuje (więc się zatrzymuje)
2. Jeżeli $w \notin L(M)$ to M w końcu się zatrzyma ale nie w stanie akceptującym

### #Język #Przekątniowy
Język przekątniowy $L_d$ składa się z takich słów - kodów MT, które nie akceptują swojego kodu jako wejścia, tzn. $L_d = \{ w: w\notin L(M(w))\}$

### #Język #Uniwersalny
Język uniwersalny $L_u$ koduje pary $(M, w)$ gdzie $M$ jest MT a $w$ jest słowem akceptowanym przez tę maszynę. (Kodowanie: $kod_M 111 w$)

### #Język #KodówPustych
Język kodów pustych MT akceptujących język pusty, tzn. $L_p = \{ M|L(M)=\emptyset \}$


### #Język #KodówNiePustych
Język kodów MT akceptujących język niepusty nazywamy językiem niepustym, tzn. $L_{np} = \{M|L(M)\neq \emptyset \}$

### #Język #KodówMaszynRekurencyjnych
Język kodów MT akceptujących język rekurencyjny, tzn. $L_r = \{ M|L(M)$ jest rekurencyjny $\}$


### #Język #KodówMaszynNieRekurencyjnych
Język kodów MT akceptujących język nierekurencyjny, tzn. $L_{nr} = \{ M|L(M)$ nie jest rekurencyjny $\}$ 

### #Język Hierarchia
1. Język rekurencyjny
2. Język rekurencyjnie przeliczalny ale nie rekurencyjny
3. Język nie rekurencyjnie przeliczalny

### #Język Dopełnienie
Dopełnieniem języka nazywamy $\bar{L} = \Sigma^{*} `\ L$


## #Język #Twierdzenie

##### #Twierdzenie #Rekurencyjny 
Jeżeli $L$ jest rekurencyjny to $\bar{L}$ jest też rekurencyjny
Dowód:
	Weź MT dla L i odwróć jej wyjście (tak $\to$ nie oraz nie $\to$ tak)

##### #Twierdzenie #RekurencyjniePrzeliczlny
Jeżeli $L$ oraz jego dopełnienie $\bar{L}$ są rekurencyjnie przeliczalne to $L$ jest rekurencyjny. Zatem $\bar{L}$ też jest rekurencyjny
Dowód:
	Weź MT $M_1, M_2$ dla $L, \bar{L}$ i stwórz M taką że jeżeli:
	1. $M_1 \to tak$ to $M \to tak$
	2. $M_2 \to tak$ to $M \to nie$

##### #Twierdzenie #Przekątniowy #RekurencyjniePrzeliczlny 
Język $L_d$ (przekątniowy) nie jest rekurencyjnie przeliczalny
Dowód:
	Załóżmy, że istnieje taka maszyna MT taka, że $L(M_d) = L_d$.
	Niech $w_d = kod_{M_d}$ jest kodem maszyny $M_d$
	Zatem $w_d \in L_d$ (ponieważ $M_d$ nie akceptuje swojego kodu)
	Zatem $w_d \in L(M(w_d))$ zatem $w_d \notin L(M_d)$ zatem $w_d \notin L_d$ 
	**Sprzeczność !**

##### #Twierdzenie #Przekątniowy  #RekurencyjniePrzeliczlny 
Dopełnienie języka przekątniowego jest rekurencyjnie przeliczalny.
Dowód:
	Niech $M'$ akceptuje $\bar{L_d} = \{ w: w\in L(M(w)) \}$
	1. Maszyna $M'$ znajduje maszynę $M(w)$
	2. Przez maszynę uniwersalną $U$ maszyna $M'$ symuluje $M(w)$
	3. $M'$ akceptuje $w$ $\iff$ $M(w)$ akceptuje $w$

##### #Twierdzenie #Uniwersalny #RekurencyjniePrzeliczlny 
Język uniwersalny jest rekurencyjnie przeliczalny
Dowód:
	Przez konstrukcję przy pomocy wielotaśmowej MT (3 taśmy + 1 taśma brudnopis) 

##### #Twierdzenie #Uniwersalny #Rekurencyjny 
Język uniwersalny ***nie*** jest rekurencyjny
Dowód:
	Jeżeli $L_u$ jest RP to jego dopełnienie też zatem można stworzyć MT symulującą MT dla języka przekątniowego, a wiadomo że język przekątniowy nie jest rekurencyjny

##### #Twierdzenie #Uniwersalny #RekurencyjniePrzeliczlny 
Dopełnienie języka uniwersalnego $\bar{L_u}$ nie jest rekurencyjnie przeliczalny
Dowód:
	Język przekątniowy jest podzbiorem języka $\bar{L_u}$ zatem można zbudować MT akceptującą język przekątniowy, który nie jest rekurencyjnie przeliczalny

##### #Twierdzenie #KodówNiePustych #RekurencyjniePrzeliczlny 
$L_{np}$ jest rekurencyjnie przeliczalny
Dowód:
	Pobieramy kod maszyny $M_i$, zgadujemy słowo $w$, które jest akceptowane przez $M_i$. Przy użyciu maszyny uniwersalnej sprawdzamy czy akceptuje słowo $w$

##### #Twierdzenie #KodówNiePustych #Rekurencyjny 
Język $L_{np}$ nie jest rekurencyjny
Dowód:
	Redukujemy z języka uniwersalnego (który nie jest rekurencyjny) do języka $L_{np}$ z #Twierdzenie #Redukcja  wiemy że w takim wypadku język $L_{np}$ nie jest rekurencyjny

##### #Twierdzenie #KodówPustych #Rekurencyjny 
Język $L_p$ nie jest rekurencyjny

##### #Twierdzenie #KodówMaszynRekurencyjnych #RekurencyjniePrzeliczlny 
Język $L_r$ nie jest rekurencyjnie przeliczalny

##### #Twierdzenie #KodówMaszynNieRekurencyjnych #RekurencyjniePrzeliczlny 
Język $L_{nr}$ nie jest rekurencyjnie przeliczalny

### #Porządek kardynalny
Porządek kardynalny definiuje porządek słów nad alfabetem w następujący sposób
1. Słowa krótsze są przed dłuższymi
2. Słowa równej długości są porządkowane porównując kolejne litery od lewej do prawej

### #Redukcja
Redukcja polega na przekształceniu jednego problemu do drugiego tak, aby zbiory odpowiedzi pierwszego problemu były podzbiorem drugiego problemu.

##### #Twierdzenie #Redukcja 
Jeżeli istnieje redukcja problemu $P_1$ do $P_2$ to:
1. Jeżeli $P_1$ ***nie*** jest #RekurencyjniePrzeliczlny  to $P_2$ też nie jest RP
2. Jeżeli $P_1$ ***nie*** jest #Rekurencyjny to $P_2$ też nie jest rekurencyjny


## #Język Podsumowanie
| Język | Pełna nazwa | RP | REK |
| ------ | --- | --- | --- |
| $L_d$ | przekątniowy | NIE | NIE |
| $\bar{L_d}$ | dop. przekątniowego | TAK |  |
| $L_u$ | uniwersalny | TAK | NIE |
| $\bar{L_u}$ | dop. uniwersalny | NIE | NIE |
| $L_{np}$ | kodów niepustych | TAK | NIE | 
| $L_p$| kodów pustych |  | NIE |
| $L_r$ | kodów maszyn rek. | NIE | NIE |
| $L_{nr}$ | kodów maszyn nierek. | NIE | NIE |


### #RAM
Maszyna RAM to wyidealizowany komputer ze swobodnym dostępem do pamięci. Składa się z nieskończonej liczby rejestrów $R_i$ zawierających dowolne słowo nad alfabetem $\Sigma = \{ a_1,a_2, \dots, a_n \}$ 
Program maszyny #RAM  to lista instrukcji oznaczonych potencjalnie nieskończonym zbiorem identyfikatorów. Instrukcje maszyny RAM:
1. $E$ $add_j$ $R$
2. E $del$ R
3. $E$ $clr$ $R$ (można zastąpić innymi operacjami)
4. $E$ $R$ ← $Q$ (można zastąpić innymi operacjami)
5. $E$ $jmp$ $E'$ (można zastąpić innymi operacjami)
6. $E$ $jmp_jR$ $E'$
7. $E$ $continue$


### #Funkcja Prosta
Następujące funkcje nazywamy prostymi:
1. Funkcja następnikowa $s^1(x)=x+1$
2. Funkcja zerowa $o^1(x)=0$
3. Funkcja projekcji $I^n_m(x_1,\dots,x_n)=x_m$ dla $1\leq m \leq n$

### Operacja #Złożenie
Operacja złożenia funkcji $g^m, f^n_1,f^n_2,\dots,f^n_m$ jest funkcja $h^n(x_1,\dots,x_n)=g^m(f^n_1(x_1,\dots,x_n),f^n_2(x_1,\dots,x_n),\dots,f^n_m(x_1,\dots,x_n))$

### Operacja #Podstawienie 
Operacją podstawienie funkcji $g^m, f_1,f_2,\dots,f_n$ jest funkcja
$h^n=g^m(t_1,t_2,\dots,t_m)$ 
gdzie $t_i = f_j(x_{j_1},\dots,x_{j_n}$ gdzie każde $x_{j_i}$ jest jedną ze zmiennych $x_1, \dots, x_n$ lub $t_i$ jest jedną ze zmiennych **$x_1, \dots, x_n$

### #Funkcja Rekursja prosta
Operatorem rekursji prostej otrzymujemy funkcję $f^{n+1}(x_1,\dots,x_n,y)$ z funkcji $g^n(x_1,\dots,x_n)$ i $h^{n+2}(x_1,\dots,x_n,y,z)$ korzystając ze schematu:
1. $f^{n+1}(x_1,\dots,x_{n-1},0)=g^n(x_1,\dots,x_n)$
2. $f^{n+1}(x_1,\dots,x_{n-1},y+1)=h^{n+2}(x_1,\dots,x_{n-1}, f^{n+1}(x_1,\dots,x_{n-1},y))$
Dla $n=0$ schemat rekursji prostej przyjmie postać:
1. $f(0)=a$
2. $f(y+1)=g(y,f(y))$

### #Funkcja pierwotnie rekursywna
Funkcja $n+1$ zmiennych $f^{n+1}$ jest pierwotnie rekursywna, jeżeli jest spełniony jeden z warunków:
1. jest funkcją *następnikową*, *zerową* lub *projekcji*
2. jest zdefiniowana za pomocą schematu rekursji pierwotnej z funkcji pierwotnie rekursywnych $g$ i $h$
3. jest zdefiniowana przez złożenie funkcji pierwotnie rekursywnych $h$, $g_1, \dots, g_m$
Wszystkie funkcje pierwotnie rekursywne można skonstruować przez stosowanie powyższych zasad skończoną ilość razy

#### #Funkcja Pierwotnie rekursywne (lista)
* funkcja stałą $f(x)=n$
* zwiększenie o stałą $f(x) = x + n$
* dodawanie $f(x,y) = x+y$
* mnożenie $f(x,y)=x \cdot y$
* potęgowanie $f(x,y) = x^y$
* silnia $f(x)=x!$
* funkcja znaku $f(x=0) = 0$ i $f(x>0)=1$
* odwrócona funkcja znaku $f(x=0)=1$ i $f(x>0)=0$
* dekrementacja ograniczona 
	  $x \dot{-} 1 = 0$ dla $x=0$
	  $x \dot{-} 1 = x-1$ dla $x>0$
* odejmowanie ograniczone 
	  $x \dot{-} y = 0$ dla $x\leq y$
	  $x \dot{-} y = x-y$ dla $x>y$
* moduł odejmowania $|x-y|$
* maksimum $max(x,y)$
* minimum $min(x,y)$
* operator porównania $<,=,>$
* operacja minimum efektywnego
* kodowanie/dekodowanie Cantora (dowód przy użyciu minimum ograniczonego)
* kodowanie/dekodowanie numeracji Godla
* wyznaczanie długości numeracji Godla $Lh(z)$
* funkcja śladu
* funkcja długości śladu

**Operacja minimum efektywnego** - najmniejsza wartość $j\leq n$ dla której $h(j)=0$ oznaczmy $\mu_{j\leq n}[h(j)=0]$ 
Definiujemy operację minimum efektywnego (ograniczonego) jako
1. $f(x_!,x_2,\dots,x_k,n)=\mu_{j\leq n}[h(x_!,x_2,\dots,x_k,y)=0]$ gdy $\exists y$
2. $f(x_!,x_2,\dots,x_k,n)=0$ gdy $\nexists y$

**Kodowanie numeracji Cantora** - kodowanie pary liczb naturalnych za pomocą jednej naturalnej
	$\pi(x,y) = \frac{(x+y)(x+y+1)}{2}+x = \frac{1}{2}(x^2 + 2xy + y^2 + 3x +y)$
i dekodowanie przy pomocy pierwotnie rekursywnej
	$\pi(\sigma_1(z),\sigma_2(z)) = z$

**Numeracja Godla** - rozkład liczby naturalnej na czynniki pierwsze.
	$x_0,\dots,x_n \to p_0^{x_0},\dots,p_n^{x_n}$
gdzie $p_i$ to (i+1)-sza liczba pierwsza
Kodowanie:
	$z=<x_0,\dots,x_n>=\Pi_{i=0}^n pn(i)^{f(i)}$
	gdzie $pn(i)$ ot (i+1)-sza liczba pierwsza (funkcja rekursywna), a $f(i)=x_i$
Dekodowanie:
	$E(i,z)$ zwraca wykładnik (i+1)-szej liczby pierwszej w rozkładzie $z$
Długość rozkładu:
	$Lh(z)$ - zwraca długość numeracji Godla


### #Funkcja #Ackerman
Definicja:
	$A(0,y) = y +1$
	$A(x+1,0) = A(x,1)$
	$A(x+1, y+1) = A(x, A(x+1,y))$
Cechy:
1. $A(1,y)=y+2$
2. $A(2,y)=2y+3$
3. $y < A(x,y)$
4. $A(x,y) < A(x,y+1)$
5. $A(x+1,y) \geq A(x, y+1)$
6. $A(x,y)<A(x+1,y)$
7. $A(r,A(x,y)) < A(r+s+2,y)$

##### #Twierdzenie #Ackerman 
Funkcja Ackermanna **nie** jest pierwotnie rekursywna
Dowód:
1. lemat: fun. Ackermanna rośnie szybciej niż dowolna funkcja pierwotnie rekursywna
2. fun. Ackermanna jest niemalejąca ze względu na pierwszą i drugą zmienną

##### #Twierdzenie 
Dla dowolnej funkcji prymitywnie rekurencyjnej f istnieje taka stałą $n_f$, że $x=max\{x_1,\dots,x_n\}$: $f(x_1,\dots,x_n)<A(n_f,x)$.

##### #Twierdzenie 
Funkcja Ackermanna rośnie szybciej niż jakakolwiek funkcja pierwotnie rekursywna


### #Funkcja #Rekurencyjna
Funkcja $g$ jest rekurencyjna, jeśli:
1. Jest funkcją stałą, funkcją następnika lub funkcją projekcji
2. Jest zdefiniowana przez składanie funkcji rekurencyjnych
3. Jest zdefiniowana poprzez pierwotną rekursję na funkcjach rekurencyjnych
4. Jest zdefiniowana poprzez operację minimum (nieograniczonego) na funkcjach całkowitych, częściowo rekurencyjnych, które są regularne

**Minimum nieograniczone** - wartością jej jest najmniejsze naturalne $z$ takie, że $k(x_1,\dots,x_n,z)=0$ jeśli ta $z$ istnieje, w przeciwnym wypadku operacja jest niezdefiniowana
	$f(x_1,\dots,x_n)=\mu_z[k(x_1,\dots,x_n,z)=0]$
Różnica między operacją minimum efektywnego polega na tym, że operacja nie musi się zakończyć

##### #Twierdzenie #Ackerman 
Funkcja Ackermanna jest funkcją rekurencyjną.
Dowód:
	Obliczenie dowolnej wartości funkcji Ackermanna można zapisać jako ciąg zagnieżdżonych wywołań funkcji
		$A(w_1,A(w_2,A(w_3,\dots A(w_{k-2}),A(w_{k-1},w_k))\dots)))$
	Wywołanie można jednoznacznie zakodować w postaci ciągu $k$ zmiennych: $(w_1,w_2,\dots,w_k)$
	Można zakodować ciąg wywołań w postaci pojedynczej liczby używając wartości Godla $2^k \cdot 3^{w_1} \cdot \dots \cdot p_k^{w_k}$ 
	Pojedyncze wywołąnie Ackermanna $w_1=A(x,y)$ kodujemy jako $2\cdot 3^{w_1}$  

### #Funkcja śladu
* Niech $\psi (x,y,n)$ będzie liczbą Godla $n$ tego kroku obliczeń funkcji $A(x,y)$
* Jeżeli obliczenie $A(x,y)$ zamyka się w $n_0$ krokach i liczba Godla dla ostatniego kroku wynosi $z$, to dla wszystkich $n\geq n_0$
* przyjmujemy $\psi(x,y,z)=z$
* Wówczas funkcja śladu $\psi$ będzie funkcją całkowitą - funkcja śladu dla obliczeń $A$

##### #Twierdzenie Funkcja śladu jest pierwotnie rekursywną
Funkcja śladu jest pierwotnie rekursywną.

### #Funkcja długość śladu
* Oznaczamy $L(z)=E(0,z)$
* Funkcja $L$ zwraca długość ciągu reprezentowanego przez daną liczbę Godla na podstawie wykładnika dwójki

##### #Twierdzenie Funkcja długości śladu jest pierwotnie rekursywna

### #Funkcja liczba kroków obliczenie $A(x,y$
* Niech $\eta (x,y)$ będzie minimalną liczbą kroków potrzebną do obliczenia wartości $A(x,y)$
* Funkcja $\eta (x,y)$ jest najmniejszą wartością $n$ dla której $\psi(x,y,z)$ (funkcja śladu) reprezentuje ciąg składający się z pojedynczej liczby naturalnej
* Zatem:
	 $\eta (x,y) = \mu_n[L(\psi(x,y,z))=1]$

##### #Twierdzenie Funkcja liczby kroków $\eta (x,y)$ jest rekursywna

### #Ackerman 
Można zdefiniować funkcję Ackermanna jako:
	$A(x,y) = E(1,\psi(x,y,\eta(x,y)))$
zatem funkcja Ackermanna należy do klasy funkcji rekurencyjnych.

### #Funkcja Obliczalna w ogólności
Funkcja $f:N^n\to N$ jest obliczalna w sensie Turinga w ogólności ( #TCG:  *Turing Computable in General*) jeżeli istnieje maszyna Turinga, która dla zapisanych na taśmie argumentów wejściowych $X_1,x_2,\dots,x_n$:
1. zatrzyma się gdy funkcja $f(x_1,\dots,x_n)$ jest określona i zapisze na taśmie wartość funkcji $f$,
2. nie zatrzyma się, gdy $f(x_1,\dots,x_n)$ nie jest określona

### #Funkcja Obliczalna
Funkcja jest obliczalna w sensie Turinga ( #TC: Turing Computable) jeżeli jest całkowita i jest #TCG

### Związek MT i funkcji
* Funkcje #TCG są obliczalne przez MT
* Funkcje #TC  są obliczalne przez MT z własnością stopu

##### #Twierdzenie  #Funkcja #TCG  a #Funkcja  Częściowo rekursywna
Każda funkcja częściowo rekursywna jest #TCG 


##### #Twierdzenie #Funkcja #TC a #Funkcja Rekursywna
Każda funkcja rekursywna jest #TC 

### #Funkcja Bazowe
Dowód:
	1. Pokażemy, że istnieje MT obliczająca każdą funkcję bazową:
		1. Dla **funkcji zerowej** maszyna wymazuje wejście i zapisuje na taśmie 0
		2. Dla **funkcji następnikowej** i wejścia $w$ zapisanym w kodzie binarnym MT wykonuje dodanie 1
		3. Dla **funkcji wyboru** maszyna przepisuje wybraną zmienną na początek taśmy a resztę wymazuje
	2. Złożenie 
		Dla danej funkcji $f(x_1,\dots,x_n)=h(g_1(x_1,\dots,x_n),\dots,g_k(x_1,\dots,x_n))$
		Najpierw obliczamy wartości $g_1,\dots,g_k$ później przepisujemy je na taśmę  obliczającą wartość $h$ i ją obliczamy
	3. Rekursja prosta - rekursywne obliczanie od $(x_1,\dots,x_n,0)$ do $(x_1,\dots,x_n,n+1)$ 
	4. Minimum nieograniczone dla $f(x_1,\dots,n_n) = \mu_z[g(x_1,\dots,x_n,z)=0]$ Obliczamy $g$ dla $z=1,2,3,\dots$ aż wartość wyniesie 0

##### #Twierdzenie #Funkcja wyliczające dla MT
Dla każdej MT $T$ istnieje funkcja częściowo rekurencyjna $f_T$, która realizuje obliczenie tej maszyny, tzn.
* Jeżeli dla pewnych danych wejściowych maszyna się zatrzyma, to dla tych danych wartością funkcji $f_T$ będzie wartość obliczenia maszyny Turinga
* Jeżeli dla pewnych danych wejściowych maszyna się nie zatrzyma, to funkcja $f_T$ jest dla tych danych nieokreślona
Dowód:
	* Bez straty ogólności: symbole binarne, taśma jednostronnie ograniczona
	* Stany numerowane są liczbami naturalnymi i stanem końcowym jest stan z indeksem 0
	* Każdą maszynę da się zasymulować taką maszyną
	Niech $M = (Q, \Sigma, \Gamma, \rho,q_0, B,F)$ gdzie $Q=\{0,1,\dots,N_q\}$, $\Sigma=\{1\}$,$\Gamma=\{0,1\}$, $\rho(q,s)=(q',s',d)$, $q_0=1$, $B=0$, $F=\{0\}$
	Definiujemy funkcje
		$Q(q,s)=q'$
		$S(q,s)=s'$
		$D(q,s)= 0$ dla $d=R$, $D(q,s)= 1$ dla $d=L$ 
	 Podział taśmy:
		 Dzielimy taśmę na 3 części:
		 1. $m(t)$ - część na lewo (mała liczba  zapisie binarnym)
		 2. $s(t)$ - to co widzi głowica
		 3. $k(t)$ - zapis na prawo w kodowaniu od najmłodszego bitu
		$TAPE[i]$ - i-ty symbol taśmy
	* W chwili początkowej:
		$t=0$
		$m(0)=0$
		$k(0)=[TAP[1],TAP[2]\dots]$
		$s(0)=[TAP[0]]$
		$q(0) = q_0 = 1$
	* Ruchy: TOO MUCH MATH
	* Zakończenie:
		funkcja realizująca obliczenie MT ma postać $f_T([TAP]) = [m(t_{\mu})s(t_{\mu}),k(t_{\mu})]$ gdzie $t_{\mu}=\mu_t[q(t)=0]$ jest obliczone przez operację minimum nieograniczonego (moment osiągnięcia stanu akceptującego)
**WNIOSEK: Dla każdej MT z warunkiem stopu istnieje #Funkcja  rekursywna, która realizuje obliczenie tej maszyny**


### Problem #NP 
Problem  jest #NP jeżeli ma on niedeterministyczny koszt wielomianowy tzn. niedeterministyczna MT rozwiązuje go w czasie wielomianowym $O(n^k)$

### Problem #NP-Zupełny
Problem decyzyjny jest zupełny w klasie NP (jest NP-Zupełny) jeżeli:
1. Problem jest #NP 
2. Każdy problem #NP redukuje się w czasie wielomianowym do tego problemu
**Jeżeli zachodzi tylko 2 to jest to problem NP-trudny**

### Problem SAT
* Dana jest formuła boolowska $f$ o zmiennych $x_1,\dots,x_n \in \{0,1\}$
* Czy istnieje wartościowanie $x_1,\dots,x_n$ dla którego formuła $f$ jest prawdziwa ?

### #Twierdzenie #Cook
Problem SAT jest #NP-Zupełny 
Dowód:
	1. Problem SAT jest #NP 
	2. Każdy problem #NP redukuje się w czasie wielomianowym do problemu SAT
	ad 1.
		Maszyna niedeterministyczna może zgadnąć rozwiązanie, a następnie sprawdzić czy dla tego wartościowanie formuła jest prawdziwa. Sprawdzenie można dokonać w czasie wielomianowym względem długości formuły.
	ad 2.
		Każdy problem #NP redukuje się w czasie wielomianowym do problemu SAT.
		Dla $M=(Q,\Sigma,\Gamma,\rho,q_0,B,F)$ działającej w czasie $p(n)$ i słowa $w$ ($|w|=n$)
		można zbudować formułę boolowską $f$ taką, że $M$ akceptuje $w$ $\iff$ istnieje wartościowanie spełniające $f$
		**Ograniczenie czasu**:
			 * Analizujemy tylko komórki oddalone o $p(n)$ od $q_0$
			 * Oznaczamy komórkę startową 0, więc rozpatrujemy odcinek taśmy $[-p(n), p(n)]$
			 * Operacja przesunięcia głowicy to zmiana licznika $d$ o $\pm 1$
		**Opis chwilowy**:
			Niech $q\in Q, i\in [-p(n),p(n)], j\in \Sigma, k \in [0, p(n)]$.
			1. $T_{ijk} = 1 \iff$ i-ta komórka taśmy zawiera symbol j, w k-tym kroku obliczeń. ($O(p^2(n))$ zmiennych)
			2. $H_{ik} = 1 \iff$ głowica jest nad i-tą komórką, w k-tym kroku obliczeń. ($O(p^2(n))$ zmiennych)
			3. $Q_{qk} = 1 \iff$ maszyna przyjmie stan $q$ w k-tym kroku obliczenia. ($O(p(n))$ zmiennych).
		**Formuła SAT**:
			* Stwórz formułę boolowską, która przedstawia obraz chwilowy MT (formuła $O(p^2(n))$ zmiennych)
			* Formuła jest koniunkcją szeregu formuł kodujących
		**Stan początkowy**:
			1. $T_{ij0}$ - zapis słowa wejściowego ($O(p(n))$ elementów)
			2. $Q_{q_01}$ - stan początkowy (1 element)
			3. $H_{00}$ - początkowe położenie głowicy (1 element)
		**Poprawność kodowania**:
			1. W każdym kroku obliczenia, w każdej komórce jest dokładnie jeden symbol ($O(p^2(n))$ zmiennych)
			2. Zmiana symbolu może nastąpić tylko w komórce wskazywanej przez głowicę ($O(p(n))$ elementów)
			3. Maszyna może być tylko w jednym stanie ($O(p(n))$ elementów)
			4. Głowica może być tylko nad jedną komórką ($O(p(n))$ elementów)
		**Poprawność obliczeń**:
			1. Zmiany kodowania są zgodne z funkcją przejścia $\delta$ ($O(p^2(n))$ elementów)
			2. Obliczenia są kończone w stanie akceptującym (($|F|\leq O(p(n))$ elementów))
		**Zakończenie**:
			* Jeżeli znamy obliczenie maszyny $M$ dla słowa $w$ to formuła jest spełniona
			* Jeżeli znamy wartościowanie $f$ to z wartości $H_{ik}, Q_{qk}, T_{ijk}$ odczytamy krok po kroku przebieg obliczenia maszyny $M$
			* Koszt przekształcenia daje się oszacować wielomianem $p(n)$

### #Twierdzenie #Savitcha
Jeżeli $M$ jest niedeterministyczną MT o konstruowanej złożoności pamięciowej $S(n)$, to istnieje deterministyczna MT $M_0$ o złożoności pamięciowej $O(S^2(n))$ taka, że $L(M)=L(M_0)$.
Dowód:
	$M=(Q,\Sigma,\Gamma,B,\delta,q_0,q_f)$ - $k$ taśmowa niedeterministyczna MT ma konstruowalną złożoność $S(n)$. Liczba ruchów, które maszyna $M$ musi wykonać co najwyżej $c^{S(n)}$ gdzie $c$ to pewna stała.
	Dokładnie oszacowanie $c^{S(n)}$ to: $|Q|\cdot (|\Sigma|+1)^{kS(n)}\cdot (S(n))^k$)
		$|Q|$ - liczba możliwych stanów $M$
		$(|\Sigma|+1)^{kS(n)}$ - liczba możliwych zawartości taśm ($k$ taśm, $S(n)$ komórek pamięci na każdej i $|\Sigma|$ symboli wejściowych)
		$(S(n))^k$ liczba możliwych położeń głowic ($k$ taśm, $S(n)$ komórek na każdej z nich)
	**Rozbicie na podciągi**:
		* Jeżeli $C_1 |-^{*}_M C_2$ to maszyna $M$ przechodzi z konfiguracji $C_1$ do $C_2$ w co najwyżej $c^{S(n)}$ ruchach
		* Sprawdzanie czy przejście można wykonać w nie więcej niż $2i$ krokach (sprawdzanie czy można przejść do takiej konfiguracji $C_3$ że potrzeba $i$ kroków na $C_1 |-^{*}_M C_3$ oraz $i$ kroków na przejście $C_3 |-^{*}_M C_2$)
	**Idea**:
		* Działanie deterministycznej MT $M_0$ polega na sprawdzeniu czy istnieje przejście z konfiguracji początkowej $C_0$ do konfiguracji akceptującej
		* Używamy rekurencyjnej procedury $TEST(C_1,C_2,i)$, która sprawdza czy możliwe jest przejście ze stanu $C_1$ do $C_2$ w co najwyżej $i$ krokach (sprawdzamy dla stanów $C_3$ z maksymalnie $S(n)$ komórkami na każdej taśmie z argumentem $ceiling(i/2)$
	**Przełożenie na MT**:
		* $C_1$ i $C_2$ zajmują nie więcej niż $S(n)$ komórek pamięci na każdej taśmie (funkcja konstruowana pamięciowo)
		* Jeżeli wywołamy procedurę $TEST(C_0,C_f,c^{S(n)})$ dla każdego ze stanów akceptujących $C_f$ i chociaż raz procedura ta zwróci $true$ to słowo jest akceptujące $\exists_{C_f \in Q} TEST(C_0,C_f,c^{S(n)}) \to w \in L(M)$
	**Złożoność pamięciowa**:
		* Można zaimplementować algorytm na deterministycznej MT o złożoności pamięciowej $O(S^2(n))$
		* Ponieważ $TEST$ implementujemy deterministycznej MT ze stosem. Argumenty procedury $TEST$ mają długość $O(S(n))$ (są na bazie niedeterministycznej MT konstruowanej pamięciowo) zatem potrzebujemy takiej długości ramek na stosie
		W każdym wywołaniu procedury $TEST$ trzeci argument jest o połowę mniejszy, więc liczba ramek odłożonych na stosie podczas całego działania algorytmu wynosi $1+ceiling(log(c^{S(n)}))$ (rząd $O(S(n))$). Zatem skonstruowana MT deterministyczna ma złożoność pamięciową $O(S^2(n))$ ponieważ:
			1. liczba ramek na stosie $O(S(n))$
			2. wielkość ramki stosu $O(S(n))$
			3. liczba ramek x wielkość ramki = $O(S^2(n))$ 