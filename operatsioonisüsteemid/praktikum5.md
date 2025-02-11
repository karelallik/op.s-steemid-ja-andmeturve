Antud praktikumi käigus õppisin tundma virtuaalmasinas Ubuntu Linux'is Unix'i failiõigusi. Sain uued teadmised *sticky bit*-st ja *ACL*-st.
Sain ka teada, kuidas anda protsesidele rohkem õiguseid kui kasutajatele.


Märge. Tegin enda ubuntus kasutaja peeter asemel hoopis teise kasutaja nimega allik

5.1 lugemiseks on vajalikud minimaalsed õigused r.
    kustutamiseks on vajalik samuti minimaalselt r.

5.2 Kuna shell peab suutma lugeda ka skripti sisu, et seda käivitada.
    Vaja läheb käivitamiseks ka read õigust

5.3 Igal kasutajal on omanimeline grupp, kuna see pakub suuremat turvalisust ja privaatsust,
    sinna pääseb ligi ainult tema.

<img width="959" alt="ulesanne5 4" src="https://github.com/user-attachments/assets/5e544c8f-38c7-4091-bd95-e9ba6fdb6c0b">


5.5 Setuid õiguse eesmärk on võimaldada antud olukorras jukuisal käivitada programm,
 mis vajab kõrgemaid õigusi, kuid, mis tagab samas turvalisuse ja juurdepääsu piirangud.
 <img width="750" alt="ulesanne5 5" src="https://github.com/user-attachments/assets/833ca68c-58b5-49cd-a190-0080ca845928">


5.6 Jah, setuid-i kasutamine võib vähendada süsteemi turvalisust. Näiteks Kui setuid õigusega programm sisaldab turvavigu, võib mõni kasutaja neid ära kasutada, et saada juurdepääs kõrgematele õigustele.

5.7 Sticky bit õigustega yhiskaust-kataloogist saavad peeter (allik) kasutaja loodud faile kustuda peeter (allik) ja root kasutaja, muud kasutajad saavad ainult enda loodud faile kustutada.

5.8
```
allik@allik24:/home/opetaja/klass$ getfacl hinded.txt
# file: hinded.txt
# owner: opetaja
# group: opetaja
user::rw-
group::---
group:direktor:rw-
mask::rw-
other::---
```

5.9 Mitte keegi ei saa testfail-2 sisu modifitseerida. Faili kustutamiseks tuleb kõigepealt sisestada käsk:
sudo chattr -i testfail-2 ning teiseks võib juba teha rm testfail-2

