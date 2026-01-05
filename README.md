# Speedrun Overlay

Jednoduchý HTML/JS overlay se stopkami pro speedruny.  
Určeno pro použití jako **OBS Browser Source** nebo samostatně v prohlížeči.

Bez knihoven, bez backendu, bez závislostí.

---

## Funkce

- Stopky s přesností na milisekundy (`performance.now`)
- Aktuální datum a čas
- Automatické ukládání **PB (Personal Best)** do `localStorage`
- Zvýraznění nového PB (žlutá barva + krátký flash)
- Ovládání myší, dotykem i klávesnicí
- Automatická pauza při ztrátě focusu okna

---

## Ovládání

### Start / Pause
- Klik na tlačítko **Start / Pause**
- Klávesa **Space**

Chování:
- `Start` spustí běh
- `Pause` zastaví běh **a vyhodnotí PB**

> Pauza zároveň znamená konec běhu. Resume neexistuje.

---

### Reset PB
- Podrž text **PB** po dobu 2 sekund
- PB se smaže z `localStorage`

Bez potvrzovací hlášky.

---

## Stavový model

IDLE → RUNNING → PAUSED
- `IDLE` – výchozí stav
- `RUNNING` – běží stopky
- `PAUSED` – běh ukončen, čeká na nový start

---

## PB logika

- PB se vyhodnocuje při ukončení běhu (`Pause`)
- Nový PB přepíše starý pouze pokud je čas kratší
- PB je uložen lokálně v prohlížeči

Omezení:
- Krátký nebo omylem spuštěný běh může přepsat PB

---

## Použití v OBS

OBS Studio: https://obsproject.com/

1. Přidej **Browser Source**
2. Do pole **URL** vlož:  
   `https://shipeast.github.io/Stopwatch/`
3. Nastav šířku cca **720 px**
4. Zapni **Transparent Background**

Doporučeno vypnout interakci myší, pokud ovládáš klávesnicí.

---

## Technické detaily

- Časování: `requestAnimationFrame`
- Ukládání dat: `localStorage`
- Bez externích knihoven
- Transparentní pozadí
- Responzivní layout

---

## Omezení

- Žádné splity
- Žádný manuální reset času (nutný reload stránky)
- Žádný export PB
- Pouze jeden běh bez resume

---

## Licence

Používej, upravuj, rozšiřuj dle potřeby.
