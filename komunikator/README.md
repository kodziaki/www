# Kodziaki i Komunikator

kodziaki i zabawy w kodowanie

```svg
<svg width="100" height="100" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  <!-- Sześciokąt o środku w punkcie (50,50) i promieniu 40 -->
  <polygon points="
    50,10
    80,25
    80,75
    50,90
    20,75
    20,25
  " fill="lime" stroke="black" stroke-width="2"/>
</svg>
```

## 1. Wybieranie nazwy użytkownika

### Opis
   - **Interfejs wyjścia:** Ekranik na urządzeniu, na którym pokazuje się miejsce do wpisania wybranej nazwy użytkownika.
   - **Interfejs wejścia:** Klawiatura (fizyczna lub ekranowa), za pomocą której wpisujesz swoją wymarzoną nazwę.
   - **Logika:** Program w urządzeniu sprawdza, czy wymyślona nazwa nie jest już używana przez kogoś innego i czy nie zawiera brzydkich słów.
   - **Dane:** Nazwa użytkownika, którą wpisałeś, jest zapisywana, abyś mógł jej używać, kiedy zechcesz się zalogować.


### Hexagon Obiektów


### Graf Akcji
```mermaid
graph LR
    A[Klawiatura] -->|Wprowadzenie nazwy| B[System Sprawdzający]
    B -->|Czy nazwa unikalna i odpowiednia?| C[Tak, Zapisz w bazie danych]
    B -->|Nie, Poproś o inną| A
    C --> D[Wyświetl potwierdzenie]
```



## 2. Nawiązywanie połączenia, w którym użytkownik nie odpowiada

### Opis
   - **Interfejs wyjścia:** Ekranik lub głośnik, który informuje o dzwonieniu do drugiej osoby.
   - **Interfejs wejścia:** Przycisk "Zadzwoń" lub podobny, który naciskasz, aby rozpocząć połączenie.
   - **Logika:** Program próbuje skontaktować się z drugą osobą, sygnalizując dzwonek po jej stronie, ale nie otrzymuje odpowiedzi.
   - **Dane:** Informacja o nieodebranym połączeniu jest zapisywana, aby można było później zobaczyć, kto próbował zadzwonić.


### Hexagon Obiektów


### Graf Akcji
```mermaid
graph LR
    A[Przycisk 'Zadzwoń'] -->|Inicjuj połączenie| B[System Dzwoniący]
    B --> C{Czy druga strona odpowiada?}
    C -->|Tak| D[Połącz rozmowę]
    C -->|Nie| E[Wyświetl komunikat o braku odpowiedzi]
    E --> F[Zapisz informację o nieodebranym połączeniu]
```


## 3. Nawiązywanie połączenia

### Opis
   - **Interfejs wyjścia:** Głośnik telefonu czy komputera, przez który słychać głos drugiej osoby.
   - **Interfejs wejścia:** Przycisk "Zadzwoń" lub podobny, który znów naciskasz, aby zacząć rozmowę, oraz mikrofon, do którego mówisz.
   - **Logika:** Program na urządzeniu łączy cię z drugą osobą i przekazuje wasze głosy między sobą.
   - **Dane:** Informacje o połączeniu, jak długość rozmowy i z kim była przeprowadzona, są zapisywane dla ewentualnych potrzeb np. rozliczeń.

### Hexagon Obiektów

### Graf Akcji
```mermaid
graph LR
    A[Przycisk 'Zadzwoń'] -->|Inicjuj połączenie| B[System Łączący]
    B --> C{Czy połączenie nawiązane?}
    C -->|Tak| D[Przekaż głosy]
    C -->|Nie| E[Wyświetl komunikat o błędzie]
    D --> F[Zapisz dane o połączeniu]
```

### Hexagon Akcji


## 4. Zakończenie komunikacji głosowej

### Opis
   - **Interfejs wyjścia:** Ekran pokazujący, że rozmowa się zakończyła, ewentualnie krótki sygnał dźwiękowy.
   - **Interfejs wejścia:** Przycisk "Zakończ" lub czerwona słuchawka, które naciskasz, kiedy chcesz zakończyć rozmowę.
   - **Logika:** Program na urządzeniu przerywa połączenie z drugą osobą, kiedy ty tego chcesz.
   - **Dane:** Informacja o zakończeniu rozmowy i jej długości zostają zapisane, abyś mógł wiedzieć, ile czasu spędziłeś na rozmowie.


### Hexagon Obiektów


### Graf Akcji

```mermaid
graph LR
    A[Przycisk 'Zakończ'] -->|Zakończ rozmowę| B[System Kończący]
    B --> C[Wyświetl komunikat 'Rozmowa zakończona']
    B --> D[Zapisz czas trwania rozmowy]
```




