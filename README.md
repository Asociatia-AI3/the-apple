# Mărul

Acest repository conține codul Arduino pentru controlul câmpurilor de vopsea electroluminiscentă Lumilor aplicată pe un măr de lemn de 50 cm. Proiectul utilizează porturile PWM ale Arduino pentru a varia intensitatea luminii emise de vopsea, creând efecte vizuale dinamice.

**Componente principale:**

* **Cod Arduino:** Schițe Arduino (.ino) care gestionează semnalele PWM către controlerul Lumilor.
* **Diagramă de conectare (opțional):** Un fișier care ilustrează modul în care Arduino este conectat la controlerul Lumilor.
* **Instrucțiuni (opțional):** Un ghid scurt despre cum să încarci codul pe Arduino și să conectezi componentele.

**Scopul proiectului:**

Demonstrarea utilizării Arduino pentru a controla creativ vopseaua electroluminiscentă Lumilor pe un obiect tridimensional, în acest caz, un măr de lemn de dimensiuni semnificative. Prin modularea semnalelor PWM, se pot obține efecte de pulsație, estompare și alte animații luminoase captivante.

Schema electrică de principiu este aici:
<img width="1075" alt="the-apple" src="https://github.com/user-attachments/assets/5237c5a5-828c-4d76-aec6-3fd5d06f3191" />


**Cuvinte cheie:** Arduino, PWM, Lumilor, vopsea electroluminiscentă, artă cinetică, sculptură luminoasă, proiect DIY.

## Instrucțiuni de Setare și Rulare

Această secțiune te ghidează prin pașii necesari pentru a configura mediul de dezvoltare și a rula codul pe placa ta Arduino.

### Cerințe

Înainte de a începe, asigură-te că ai următoarele instalate:

* **Arduino IDE** sau **Visual Studio Code cu extensia PlatformIO:** Recomandăm PlatformIO pentru o gestionare mai avansată a proiectelor și a dependențelor. Poți descărca PlatformIO IDE de aici: [https://platformio.org/install](https://platformio.org/install)
* **Placa Arduino:** O placă Arduino compatibilă (de exemplu, Arduino Uno, Nano, etc.) cu suficiente porturi PWM disponibile.
* **Librăria `arduinoFFT`:** Această librărie este utilizată pentru analiza frecvenței (dacă codul tău o folosește). Dacă nu este inclusă direct în cod, va trebui să o instalezi.

### Instalare

**Folosind Arduino IDE:**

1.  Deschide Arduino IDE.
2.  Mergi la `Sketch` -> `Include Library` -> `Manage Libraries...`.
3.  În fereastra Library Manager, caută `arduinoFFT` (dacă este necesară).
4.  Instalează librăria `arduinoFFT` de către `TFTLCDCyg`.
5.  Copiază fișierele `.ino` din acest repository în folderul tău de proiect Arduino.
6.  Conectează placa Arduino la computer prin cablul USB.
7.  Selectează placa corectă din `Tools` -> `Board:` și portul serial corect din `Tools` -> `Port:`.
8.  Încarcă schița pe placa Arduino făcând clic pe butonul `Upload` (săgeata spre dreapta).

**Folosind PlatformIO (recomandat):**

1.  Deschide Visual Studio Code.
2.  Instalează extensia PlatformIO IDE dacă nu ai făcut-o deja.
3.  Deschide folderul acestui repository ca un nou proiect PlatformIO (`File` -> `Open Folder...`). PlatformIO ar trebui să detecteze automat structura proiectului.
4.  PlatformIO va gestiona automat dependențele specificate în fișierul `platformio.ini`. Dacă librăria `arduinoFFT` este necesară și nu este inclusă, adaugă următoarea linie în secțiunea `[env:your_arduino_board]` (înlocuiește `your_arduino_board` cu numele mediului tău Arduino):
    ```ini
    lib_deps =
        arduinoFFT
    ```
5.  PlatformIO va descărca și instala automat librăria la următoarea compilare.
6.  Conectează placa Arduino la computer prin cablul USB.
7.  În bara de jos a ferestrei VS Code, selectează mediul corespunzător plăcii tale Arduino.
8.  Încarcă codul pe placa Arduino făcând clic pe pictograma de încărcare (săgeata spre dreapta) din bara de activități PlatformIO.

### Rulare

1.  După ce codul a fost încărcat cu succes pe placa Arduino, deconectează placa de la computer (dacă este necesar pentru configurarea finală).
2.  Conectează placa Arduino la controlerul Lumilor conform diagramei de conectare (dacă este furnizată). Asigură-te că alimentarea este corectă pentru toate componentele.
3.  În funcție de codul încărcat, vei observa efecte luminoase pe mărul vopsit cu vopsea electroluminiscentă. Intensitatea luminii ar trebui să varieze în funcție de semnalele PWM generate de Arduino.
4.  Dacă codul tău utilizează analiza FFT (prin librăria `arduinoFFT`), acesta ar putea reacționa la sunete sau alte intrări, modulând lumina în consecință. Asigură-te că senzorii de intrare (de exemplu, microfon) sunt conectați corect dacă este cazul.

### Probleme Comune

* **Librăria `arduinoFFT` nu este găsită:** Verifică dacă ai instalat corect librăria în Arduino IDE sau dacă ai adăugat-o în `platformio.ini` pentru PlatformIO.
* **Placa Arduino nu este detectată:** Asigură-te că driverele plăcii Arduino sunt instalate corect pe computer și că ai selectat portul serial corect.
* **Nicio lumină de la vopseaua Lumilor:** Verifică conexiunile dintre Arduino și controlerul Lumilor, precum și alimentarea controlerului. Asigură-te că pinii PWM specificați în cod corespund pinilor conectați la controler.
* **Comportament neașteptat al luminii:** Revizuiește codul Arduino pentru a te asigura că logica de control PWM este cea dorită. Verifică valorile minime și maxime ale PWM și modul în care acestea sunt mapate la intensitatea luminii.

Pentru orice întrebări sau probleme, te rog să deschizi un "issue" în acest repository.
