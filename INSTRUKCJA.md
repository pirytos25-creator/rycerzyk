# Strażnik Torunia

Interaktywna scena 3D z rycerzem, dziedzińcem i dwoma treningami. Postać ma teksturowaną twarz, metalową zbroję z ornamentami, kolczugę, skórzane pasy, miecz, tarczę herbową, łuk i animowany płaszcz.

## Uruchomienie

Otwórz **straznik-torunia.html** w Edge lub Chrome. Wszystkie biblioteki, modele i tekstury gry są zapisane wewnątrz pliku. Gra działa lokalnie i bez internetu. W przeglądarce musi być dostępny WebGL 2 i włączona akceleracja sprzętowa.

Kliknij **Wejdź na dziedziniec**. Przycisk **Przejdź do treningu** przenosi rycerza do strefy wybranej broni. Menu **Obejrzyj rycerza** pozwala obracać postać, przybliżać widok i pobrać model GLB.

## Sterowanie

| Czynność | Sterowanie |
| --- | --- |
| Ruch | WASD lub strzałki |
| Bieg | Shift |
| Wybór miecza / łuku | 1 / 2 lub przyciski ekwipunku |
| Cięcie | Lewy przycisk myszy lub spacja |
| Strzał | Przytrzymaj i puść lewy przycisk myszy lub spację |
| Obrót kamery | Prawy przycisk myszy + ruch myszy; Q / E obraca poziomo |
| Blok tarczą | F |
| Przybliżenie | Kółko myszy |
| Pauza i pomoc | Escape lub „?” |

W treningu miecza podejdź do manekina i ustaw się przodem. Celne cięcie daje 25 punktów; co trzecie trafienie w danego manekina daje dodatkowe 50 punktów. Zadanie treningowe: 10 celnych cięć.

W treningu łuczniczym celuj środkiem ekranu. Dłuższy naciąg zwiększa prędkość strzały. Pola tarczy dają 25, 50, 75 lub 100 punktów. Zadanie treningowe: 5 trafień. Strzały nie kończą się. Można ćwiczyć również po ukończeniu zadań.

Dźwięk włącza się przyciskiem w prawym górnym rogu. W menu pauzy można przełączyć jakość na wydajną i wyzerować trening.

## Modele i projekt

- **rycerz-torunski.glb** — wariant z mieczem i tarczą; animacje bezczynności, chodu i cięcia.
- **rycerz-lucznik.glb** — wariant z łukiem; animacje bezczynności, chodu i naciągu.
- **dziedziniec-torunski.glb** — geometria i materiały dziedzińca.
- **projekt-zrodlowy.zip** — kod, oryginalne zasoby twarzy, konfiguracja i skrypt budowania.
- **LICENCJE.txt** — autorzy, źródła i warunki wykorzystania zasobów.

Modele GLB można importować do Blendera lub silnika 3D obsługującego glTF. Jednostką jest metr. Zbroja i kończyny są połączone hierarchią ruchomych węzłów; animacje sterują obrotem części. Płaszcz i flagi poruszają się proceduralnie w grze, a w GLB zachowują zapisany kształt. Efekty światła, kolizje i zasady treningu są częścią aplikacji HTML. Dziedziniec używa rozszerzenia EXT_mesh_gpu_instancing dla roślinności.

Styl: autorska interpretacja strażnika Torunia i dziedzińca inspirowanego ceglanym gotykiem. Relief trzech wież jest stylizowanym motywem miejskim.

## Budowanie ze źródeł

Rozpakuj projekt, przejdź do katalogu `work`, a następnie uruchom:

```powershell
npm install
npm run build
```

Wynik pojawi się w sąsiednim katalogu `outputs`. `npm run serve` uruchamia lokalny podgląd na `http://127.0.0.1:4318`.

Sprawdzono: uruchamianie z dysku bez serwera, ruch, cięcia i premię, naciąg łuku, trafienie w tarczę, pauzę oraz eksport GLB. Modele sprawdzane są narzędziem Khronos glTF Validator.
