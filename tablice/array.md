
## Inicjalizacja tablicy:
Aby przygotować tablicę musimy podać długość naszej tablicy, oraz typ danych jakie będzie zawierała. Stwórzmy tablicę typu `int` o nazwie `myArr` która zawiera `50\` elementów:

```java
// typ[] nazwa = new typ[długość];
int[] myIntArr = new int[5];
```

To samo dla innych typów, np `String`:
```java
// typ[] nazwa = new typ[długość];
String[] myStringArr = new String[5];
```

Uzyskamy wtedy tablicę zawierającą `5` elementów. Nie zdefiniowaliśmy jaką wartość mają mieć poszczególne elementy, więc wyglądać będą tak: `{ null, null, null, null, null }`. 
Zdefiniujmy teraz tablice, które mają na sztywno ustalone wartości poszczególnych elementów. Elementy umieszczamy w wąsach: `{ elementy }` zaraz po deklaracji:
```java
// typ[] nazwa = { elementy };
int[] myIntArr = { 10, 11, 12, 13, 14 };
String[] myStringArr = { "raz", "dwa", "trzy", "cztery", "pięć" };
```

Możemy połączyć te dwa sposoby:
```java
// typ[] nazwa = new typ[]{ elementy };
int[] myIntArr = new int[]{ 10, 11, 12, 13, 14 };
String[] myStringArr = new String[]{ "raz", "dwa", "trzy", "cztery", "pięć" };
```

Elementy tablicy mają swoje pozycje, które nazywamy indeksami. W Javie indeksy liczymy od zera, a nie od jednego. Wynika stąd, że pierwszy element tablicy ma indeks równy zero. Do danego elementu tablicy możemy odwołać się podając jego indeks w kwadratowych nawiasach: `[index]`. Wyświetlmy zatem dla przykładu pierwszy i czwarty element tablicy:

```java
// tablica[index]
String[] myStringArr = {"pierwszy", "drugi", "trzeci", "ostatni"};
System.out.println(myStringArr[0]); // Wyświetl pierwszy element tablicy
System.out.println(myStringArr[3]); // Wyświetl czwarty element tablicy

// BONUS
System.out.println(myStringArr[myStringArr.length - 1]); // Wyświetl ostatni element tablicy
```
```
Output:
pierwszy
ostatni
ostatni
```

W poprzednim przykładzie użyliśmy własności tablic `length`. Pokazuje ona długość danej tablicy, z tym że tutaj liczymy jej długość zaczynając od jedynki.
```java
String[] myStringArr = {"pierwszy", "drugi", "trzeci", "ostatni"};
int[] myIntArr = new int[30];

System.out.println(myStringArr.length);
System.out.println(myIntArr.length);
```
```
Output:
4
30
```
## Iterowanie po tablicy:

Aby odnieść się do kolejnych elementów tablicy możemy wesprzeć się iteratorem. Aby go użyć musimy znać `typ` danych naszej tablicy, oraz wiedzieć jaka jest `nazwa` naszej tablicy: 
```java
// for (typ nazwaZmiennej: nazwa) {
//	 ciało iteratora
// }

int[] myIntArray = { 1, 2, 3, 4, 5 };
for (int myIntVariable: myIntArray) {
	System.out.println(myIntVariable);
};
```
```
Output:
1
2
3
4
5
```

Iterator ten nie udostępnia nam indeksu elementu po którym aktualnie iteruje. Nie mamy też sposobu na edycje zawartości naszej tablicy w ciele powyższego iteratora. W takich sytuacjach przyda nam się odpowiednio wywołana pętla `for`:
```java
int[] myIntArray = { 1, 2, 3, 4, 5 };
for (int i = 0; i < myIntArray.length; i++) {
	System.out.println("Dla indeksu równego " + i + " wartość elementu wynosi: " + myIntArray[i]);
};
```
```
Output:
Dla indeksu równego 0 wartość elementu wynosi: 1
Dla indeksu równego 1 wartość elementu wynosi: 2
Dla indeksu równego 2 wartość elementu wynosi: 3
Dla indeksu równego 3 wartość elementu wynosi: 4
Dla indeksu równego 4 wartość elementu wynosi: 5
```

Pozwala nam to na swobodne edytowanie elementów tablicy. Spróbujmy zmodyfikować naszą tablicę. Niech każdy jej element zostanie pomnożony przez 10:
```java
int[] myIntArray = { 1, 2, 3, 4, 5 };
for (int i = 0; i < myIntArray.length; i++) {
	myIntArray[i] = myIntArray[i] * 10;
	System.out.println("Dla indeksu równego " + i + " wartość elementu wynosi: " + 
myIntArray[i]);
};
```
```
Output:
Dla indeksu równego 0 wartość elementu wynosi: 10
Dla indeksu równego 1 wartość elementu wynosi: 20
Dla indeksu równego 2 wartość elementu wynosi: 30
Dla indeksu równego 3 wartość elementu wynosi: 40
Dla indeksu równego 4 wartość elementu wynosi: 50
```

Znajomość indeksu elementu do którego się odwołujemy jest bardzo przydatna. Zobaczmy przykład w którym edytujemy tylko co drugi element tablicy:
```java
int[] myIntArray = { 1, 2, 3, 4, 5 };
for (int i = 0; i < myIntArray.length; i++) {
	if (i % 2 == 0) {
		myIntArray[i] = myIntArray[i] * 10;
	}
	System.out.println("Dla indeksu równego " + i + " wartość elementu wynosi: " + 
myIntArray[i]);
};
```
```
Output:
Dla indeksu równego 0 wartość elementu wynosi: 10
Dla indeksu równego 1 wartość elementu wynosi: 2
Dla indeksu równego 2 wartość elementu wynosi: 30
Dla indeksu równego 3 wartość elementu wynosi: 4
Dla indeksu równego 4 wartość elementu wynosi: 50
```

## Tablice dwuwymiarowe

Żeby zdefiniować czym jest tablica dwuwymiarowa użyjmy skrótu myślowego - tablica dwuwymiarowa jest to tablica zawierająca inne tablice, np:
```java
int[][] myTwoDimensionalIntArray = {{1, 2}, {3, 4}};
```

Do elementów danych tablic odwołujemy się w sposób podobny do tego, którego używaliśmy w tablicach jednowymiarowych. Musimy odwołać się do indexu danej tablicy, a następnie do indexu elementu:
```java
int[][] myTwoDimensionalIntArray = {{1, 2}, {3, 4}};

System.out.println(myTwoDimensionalIntArray[0][0]); //pierwsza tablica, pierwszy element
System.out.println(myTwoDimensionalIntArray[0][1]); //pierwsza tablica, drugi element
System.out.println(myTwoDimensionalIntArray[1][0]); //druga tablica, pierwszy element
System.out.println(myTwoDimensionalIntArray[1][1]); //druga tablica, drugi element
```
```
Output:
1
2
3
4
```
