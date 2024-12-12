# Praktikum 12
### Siin praktimus saime hea ülevaate käsurea skriptide loomisest linuxis.


### Ülesannete (3-6):
Esimene skript:

![Screenshot 2024-12-04 at 14 48 44](https://github.com/user-attachments/assets/5643aa82-41d3-42f0-b971-b5700754799c)

Kood:
```
echo "Sisesta nimi: "
read nimi
echo "Sisesta eriala: "
read eriala
echo "Sisesta matriklinumber: "
read matrik

echo "Sisestati: $nimi"
echo "Sisestati: $eriala"
echo "Sisestati: $matrik"
```

Teine skript:

![Screenshot 2024-12-04 at 15 06 15](https://github.com/user-attachments/assets/cf8663a4-975f-4654-84d2-7a1fa7149e51)

Kood:
```
#!/bin/bash

if [ $# -ne 2 ]; then
  echo "<fail1> <fail2>"
  exit 1
fi

laiend1=$1
laiend2=$2

for fail in *.$laiend1; do
  if [ -f "$fail" ]; then
    uusfail="${fail%.$laiend1}.$laiend2"
    mv "$fail" "$uusfail"
    echo "Fail \u00fcmber nimetatud: $fail -> $uusfail"
  fi
done
```

Kolmas skript:

![Screenshot 2024-12-04 at 15 17 07](https://github.com/user-attachments/assets/e9a33050-8b3d-402c-854f-c842bcf1936b)

Kood:
```
#!/bin/bash

if [ $# -ne 1 ]; then
  echo "<protsessi nimi>"
  exit 1
fi

protsessinimi=$1

ps -A | grep "$protsessinimi" | while read -r rida; do
  line=$(echo " $rida" | tr -s ' ')  
  pid=$(echo "$line" | cut -d ' ' -f2)
  nimi=$(echo "$line" | cut -d ' ' -f5-)
  echo "PID: $pid, Nimi: $nimi"
done
```
Neljas skript:

![Screenshot 2024-12-04 at 15 20 57](https://github.com/user-attachments/assets/762bea58-17d4-4079-83e2-904f11d09bc7)

Kood:
```
#!/bin/bash

astenda() {
  numbah1=$1
  aste=$2
  tulemus=1

  if [ $aste -eq 0 ]; then
    echo 1
    return
  fi

  for (( i=0; i<$aste; i++ )); do
    tulemus=$(($tulemus * $numbah1))
  done

  echo $tulemus
}

tulemus=$(astenda 9 5)
echo "9^5 = $tulemus"
```

### Ülesanne 7

<img width="600" alt="Screenshot 2024-12-12 at 19 18 02" src="https://github.com/user-attachments/assets/9c0dd4a3-7ec8-489b-82c8-777db22e4fa0" />

<img width="600" alt="Screenshot 2024-12-12 at 19 18 27" src="https://github.com/user-attachments/assets/ffd65663-f72e-4314-8091-36af80fc972a" />

<img width="600" alt="Screenshot 2024-12-12 at 19 18 49" src="https://github.com/user-attachments/assets/4333d25d-7d99-4b2f-90e0-f01463e3f139" />



