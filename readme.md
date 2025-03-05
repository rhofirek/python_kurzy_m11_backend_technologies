# Project HollyMovies

## Project description
TBD

## Django 

### Instalace
``` bash
    pip install django 
```

### Struktura projektu

- `hollymovies` -  složka projektu (obsahuje innforamce o celém projektu)
  - `settings.py` - nastavení projektu
- `manage.py` - hlavní soubor pro správu projektu


### Spuštění serveru
```bash
  python manage.py runserver
```

Případně můžeme zadat ručně port serveru
```bash
  python manage.py runserver 8001
```

# Rady pro finální projekt 

- jeden člen týmu vytvoří projekt
  - nainstaluje Django 
  ```bash
    pip isnstall django 
  ```
  - následně se vytvoří doubor `requirements.txt`
    ```bash
    pip freeze > requirements.txt
    ```
  - vytvoří Django projekt 
  ```bash
  django-admin startproject <nazev-projektu> . 
  ```
  - Nainstaluje `python-dotenv`:
  ```bash
    pip install python-dotenv
  ```
  - vytvoří soubor `.env`, který bude obsahovat citlivé informace (např. `SECRET_KEY`) a nebude součástí repozitáře
  - V `settings.py` nahradíme SECRET_KEY odkazem do `.env`
  - Vytvoří git repozitář
    - vytvoří `.gitignore` soubor 
    ```git
    /.idea
    /.env
    /db.sqlite3
    ```
    - odešle repozitář na GitHub
    - nasdílí s ostatními členy týmu
    - nastavé collaboratores
- Ostatní členové 
  - naklonují projekt
  - vytvoří virtuální prostředí `.venv`
  - nainstalujeme si potřebné balíčky ze soouboru `requirements.txt`
    ```bash
    pip install -r requirements.txt
    ```
  - vytvoří si soubor `.env` a vytvoří si vlastní SECRET_KEY