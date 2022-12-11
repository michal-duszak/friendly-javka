### Czym jest metoda w Javie?

Definicje metody najlepiej opisują elementy których potrzebujemy, by ją zadeklarować. 
Deklaracja metody ma pięć elementów: typ, nazwa, (parametry), {ciało funkcji}, modyfikatory.

1. Zwracany typ - typ wartości którą zwraca metoda, lub `void` jeśli nic nie zwraca
2. Nazwa -  nazwa metody w konwencjiCamelCase
3. Modyfikatory —dostępu np. `public`, `private`, lub inne np. `static`
4. Parametry w okrągłych nawiasach - oddzielone przecinkami, z określeniami typów
5.  Ciało metody w nawiasach klamrowych - kod który metoda wykonuje

### Przeładowanie metody 
Metody o tej samej nazwie w klasie mogą przyjmować różne parametry. 

```java
  public static void tellType(String x) {
    System.out.println("To jest string");
  }
  public static void tellType(int x) {
    System.out.println("To jest int");
  }
  
  public static void main(String args[]) {
    tellType("Friendly javka");
    tellType(2);
  }
```
```
Output:
To jest string
To jest int
```