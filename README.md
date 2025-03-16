# Przetwarzanie Sygnałów Satelitarnych z systemu APT satelitów NOAA-18 i NOAA-19.
## Wprowadzenie i cel projektu
Celem projektu jest opracowanie narzędzi umożliwiających kompleksowe przetwarzanie sygnałów pobieranych z satelitów NOAA-18 i NOAA-19. Projekt przyjmuje pliki .wav z systemu APT 137MHz i realizuje:

- **Demodulacja FM:** Przetwarzanie sygnałów o zmiennej częstotliwości.
- **Demodulacja AM:** Przetwarzanie sygnałów o zmiennej amplitudzie.
- **Dekodowanie danych obrazowych:** Analiza i wizualizacja danych wynikowych.

Dzięki zastosowanym metodom przetwarzania, możliwa jest analiza oraz wizualizacja danych telemetrii satelitarnych.

## Instrukcje instalacji środowiska
Projekt został stworzony przy użyciu języka Python i platformy Jupyter Notebook. Aby uruchomić projekt, wykonaj poniższe kroki:

1. **Klonowanie repozytorium**
   ```bash
   git clone <URL_REPOZYTORIUM>
   cd NOAA-demo_deco
2. **Instalacja zależności**

   ```bash
   pip install -r requirements.txt

Upewnij się, że masz zainstalowanego Pythona (wersja 3.7 lub wyższą) i zainstaluj wymagane pakiety.

3. **Uruchomienie Jupyter Lab w terminalu**
   ```bash
   jupyter lab

Następnie otwórz wybrany notebook z repozytorium.

## Opis notebooków
Projekt zawiera trzy główne pliki notebooków, z których każdy realizuje inny etap przetwarzania sygnału:

1. **Demodulacja częstotliwościowa — FM_demo_dec.ipynb**

Notebook służy do demodulacji sygnałów FM.
Przed uruchomieniem należy podać trzy ścieżki:
  - **Lokalizację pliku wejściowego .wav do demodulacji** (plik odczytywany jest z formacie .wav oraz zamieniany na postać binarną)
  - **Lokalizację zapisu pliku wyjściowego** (nowy_plik.wav) po demodulacji.
2. **Demodulacja amplitudowa — AM_demo.ipynb**

Notebook realizuje demodulację sygnałów AM.
W notebooku należy podać:
  - **ścieżkę do pliku nowy_plik.wav** (wynik demodulacji FM) 
oraz odpowiednio **nazwać eksportowane tablice numpy.**

Ważna uwaga: Jeśli pojawiają się problemy z przetwarzaniem wykresów, zaleca się wyświetlenie jedynie fragmentu obwiedni sygnału, przy jednoczesnej demodulacji całego sygnału. Zmiana dotyczy linii 26, gdzie występuje instrukcja:

    raw_data = wav_file.readframes(n_frames)
   
- można zmodyfikować tę linię, aby przetwarzać jedynie określony fragment (np. 0,5 sekundy) do celów wizualizacji.

3. **Dekodowanie — my_deco_sync.ipynb**

Notebook służy do dekodowania danych obrazowych.
Przed uruchomieniem należy załadować:
- **uprzednio zapisane, nazwane tablice numpy** wygenerowane podczas demodulacji AM.

## Uwagi dodatkowe
Projekt powstał w ramach pracy inżynierskiej.
Upewnij się, że wszystkie ścieżki do plików w notebookach są dostosowane do struktury Twojego systemu.

W przypadku problemów z wyświetlaniem wykresów w AM_demo.ipynb zaleca się modyfikację linii odczytu danych, aby umożliwić wyświetlenie jedynie fragmentu obwiedni, jednocześnie przetwarzając cały sygnał.
## Licencja
Projekt jest udostępniany do użytku niekomercyjnego. Oznacza to, że możesz swobodnie przeglądać kod, jednak nie wolno wykorzystywać go w celach komercyjnych bez uzyskania odpowiedniej zgody.

## Kontakt
W przypadku pytań lub sugestii dotyczących projektu, proszę o kontakt  poprzez zgłoszenia (issues) na GitHub.
