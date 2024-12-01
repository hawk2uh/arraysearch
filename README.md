# Metoda binarnego wyszukiwania
## 1. Wyszukiwanie binarne
**Wyszukiwanie binarne** – zwane również „podziałem na pół”, to algorytm, który w bardzo efektywny sposób odnajduje poszukiwany element w posortowanym zbiorze danych. Ta pozornie trywialna idea sprawia, że algorytm ten doskonale sprawdza się w praktyce, szczególnie przy dużych ilościach danych.
   
### **Zalety**:
- Jest szybkie (złożoność obliczeniowa - **O(log n)**)
  
### **Wady**:
- Może być wykorzystane tylko dla posortowanego zbioru danch
---
### Mechanizm działania

---

### Implementacja wyszukiwania binarnego
```python
def binary_search(list, left, right, x):

    # Warunek dla zakończenia szukania wartości
    while left <= right:

        # Wyznaczamy środek rozpatrywanego zbioru danych
        mid = left + (right - left) // 2

        # Sprawdzamy, czy szukana wartość znajduje się w środku
        if list[mid] == x:
            return mid

        # Jeśli szukana wartość jest większa, ignorujemy lewą stronę
        elif list[mid] < x:
            left = mid + 1

        # Jeśli szukana wartość jest mniejsza, ignorujemy prawą stronę
        else:
            right = mid - 1

    # Jeśli dojdziemy tutaj, oznacza to, że wartość nie występuje w zbiorze danych
    return -1
```
---

## 2. Szukanie lidera w zbiorze danych
**Lider** - liczba w zbiorze danych większa niż wszystkie liczby po jej prawej stronie

#### Przykład:
Dla zbioru liczb `[16, 17, 4, 3, 5, 2]` liderem są 17, 5 i 2

**Uwaga**: ostatni element zbioru danych jest zawsze liderem

### Proces znajdowania lidera
1. Zaczynając od ostatniego elementu skanujemy wszystkie liczby w zbiorze danych
2. Ostatni element zawsze jest liderem, więc przenosimy go to `output` i przypisujemy zmiennej `max` jego wartość
3. Po napotkaniu kolejnej liczby sprawdzamy, czy jest większa od `max`
   - Jeśli tak, przenosimy ją do `output` i zmieniamy wartość `max` na tę liczbę 
   - Jeśli nie, przechodzimy do następnego elementu


## 4. Zadania ##
#### Napisz algorytm wyszukiwania binarnego w wersji rekurencyjnej.



---

## Żródła:
- https://www.geeksforgeeks.org/binary-search/#what-is-binary-search
- https://pl.khanacademy.org/computing/computer-science/algorithms/binary-search/a/binary-search
- https://stormit.pl/wyszukiwanie-binarne/#wyszukiwanie-binarne-wprowadzenie
- https://www.youtube.com/watch?v=hDn8iOc30Tk&ab_channel=Computerphile
- https://pl.wikipedia.org/wiki/Wyszukiwanie_binarne
- https://www.geeksforgeeks.org/leaders-in-an-array/
- 
