#  Task Manager (Python + MySQL)

Jednoduchý program pro správu úkolů napsaný v Pythonu s využitím MySQL databáze. Součástí projektu jsou automatické testy pomocí pytest.

---

##  Funkce

- Přidání úkolu (název a popis jsou povinné)
- Zobrazení úkolů (zobrazí pouze úkoly ve stavu `nezahájeno` nebo `probíhá`)
- Aktualizace stavu úkolu (umožňuje změnit stav úkolů na `probíhá` nebo `hotovo`)
- Odstranění úkolu (umožňuje smazat libovolný úkol z databáze)

---

##  Struktura projektu

src/task_manager.py  
tests/  
.env.example  
.env.test.example  
README.md  
requirements.txt

---

##  Požadavky

- Python 3.13.7
- MySQL

## Instalace

- Naklonujte repozitář nebo stáhněte projekt

- Nainstalujte závislosti:
```bash
pip install -r requirements.txt
```  

---

## ⚙️ Konfigurace

1. Vytvoř `.env` a `.env.test` podle `.env.example` souborů

2. Nastav přístup k MySQL

3. Databáze i tabulka se vytvoří automaticky při spuštění aplikace

##  Spuštění aplikace

python src/task_manager.py

---

##  Testování

Spuštění testů:

pytest tests/

Testy obsahují:
- pozitivní scénáře (správné fungování)
- negativní scénáře (chybný vstup)

Použité nástroje:
- pytest fixtures (testovací databáze)
- unittest.mock (simulace vstupu)
- capsys (zachycení výstupu)

Testy používají samostatnou databázi a po každém testu se provádí TRUNCATE TABLE ukoly

---

##  Databáze

Tabulka `ukoly` obsahuje:
- id – primární klíč  
- nazev – název úkolu  
- popis – popis  
- stav – (nezahájeno, probíhá, hotovo)  
- datum_vytvoreni – přidá se automaticky

---

##  Poznámky

- Aplikace běží v terminálu
- Vyžaduje běžící MySQL server
- Testy používají oddělenou databázi