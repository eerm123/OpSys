# Praktikumi 7 aruanne

### Tegu oli operatsioonisüsteemid kursuse seitsmenda praktikumiga
#### Seitsmenda operatsioonisüsteemi praktikumis saime me uurida kuidas kasutada lokaalseidkettaid kui ka võrgukettaid Windowsi ja Linuxi keskkonnas

#### Ülesanne 1

1. kõvakettad ja SSD-d, vajavad lähtestamist, et neid saaks uues süsteemis kasutada. see loob meile andmestruktuurid ja loogilised partitsioonid, ilma lähtestamiseta ei pruugi operatsioonisüsteem kõvaketta sisu tuvastada

2. 
* toetab suuremat mahtu
* rohkem partitsioone: GPT suudab luua kuni 128 partitsioon, samalajal kui MBR suudab 4
* MBR kettad kasutavad standardset BIOS-i partitsioonitabelit. (GPT) kettad kasutavad ühtset laiendatavat püsivara liidest UEFI

#### Ülesanne 2

https://kodu.ut.ee/~eerojurg/opsys/hdd.png


#### Ülesanne 3

￼<img width="400" alt="Screenshot 2024-11-06 at 15 36 57" src="https://github.com/user-attachments/assets/792559a3-112e-451b-8782-97bdaddd7b70">


#### Ülesanne 5 
Kuna minu Macbook-il ei olnud USB auku, siis mõtlesin, et loon endale virtuaalse USB: /dev/sda1: UUID="0E1B-0BB0" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="30418575-81f4-4a88-af5a-2692601a2aae"


1. Mida mõjutasid mount-käsu parameetrid -o ro ja -t auto? - (-o ro) parameeter määrab, mul USB-seadme ära nii, et sisu saab ainult lugeda - (-t auto) parameeter määrab, et operatsioonisüsteem valiks automaatselt sobiva failisüsteemi tüübi

2. Leidke mount-käsu väljundist üles, mis väärtusega asendas Ubuntu auto-parameetri?
jurgenson24@jurgenson24:~$ mount | grep /media/usb
/dev/sda1 on /media/usb type vfat (ro,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=iso8859-1,shortname=mixed,errors=remount-ro)


#### Ülesanne 6

￼<img width="400" alt="Screenshot 2024-11-06 at 22 17 34" src="https://github.com/user-attachments/assets/797d79a5-3b20-48ea-ba98-d2a6e23804f9">
<img width="400" alt="Screenshot 2024-11-06 at 22 18 39" src="https://github.com/user-attachments/assets/e59842ca-e08e-4134-b39f-7124eafac8da">

￼
