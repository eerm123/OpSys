# Praktikum 9 
### Selles praktikumis tutvusime operatsioonisüsteemi ressurssidega, siin on minu tulemused

| **Küsimus**                                 | **Linux vastus**                                    | **Windows vastus**                                | **Linuxi käsk** | **Windowsi käsk** |
|---------------------------------------------|---------------------------------------------|-------------------------------------------|--------------------------------|----------------------------------|
| **Mitu protsessi kokku arvutis käib?**      | 201                                         | 141                                       | ps -aux wc -l              | Task Manager → Performance       |
| **Milline on kõige esimesena käivitatud protsess?** | `/sbin/init`                        | `smss.exe`                                | ps axo pid,cmd head -n 2   | Process Explorer → Start Time    |
| **Milliste kasutajate protsesse arvutis käib?** | `jurgenson24, sys, root `               | `Eero`                                    | ps -eo user sort uniq`     | Task Manager → Details → User    |
| **Kui kaua on arvuti järjest töötanud?**    | `up to 14 minutes`                          | `0.00.18.10`                              | uptime                     | Task Manager → Performance → CPU |
| **Milline protsess käivitati kõige hiljem?**| `gjs /usr/share/gnome-shell/`               | `msedgeview2.exe`                         | ps -eo pid,cmd,etime sort -k3 -r  | Process Explorer → Start Time    |
| **Milline protsess võtab kõige rohkem protsessoriaega ja kui palju?** | `gnome-shell (0:10.72s)`        | `WindowsTerminal (307.2s)`  | top -o %CPU head -n 10     | Get-Process Sort-Object CPU -Descending Select-Object -First 1 |
| **Milline protsess võtab kõige rohkem virtuaalmälu?** | `/usr/bin/gnome-shell`            | `msedgewebview2`                          | ps -eo vsz,pid,cmd --sort=-vsz | Get-Process Sort-Object VM -Descending Select-Object -First 1 |
| **Milline protsess võtab kõige rohkem füüsilist mälu?** | `/usr/bin/gnome-shell`          | `powershell`                              | ps -eo rss,pid,cmd --sort=-rss | Get-Process Sort-Object WorkingSet -Descending Select-Object -First 1" |
| **Kui palju füüsilisest mälust on vaba ja kui palju hõivatud?** | `Used: 975Mi, Free: 966Mi` | `Total: 4 087 MB, Available: 1 133 MB`    | free -h                   | systeminfo findstr /C:"Available Physical Memory" /C:"Total Physical Memory" |
| **Kui palju on põhikettal vaba ruumi?**     | `12G (50%)`                                  | `24GB (40%)`                              | df -h /                   | chkdsk C:/                            |
| **Milline on suurim fail ja kaust?**        | `Fail: ./snap/firefox/common/.mozilla/firefox/dr9xbbzl.default/storage/permanent/chrome/idb/3870112724rsegmnoittet-es.sqlite  Kaust: ./snap` | `Fail: Tartu Ülikool\Võnkumine  ja laine aines.ppt Kaust: \Users\`  | Kaust: sudo du -a sort -n -r head -n 10 Fail: find -type f -printf '%s %p\n' sort -nr head -10 | WinDirStat |
| **SHA1sum protsessori kasutus (Linux)**     | `sha1sum /dev/zero teeb rohkem user protsessi ehk kulub us protsessori aega ja sha1sum /dev/urandom teeb rohkem süsteemi põhist, ehk kulub sy protsessori aega`| | `sha1sum /dev/zero` ja `/dev/urandom` | |
| **Milline protsess kõige rohkem salvestusseadmele kirjutab?** |                           | `System`                                  |                           | Resource Monitor → Disk          |
| **Millisesse faili eelmise küsimuse protsess kõige rohkem kirjutab?** |                   | `pagefile.sys`                            |                           | Resource Monitor → Disk          |
| **Milline protsess kõige rohkem salvestusseadmelt loeb?** |                               | `firefox.exe`                             |                           | Resource Monitor → Disk          |
| **Millisest failist eelmise küsimuse protsess kõige rohkem loeb?** |                      | `pagefile.sys`                            |                           | Resource Monitor → Disk          |
| **Milline protsess tekitab suurima võrguliikluse?** |                                     | `firefox.exe`                             |                           | Resource Monitor → Network       |  

**Milline protsess tekitab suurima võrguliikluse?:**

- Kohalik IP-aadress: 192.168.64.3
- Kohalik port: 50548
- Kaug IP-aadress: 193.40.5.90
- Kaugport: 443
- Latents: 46 ms
- Võrguliikluse kogumaht: Send: 79 B/sec, Receive: 82 B/sec

<img width="1000" alt="Screenshot 2024-11-20 at 21 44 44" src="https://github.com/user-attachments/assets/bdd123f6-07fb-476e-905e-8611e0587962">

<img width="1000" alt="Screenshot 2024-11-20 at 15 37 48" src="https://github.com/user-attachments/assets/aba93e1f-ba9f-43ad-a9da-7f3dfaa846ea">

---

**Sõbra arvuti aegluse tuvastamine:**

Valin Linuxi:

- **Linux:**
  - **Käsk "top":**
    - Sellega vaatadata veergu %CPU – see näitab protsessorikasutuse protsenti iga protsessi kohta
    - Leida protsessid, millel on kõrge %CPU väärtus
    - Üldise koormuse jälgimiseks vaadata rida load average
    - Kui koormuse väärtus on suurem kui protsessorite arv, siis protsessor on ülekoormatud
  - **Käsk "iotop":**
    - Veerud DISK READ ja DISK WRITE näitavad protsesside lugemis- ja kirjutamistoimingute kiirust kettal
    - Sorteerida protsessid, et näha kõige aktiivsemat kettakasutust
  - **Käsk "free -h":**
    - Vaadata rida Mem: ja selle kahte väärtust -> Used: näitab, kui palju füüsilisest mälust on kasutusel -> Available: näitab, kui palju mälu on saadaval uutele protsessidele
    - Kui Available väärtus on väga madal, võib süsteem töötada aeglaselt mälu puudumise tõttu

