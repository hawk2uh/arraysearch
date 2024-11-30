# Metoda binarnego wyszukiwania
## 1. Czym jest wyszukiwanie binarne?
**Wyszukiwanie binarne** – zwane również „podziałem na pół”, to algorytm, który w bardzo efektywny sposób odnajduje poszukiwany element w posortowanym zbiorze danych. Ta pozornie trywialna idea sprawia, że algorytm ten doskonale sprawdza się w praktyce, szczególnie przy dużych ilościach danych.
   
### **Zalety**:
- Jest bardzo szybkie (złożoność obliczeniowa - **O(log n)**)
  
### **Wady**:
- Może być wykorzystane tylko dla posortowanego zbioru danch

---

## 2. Mechanizm działania

---

## 3. Implementacja wyszukiwania binarnego
### Python

```python
def binary_search(list, x):

    # Wyznaczamy indeksy końcowe zbioru danych
    left = 0
    right = len(list) - 1

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

### Java

---

## 4. Zadania ##
### Napisz algorytm wyszukiwania binarnego w wersji rekurencyjnej.

---

## Żródła:
- https://www.geeksforgeeks.org/binary-search/#what-is-binary-search
- https://pl.khanacademy.org/computing/computer-science/algorithms/binary-search/a/binary-search
- https://stormit.pl/wyszukiwanie-binarne/#wyszukiwanie-binarne-wprowadzenie
- https://www.youtube.com/watch?v=hDn8iOc30Tk&ab_channel=Computerphile
- https://pl.wikipedia.org/wiki/Wyszukiwanie_binarne
