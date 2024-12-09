Antud praktikumi käigus sain algsed teadmised, kuidas luua linuxis skripte, neid käivitada ning kus üldse kirjutada skripte.
ÜLESANNE 3
```
#!/bin/sh
echo "Sisesta oma nimi:"
read nimi
echo $nimi
echo "Sisesta oma eriala:"
read eriala
echo $eriala
echo "Sisesta oma martilkinumber:"
read martilkinumber
echo $martilkinumber
```
![ÜLESANNE3](https://github.com/user-attachments/assets/9feedfe0-70c2-422c-8088-318f20480339)


ÜLESANNE 4
```
#!/bin/bash
echo "Sisesta vana laiend:"
read ALGNE
echo "Sisesta uus laiend:"
read UUS

valjund=$(ls)

for i in $(ls)
do
    if [ "${i##*.}" = "$ALGNE" ];then
        fail="${i%.*}.$UUS"
        mv "$i" "$fail"
        echo "Nimetatud $i -> $fail"
    fi
done
```

![ÜLESANNE4](https://github.com/user-attachments/assets/f4f52690-b4e6-4027-b291-b50de2776314)

ÜLESANNE 5
```
#!/bin/bash
echo "Palun sisesta protsessi nimi:"
read PROTSESSI_NIMI

IFS=$'\n'

for line in $(ps -eo pid,comm --no-headers); do

    rida=$(echo "$line" | tr -s ' ')
    pid=$(echo "$rida" | cut -d ' ' -f1)
    nimi=$(echo "$rida" | cut -d ' ' -f2-)

    if [[ "$nimi" =~ "$PROTSESSI_NIMI" ]]; then
        echo "Protsess: $nimi, PID: $pid"
    fi
done
```

![ÜLESANNE5 1](https://github.com/user-attachments/assets/6d973131-db73-416c-b998-de268117b707)

ÜLESANNE 6
```
#!/bin/bash
aste () {
    alus=$1
    aste=$2
    tulemus=1

    while [ $aste -gt 0 ]; do
        tulemus=$(($tulemus * $alus))
        aste=$(($aste - 1))
    done

    echo $tulemus
}

vastus=$(aste 9 5)
echo "9^5 väärtus on: $vastus"
```
<img width="938" alt="ÜLESANNE6" src="https://github.com/user-attachments/assets/2d0b6086-3040-4647-b29b-38d2b118c882">

ÜLESANNE 7


<img width="701" alt="ÜLESANNE6-CHATGPT-1" src="https://github.com/user-attachments/assets/323dc97c-1133-4656-98b6-406bef08aa34">
<img width="720" alt="CHAT-GPT-2" src="https://github.com/user-attachments/assets/5aff84b5-8200-4e6f-878d-9242ab8c1e5d">
<img width="693" alt="CHAT-GPT-3" src="https://github.com/user-attachments/assets/afdcfe46-a6fb-4e85-b226-e91268f58f57">


