# Driver pentru Motoare Pas cu Pas Bipolare (L297 & L298N)

Proiect realizat în cadrul disciplinei **Componente Mecatronice Digitale** (Anul 3 – Mecatronică și Robotică, FIMM, UPB).

## 📌 Descriere Proiect
Acest proiect vizează proiectarea, simularea și realizarea unui circuit de comandă (driver) dedicat motoarelor pas cu pas bipolare. Sistemul este capabil să gestioneze secvențele de fază necesare mișcării controlate, oferind o soluție robustă de poziționare în buclă deschisă.

## 🚀 Arhitectură și Funcționalități

### 1. Etajul de Comandă și Putere
* **Controler L297:** Funcționează ca „creier” al sistemului, generând secvențele corecte de fază (A, B, C, D) și gestionând controlul curentului prin PWM Chopper.
* **Driver L298N:** O punte H duală capabilă să amplifice semnalele logice și să furnizeze curentul necesar pentru acționarea bobinelor motorului.
* **Protecție Inductivă:** Integrarea a 8 diode de comutație rapidă pentru protejarea tranzistorilor împotriva tensiunilor autoinduse.

### 2. Gestiunea Alimentării Multi-nivel
Sistemul utilizează o sursă principală de 36V DC, din care sunt derivate trei praguri de tensiune specifice:
* **5V (LM7805):** Alimentarea logicii digitale a circuitelor integrate.
* **12V (LM7812):** Alimentarea stabilă a circuitului de ceas.
* **24V Ajustabil (LM317):** Tensiune dedicată bobinelor motorului, calculată prin divizor rezistiv (aprox. 23.75V).

### 3. Generatorul de Semnal (Clock)
* **NE555 (Regim Astabil):** Implementarea unui oscilator pentru generarea impulsurilor de ceas care dictează viteza motorului.
* **Parametri:** Configurat pentru o frecvență de aproximativ 27.86 Hz, asigurând o mișcare vizibilă în etapele de testare.

## 🛠 Validare și Testare
* **Simulare Software:** Întreaga schemă a fost proiectată și validată în **Proteus Design Suite**, monitorizând formele de undă pe osciloscopul digital pentru a confirma corectitudinea fazelor.
* **Prototipare Fizică:** Testarea soluției pe breadboard, verificarea integrității circuitelor și măsurarea tensiunilor de ieșire cu multimetrul digital.

## 📂 Componente Principale
* Motor pas cu pas bipolar.
* Circuite Integrate: L297, L298N, NE555, LM317, LM7805, LM7812.
* Diode Schottky și componente pasive (rezistoare de putere, condensatoare de filtrare).

---
*Autor: Neagu Mihnea – Student la Facultatea de Inginerie Mecanică și Mecatronică (FIMM)*.
