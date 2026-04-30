# Duel Game

## Descriere

Acest proiect este un joc de tip turn-based duel realizat in TypeScript. Ideea principala este simularea unei lupte dintre doua personaje generate aleator, fiecare avand valori pentru atac, aparare si o abilitate speciala. Programul poate fi rulat in doua moduri: un duel simplu, afisat pas cu pas in terminal, sau un mod de simulare in care sunt rulate 1000 de lupte pentru a observa statistici generale.

Proiectul a fost facut astfel incat sa fie usor de urmarit si de testat din consola. Logica este impartita pe fisiere separate pentru personaje, abilitati, lupta, afisare si simulare.

## Ce face programul

- genereaza doua personaje cu valori random pentru attack si defense
- fiecare personaj porneste cu 100 HP
- abilitatile pot influenta atacul sau apararea in timpul luptei
- programul decide aleator cine incepe primul
- lupta continua pe runde pana cand unul dintre personaje ajunge la 0 HP
- exista si un mod de simulare pentru a calcula win rate si durata medie a luptelor

## Abilitati implementate

- Damage Reduction
  Reduce damage-ul primit la jumatate atunci cand se activeaza.
- Power Strike
  Mareste damage-ul produs de atacator atunci cand se activeaza.
- Second Wind
  Ofera un mic heal atunci cand personajul ar scadea sub un anumit prag de viata.
- Revenge Reflex
  Blocheaza atacul si reflecta o parte din damage inapoi catre adversar.

## Structura proiectului

```text
duel_game/
|-- src/
|   |-- abilities.ts
|   |-- character.ts
|   |-- combat.ts
|   |-- display.ts
|   |-- index.ts
|   |-- simulation.ts
|   |-- utils.ts
|-- dist/
|-- node_modules/
|-- package.json
|-- package-lock.json
|-- tsconfig.json
|-- testing_commands
|-- README.md
```

## Tehnologii folosite

- TypeScript
- Node.js
- ts-node

## Cerinte

Pentru a rula proiectul este nevoie de:

- Node.js instalat
- npm instalat
- un terminal deschis in folderul proiectului

## Instalare

1. Se deschide terminalul in folderul proiectului.
2. Se instaleaza dependentele:

```powershell
npm install
```

3. Se compileaza proiectul:

```powershell
npm run build
```

## Rulare

### 1. Duel simplu

Ruleaza o singura lupta si afiseaza toate rundele in terminal.

```powershell
npm start
```

### 2. Simulare

Ruleaza 1000 de lupte si afiseaza statistici generale.

```powershell
npm run sim
```

### 3. Duel cu abilitati fixe

Fiecare personaj isi pastreaza abilitatea initiala pe toata durata luptei.

```powershell
npm run fixed
```

### 4. Simulare cu abilitati fixe

Ruleaza 1000 de lupte in care abilitatile nu se schimba intre runde.

```powershell
npm run sim-fixed
```

## Comenzi utile

```powershell
npm install
npm run build
npm start
npm run sim
npm run fixed
npm run sim-fixed
```

## Posibila problema in PowerShell

Pe unele sisteme Windows este posibil ca scripturile sa nu porneasca direct din PowerShell. Daca apare o eroare legata de execution policy, se poate deschide PowerShell cu drepturi de administrator si se poate rula:

```powershell
Set-ExecutionPolicy Unrestricted
```

Dupa aceea se pot incerca din nou comenzile de mai sus.

## Cum functioneaza pe scurt

La inceputul jocului sunt create doua personaje. Fiecare primeste automat valori random pentru atac si aparare. In timpul luptei, damage-ul de baza se calculeaza din diferenta dintre attack-ul atacatorului si defense-ul aparatorului. Peste acest damage intervin abilitatile speciale, care pot modifica rezultatul final al unui atac.

In modul normal, abilitatile se pot schimba de la o runda la alta. In modul fixed, fiecare personaj ramane cu abilitatea primita la inceput. Modul simulation repeta lupta de 1000 de ori pentru a observa rezultate medii, nu doar un singur caz.

## Scopul proiectului

Scopul acestui proiect a fost sa exersez lucrul cu TypeScript, organizarea codului pe module si implementarea unei logici simple de joc in consola. In acelasi timp, proiectul poate fi folosit si pentru a observa cum mici diferente de stats si abilitati pot influenta rezultatul unei lupte.

## Autor

Proiect realizat ca exercitiu / proiect de laborator pentru practica in TypeScript si Node.js.
