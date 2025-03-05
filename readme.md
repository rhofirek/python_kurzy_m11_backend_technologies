# Project HollyMovies

## Project description
Chceme vytvořit filmovou databázi. 
1. Zobrazit seznam filmů 
2. Zobrazit detaily filmu
3. Zobrazit seznam herců/režisérů
   1. Název
   2. žánr
   3. ...
3. Filtrování filmů např. podle žánru 
4. Hledání filmů
5. Přidávání hodnocení filmů 
6. Přidávání ocenění 
7. Zobrazení seznamu seriálů
8. Zobrazení seriálů/epizody
9. Watchlist

## Databáze
- Genre
  -[ ] name(String)
  
- Countries 
  - [ ] name (String)
  - [ ] flag (Image)

- [ ] Creators
  - [ ] first_name (String)
  - [ ] last_name (String)
  - [ ] country (-> Countries)
  - [ ] date_of_birth (Date)
  - [ ] date_of_death (Date)
  - [ ] biography (String)
  - [ ] awards (n:m -> ??)
  - [ ] acting (n:m -> Movie)
  - [ ] directing (n:m -> Movie)

  
- Movie
  - title_original (String)
  - title_cz (String)
  - genres (n:m -> Genre)
  - actors (n:M -> Creators)
  - directors (n:m -> Creators)
  - countries (n:m -> Countries)
  - lenght (Int)
  - description (String)
  - released_date (Date)
  - rating (Float)
  - images (1:n -> Images)
  - video_url (String)
- [ ] Review
  - [ ] reviewer (->User)
  - [ ] movie (-> Movies)
  - [ ] rating (Int, 1-5 hvězdiček)
  - [ ] comment (String)
  - [ ] created (Date)
  - [ ] updated (Date)

- [ ] Images
- [ ] Awards

- [ ] User (Defaultní z Django)
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
## Aplikace

### Vytvoření aplikace

>[!WARNING]
> Nesmíme zapomenout zaregistrovat aplikaci do `setting.py`
> ```angular2html
> INSTALLED_APPS = [
>    'django.contrib.admin',
>    'django.contrib.auth',
>    'django.contrib.contenttypes',
>    'django.contrib.sessions',
>    'django.contrib.messages',
>    'django.contrib.staticfiles',
>
>    'viewer',
> ]
> ``` 

### Struktura Aplikace

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