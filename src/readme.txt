Autor: Tomasz Dakowicz
261438
Student 5 semestru Informatyki, ISI

Przedmiot: AAL
Zadanie: T2 - Mrówki

Opcje uruchomienia:
./main --input 
	uruchamia w trybie manualnego wprowadzania
./main --random
	uruchamia z losowymi testami i porownuje poprawnosc algorytmu
./main --complex
	uruchamia z generowanie testow, porownaniem i mierzeniem czasu

N - liczba wierzchołkow w drzewie
P - liczba możliwych ścieżek do ułożenia
L - liczba liści w drzewie

Metoda rozwiązania:
-metoda brutalna - opiera się na generowaniu wszystkich ścieżek pomiędzy
				wszystkimi liśćmi drzewa i wybraniu tych, które w danej 
				chwili wnoszą największe pokrycie - O(L^2(P + 2N))
-metoda zoptymalizowana - opiera się na pojęciu średnicy grafu - w każdej 
				iteracji algorytmu wybieraną ścieżką jest średnica grafu
				dla dwóch dotąd niepokrytych liści - O(4PN)

Podział na klasy i pliki:
- main.cpp - główny plik programu zawierający funkcję main()
- klasa Tree - przechowuje wierzchołki typu Node w mapie wskaźników oraz 
				zawiera całą funkcjonalność operacji na drzewie, zaimplementowaną 
				w tym projekcie
- klasa Node - reprezentuje pojedynczy wezeł drzewa


Sposób generacji danych - połączenia miedzy węzłami są generowane tak, aby w 
rezultacie otrzymać drzewo: węzeł źródłowy połączenia jest wybierany spośród istniejących
już węzłów, zaś węzeł docelowy jest wybierany spośród jeszcze nie stworzonych węzłów
- w ten sposób otrzymamy spojny graf acykliczny, czyli drzewo (wierzchołki są numerowane 1...n) 
