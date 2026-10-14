# Bouwplan – Slimme Notitieboek
*(basisversie, standalone, vrolijk · efficiënt · doelgericht)*

## Designprincipes

### Vrolijk
Zachte, warme kleuren. Veel witruimte. Positieve microcopy. Subtiele beloningen bij afronden (korte check-animatie, vriendelijke toast). Geen corporate grijs.

### Efficiënt
Capture is altijd het snelste pad. Keyboard-first. Eén primaire actie per scherm. Geen verplichte velden of rituelen. Optimistic UI (alles reageert direct).

### Doelgericht
De gebruiker ziet altijd “wat is mijn volgende stap?”. Progressie per order is zichtbaar. De app helpt vooruit, niet om te administreren.

---

## Visuele richting

- **Kleuren**: lichte achtergrond (#FAFAFA), primaire actie in fris teal/blauw, stages in zachte herkenbare kleuren (groen, oranje, blauw, paars), positieve accenten in warm geel/oranje.
- **Typografie**: vriendelijke sans (Inter of system font).
- **Vorm**: afgeronde hoeken, zachte schaduwen, ruime touch targets.
- **Feedback**: korte animaties bij “Klaar”, vriendelijke toasts (“Idee vastgelegd”, “Mooi, die is klaar”), subtiele progressie-indicatie.

---

## Kernschermen

### 1. Home / Vandaag (startscherm)
- Groot, altijd zichtbaar capture-veld bovenaan.
- Direct daaronder: top 3–5 next-actions (duidelijk gerangschikt).
- Elke taak toont stage-badge + order (indien gekoppeld) + prioriteit.
- Eén-klik acties: Klaar / Later / Notitie.
- Kleine interrupt-tray alleen als er écht iets urgents binnenkomt.

### 2. Notities & Ideeën
- Notebook-achtige stream of simpele doorzoekbare lijst.
- Alles wat geen taak is, landt hier.
- Eén tik “→ Taak” om een idee om te zetten.
- Zoekbalk prominent.

### 3. Orders / Stages
- Overzicht van actieve orders als vrolijke kaarten.
- Per order: mini-progress van de 4 stages (Goedkeurtekeningen → Revisies → Productie klaar maken → Map maken).
- Klik op een stage om de open taken te zien.
- Nieuwe order aanmaken is optioneel en snel.

### 4. Focus-modus (optioneel in v1, wel voorbereid)
- Eén taak groot in beeld.
- Rustige achtergrond, optionele timer.
- Terug naar Home met één tik.

---

## Gebruikersflows (notebook-snelheid)

1. **Iets vastleggen** (3–8 seconden)  
   Typ of spreek → Enter.  
   AI (of regelgebaseerd in eerste fase) bepaalt: taak of notitie, stage, order.  
   Gebruiker hoeft niets te kiezen.

2. **Werken vanuit Home**  
   Open app → zie top-taken → klik Klaar → volgende verschijnt.  
   Geen navigatie nodig voor 80% van het gebruik.

3. **Idee of opmerking**  
   Gewoon schrijven. Later terugvinden in Notities of gekoppeld aan de order.

4. **Order overzicht**  
   Eén tik naar Orders → zien welke stage aandacht nodig heeft.

---

## Functionele scope (basisversie)

### Must-have
- Universal capture (tekst)
- Automatische classificatie taak vs notitie
- Herkenning van de 4 stages + ordernummer
- Dynamische prioriteit (urgency, stage, keywords)
- Home (gerangschikte taken)
- Notities-overzicht + omzetten naar taak
- Orders-overzicht met stage-progress
- Local persistence (localStorage / IndexedDB)
- Klaar / verwijderen / later

### Nice-to-have in v1
- Spraak-capture (browser Speech API)
- Eenvoudige focus-modus
- Zoeken over alles
- Lichte animaties en positieve feedback

### Bewust niet in v1
- Externe kalender-koppelingen
- Accounts / login
- Complexe AI-aanroepen (kan later)

---

## Technische aanpak (voor Grok Build)

- **Frontend**: React + Vite of Next.js (of pure HTML/JS als snelste start).
- **Styling**: Tailwind CSS (snel vrolijke, consistente UI).
- **State & opslag**: Zustand of React Context + localStorage/IndexedDB (local-first).
- **Classificatie**: eerst regelgebaseerd (keywords + prefixes), later optionele AI-call.
- **PWA**: installeerbaar op telefoon en desktop voor snelle toegang.
- **Structuur**: componenten voor CaptureBar, TaskItem, NoteItem, OrderCard, StageProgress.

---

## Bouwfasen

### Fase 1 – Kern (testbaar in dagen)
Capture + localStorage + Home-lijst + Notities + basis stages.  
Doel: notebook-gevoel valideren.

### Fase 2 – Structuur & progressie
Orders-overzicht met stage-progress, betere prioritering, positieve feedback en animaties.  
Doel: doelgericht en vrolijk aanvoelen.

### Fase 3 – Verfijning
Focus-modus, zoeken, spraak, kleine UX-polish, eventuele AI-classificatie.  
Doel: productie-waardige basisversie.

---

## UI-details die het verschil maken

- Capture-veld is groot en uitnodigend (“Wat wil je vastleggen?”).
- Lege staten zijn vriendelijk en actiegericht.
- Bij “Klaar” een korte, vrolijke animatie + toast.
- Stage-progress als mini-stappenbalk of gekleurde dots.
- Prioriteit is subtiel zichtbaar (niet schreeuwerig).
- Alles is in het Nederlands, met een lichte, positieve toon.

---

Dit bouwplan is concreet genoeg voor Grok Build om direct mee aan de slag te gaan, en houdt de essentie vast: een slim notitieboek dat vrolijk aanvoelt, weinig tijd kost en je helpt je werk gedaan te krijgen.