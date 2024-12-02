# Szukanie określonego elementu w zbiorze
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

    # warunek dla zakończenia szukania wartości
    while left <= right:

        # wyznaczamy środek rozpatrywanego zbioru danych
        mid = left + (right - left) // 2

        # sprawdzamy, czy szukana wartość znajduje się w środku
        if list[mid] == x:
            return mid

        # jeśli szukana wartość jest większa, ignorujemy lewą stronę
        elif list[mid] < x:
            left = mid + 1

        # jeśli szukana wartość jest mniejsza, ignorujemy prawą stronę
        else:
            right = mid - 1

    # jeśli dojdziemy tutaj, oznacza to, że wartość nie występuje w zbiorze danych
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
   - W innym wypadku przechodzimy do następnego elementu

### Implementacja
```python
def leaders(list):
    result = []
    n = len(list)

    # przypisujemy zmiennej max wartość ostatniego elementu
    max = list[-1]

    # ostatni element zawsze jest liderem
    result.append(max)

    # iterujemy po liście od prawej do lewej
    for i in range(n - 2, -1, -1):
        # jeśli wartość jest większa od maxa, to jest liderem
        if list[i] > max:
            # aktualizujemy wartość zmiennej max
            max = list[i]
            result.append(max)

    result.reverse()

    return result
```
## 2. Szukanie idola w zbiorze danych
**Idol** - element, który występuje w zbiorze więcej niż połowę razy, czyli więcej niż `n/2` razy, gdzie `n` jest liczbą elementów zbioru.
#### Przykłady: 

Dla zbioru liczb `[1, 1, 2, 1, 3, 5, 1]` idolem jest 1 (jedynka pojawia się 4 razy w 7-elementowym zbiorze)

Zbiór liczb `[3, 3, 4, 2, 4, 4, 2, 4]` nie ma idola

## 4. Zadania ##
#### Napisz algorytm wyszukiwania binarnego w wersji rekurencyjnej.



---

## Żródła:
- https://www.geeksforgeeks.org/binary-search/#what-is-binary-search
- https://stormit.pl/wyszukiwanie-binarne/#wyszukiwanie-binarne-wprowadzenie
- https://www.youtube.com/watch?v=hDn8iOc30Tk&ab_channel=Computerphile
- https://pl.wikipedia.org/wiki/Wyszukiwanie_binarne
- https://www.geeksforgeeks.org/leaders-in-an-array/
- https://takeuforward.org/data-structure/leaders-in-an-array/
- https://www.geeksforgeeks.org/majority-element/
