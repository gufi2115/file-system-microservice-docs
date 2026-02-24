## Mikroserwis do wydajnego i bezpiecznego zarządzania plikami statycznymi
Architektura opiera się na Nginx, który odpowiada za bezpośrednie serwowanie plików do klienta. Django REST Framework odpowiada za autoryzację i zapisywaniem plików.  Baza danych Postgresql przetrzymuje informację o uuid, wielkości, typie oraz ścieżce pliku. Każdy komponent działa w osobnym kontenerze Docker.

## Kluczowe cechy:

#### Wysoka wydajność serwowania
 Wykorzystanie mechanizmu X-Accel-Redirect. API po pozytywnej weryfikacji uprawnień zwraca nagłówek z wewnętrzną ścieżką, a Nginx serwuje plik bezpośrednio z dysku, odciążając workery Pythona.
#### Struktura przechowywania
Pliki są zapisywane na dysku z wykorzystaniem dwupoziomowego fragmentowania na podstawie UUID (np. /12/34/12345...jpeg). Zapobiega to problemom z wydajnością systemu plików przy ogromnej liczbie obiektów.
#### Bezpieczeństwo
Dostęp do API jest zabezpieczony za pomocą API KEY.
#### Skalowalność
Dzięki delegowaniu transferu do Nginxa, serwis jest w stanie obsłużyć wysoki ruch przy minimalnym zużyciu zasobów.


## Paczka do integracji
Dodatkowo stworzyłem paczkę ułatwiającą integrację z mikroserwisem.
[File system pack](https://pypi.org/project/filesystempack/)


## Repozytorium Git

### Microservice
[https://github.com/gufi2115/Microservice-to-save-files](https://github.com/gufi2115/Microservice-to-save-files)

### File system pack
[https://github.com/gufi2115/filesystem-integration](https://github.com/gufi2115/filesystem-integration)

