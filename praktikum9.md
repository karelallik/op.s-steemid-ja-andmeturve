Vastused leitud enda windowsis

|  Küsimus | Linux |  Windows |   Linuxis kasutatud käsklus| Windowsis kasutatud tööriist  |
|---|---|---|---|---|
| Mitu protsessi kokku arvutis käib?  |   | 125  |   | Task Manager -> jõudlus  |
| Milline on kõige esimesena käivitatud protsess?  |   | Registry  |   | Process explorer-> Start time  |
|Milliste kasutajate protsesse arvutis käib?   |   |  DWM-1, karelallik, LOCAL SERVICE, NETWORK SERVICE, SYSTEM, UMFD-0, UMFD-1 |   |  Task Manager-> üksikasajd |
|  Kui kaua on arvuti järjest töötanud (up time)? |   |  49min 5s |   |Task Manager -> Jõudlus   |
| Milline protsess käivitati kõige hiljem (viimasena)?  |   | openvpnserv.exe  |   | Process explorer -> Start time  |
| Milline on kõige rohkem protsessoriaega võttev protsess ja kui mitu protsenti protsessoriajast ta tarbib?  |   |  virtualBoxVM.exe, 15,73%  |   | Process Explorer ->vaatan CPU time järgi  |
|Milline on kõige rohkem virtuaalmälu (aadressiruumi, commit, Virtual Size) võttev protsess?   |   | msedgewebview2.exe  |   |  Process explorer -> Process Memory -> virtual size |
|Milline on kõige rohkem füüsilist mälu (working set) võttev protsess?   |   | explorer.exe  |   |Process Explorer -> vaatan suurimat working set-i   |
|Kui palju füüsilisest mälust (Physical Memory) on vaba ja kui palju hõivatud?   |   |Hõivatud on 9.3GB ja vaba on 6.0GB   |   | Task Manager -> Jõudlus -> Memory  |
|Kui palju on põhikettal (C:, /) vaba ruumi mahult (GB) ja protsentuaalselt?   |   | Vaba on 279.7GB ehk 58.9%   |   | WinDirStat  |
|Milline on kõige suurem arvutis olev fail ja kõige rohkem andmemahtu hõivav kaust (arvesse võta ka alamkaustade mahtu, ja jätta juurkaust / või C: välja)?   |   | Kõige suurem kaust on VirtualBox ja kõige suurem fail on {cf064b05-53d4-4564-9330-d492dfc17d15}.vdi  |   | WindirStat ja windows explorer -> C: -> search Windows (C:) - size:Gigantic  |
| Võrrelge terminali käskude: sha1sum /dev/zero  sha1sum /dev/zero ja sha1sum /dev/urandom  sha1sum /dev/urandom protsessori kasutust. Võrdluseks avage teine terminaliaken ja top samaaegseks käivitamiseks. Kirjutage millisele CPU alamtegevusele (us, sy, id, wa, st jne) kulub enim protsessori aega kummagi käsu puhul  |   |  --- |   |  --- |
| Vasta järgnevatele alamküsimustele: (Ainult Windowsis) | --- |   |  --- |   |
|  Milline protsess kõige rohkem salvestusseadmele kirjutab? |---   | System  |  --- |Resource Monitor ->Disk -> Processes with Disk activity -> write (B/sec)   |
| Millisesse faili eelmise küsimuse protsess kõige rohkem kirjutab? | ---  |   | ---  |Resource Monitor ->Disk -> Disk activity -> write (B/sec)   |
| Milline protsess kõige rohkem salvestusseadmelt loeb?  |  --- |   | ---  |  Resource Monitor ->Disk -> Processes with Disk activity -> Read (B/sec) |
|Millisest failist eelmise küsimuse protsess kõige rohkem loeb?   | ---  |   | ---  |   |
|  Millise protsessi poolt tekitatud võrguliiklus on suurima mahuga? Vali antud protsessi poolt kasutatavatest ühendustest üks ning kirjuta välja järgnev: kohalik IP-aadress, kohalik port, ühenduse teise poole IP-aadress, port, latents ja antud ühenduse poolt kasutatav võrguliikluse kogumaht. (Ainult Windowsis) Lisa ka ekraanipilt aruande juurde näiteks pärast tabelit. | ---  |   |   |   |
| Sõber kurdab, et tema arvuti on oluliselt aeglasemaks muutunud. Milliseid konkreetseid programme või käsureakäske kasutad põhjustaja tuvastamiseks. Mõlemal juhul kirjuta, mida konkreetselt jälgid (nt mis aken, veerud, numbrid jne). (Vali Linuxis või Windowsis)  |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |
