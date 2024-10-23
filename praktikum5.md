# Praktikumi 5 aruanne

### Tegu oli operatsioonisüsteemid kursuse viienda praktikumiga
#### Viienda operatsioonisüsteemi praktikumis tuli meil testida ja võrrelda erinevaid failiõigusi Linuxis.

### Ülesanne 5-1: Minimaalsed õigused

a)

- Fail: r--
- Kataloog: --x

b)
- Fail: ---
- Kataloog: -wx

### Ülesanne 5-2: Miks chmod a=x ei ole piisav?

Lisaks käivitusõigusele on vaja lugemisõigust (r), et skripti sisu saaks lugeda

### Ülesanne 5-3

Omanimelised grupid on head, et anda iga kasutaja failidele täpsemad õigused ja vältida mitme kasutajaga õiguste konflikte

### Ülesanne 5-4

Minimaalsed õigused mida vaja oleks:

- Fail: r--
- Kataloog: r-x

<img width="400" alt="Screenshot 2024-10-23 at 21 15 45" src="https://github.com/user-attachments/assets/4aa1190b-8cd1-42da-b695-df2ac9298279">


### Ülesanne 5-5

<img width="400" alt="Screenshot 2024-10-23 at 21 31 11" src="https://github.com/user-attachments/assets/eb747d20-3c62-433a-8e6e-7a079aa6da80">


Setuid õigust kasutatakse siis, kui soovid, et programm käivituks faili omaniku õigustes, ehk siis “opetaja” õigustega, hoolimata, kes seda käivitab

### Ülesanne 5-6

Jah, setuid võib vähendada turvalisust, kuna see lubab kasutajatel ajutiselt kasutada kõrgemaid õigusi

### Ülesanne 5-7

Proovisin kolme erineva kontoga “jukuisa” tehtud faili kustutada millel on sticky bit parameeter peal
Kontod millega üritasin kustutada olid:
- opetaja

- eeroboy

- eeroj

<img width="400" alt="Screenshot 2024-10-23 at 21 41 07" src="https://github.com/user-attachments/assets/1e76dda6-45a8-4110-98eb-29108331908f">


<img width="400" alt="Screenshot 2024-10-23 at 21 42 41" src="https://github.com/user-attachments/assets/e51fe04a-f34e-4e96-8da3-9f7767bd6543">

Aga ei saanud kustutatud. Eeldan, et kui sticky bit õigused on lisatud, siis saab ainult root või faili omanik kustutada faili


### Ülesanne 5-9

<img width="400" alt="Screenshot 2024-10-23 at 21 52 08" src="https://github.com/user-attachments/assets/876d25dc-7159-4554-9491-d18b52b71252">


### Kes saab chattr +i-parameetriga faili sisu modifitseerida (kirjutada)?

root ja failiomanik saved faili sisu modifitseerida

### Milliste käskudega saate kustutada testfail-2-nimelise faili (ehk kuidas siiski kustutada +i-parameetriga faili)?

- Algselt tuleks eemaldada +i parameter
  * sudo chattr -i testfail-2
- Siis saab alles eemaldada faili
  * rm testfail-2
- Kui aga küsib adminõigusi siis peab sudo ette panemaa
