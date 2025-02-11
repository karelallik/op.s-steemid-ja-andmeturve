Vastused leitud enda windowsis

|  Küsimus | Linux |  Windows |   Linuxis kasutatud käsklus| Windowsis kasutatud tööriist  |
|---|---|---|---|---|
|1. Mitu protsessi kokku arvutis käib?  |  210 | 125  |   | Task Manager -> jõudlus  |
|2. Milline on kõige esimesena käivitatud protsess?  | /sbin/init splash  | Registry  | ps axo pid,cmd,comm,etime  | Process explorer-> Start time  |
|3. Milliste kasutajate protsesse arvutis käib?   |avahi, colord, geoclue, karel, kernoops, lp, message+, root, rtkit,syslog,systemd+   |  DWM-1, karelallik, LOCAL SERVICE, NETWORK SERVICE, SYSTEM, UMFD-0, UMFD-1 | ps aux --no-headers (pipe) awk '{print $1}' (pipe) sort (pipe) uniq  |  Task Manager-> üksikasajd |
|4. Kui kaua on arvuti järjest töötanud (up time)? | 6min  |  49min 5s |uptime   |Task Manager -> Jõudlus   |
|5. Milline protsess käivitati kõige hiljem (viimasena)?  |update-notifier   | openvpnserv.exe  |ps axo pid,cmd,comm,etime   | Process explorer -> Start time  |
|6. Milline on kõige rohkem protsessoriaega võttev protsess ja kui mitu protsenti protsessoriajast ta tarbib?  |/usr/bin/gnome-shell   |  virtualBoxVM.exe, 15,73%  | ps axo pid,cmd,comm,%cpu --sort=-%cpu | head -n 10  | Process Explorer ->vaatan CPU time järgi  |
|7. Milline on kõige rohkem virtuaalmälu (aadressiruumi, commit, Virtual Size) võttev protsess?   |/usr/bin/gnome-shell   | msedgewebview2.exe  |ps axo pid,user,vsz,comm --sort=-vsz (pipe) head -n 1   |  Process explorer -> Process Memory -> virtual size |
|8. Milline on kõige rohkem füüsilist mälu (working set) võttev protsess?   |/usr/bin/gnome-shell   | explorer.exe  | ps aux --sort=-rss (pipe) head -n 1  |Process Explorer -> vaatan suurimat working set-i   |
|9. Kui palju füüsilisest mälust (Physical Memory) on vaba ja kui palju hõivatud?   |Hõivatud on 966Mib, Vaba on 629Mib ja Saadaval on 1,8GiB   |Hõivatud on 9.3GB ja vaba on 6.0GB   (pipe) free -h  | Task Manager -> Jõudlus -> Memory  |
|10. Kui palju on põhikettal (C:, /) vaba ruumi mahult (GB) ja protsentuaalselt?   |Vaba on 12GB ehk 52%   | Vaba on 279.7GB ehk 58.9%   | df -h /  | WinDirStat  |
|11. Milline on kõige suurem arvutis olev fail ja kõige rohkem andmemahtu hõivav kaust (arvesse võta ka alamkaustade mahtu, ja jätta juurkaust / või C: välja)?   | __suurim fail__ on /var/lib/snapd/snaps/gnome-42-2204_176.snap, __suurim kaust__ : /usr| Kõige suurem kaust on VirtualBox ja kõige suurem fail on {cf064b05-53d4-4564-9330-d492dfc17d15}.vdi  |faili leidmise käsk: sudo du -ah (pipe) sort -rh (pipe) grep '^/' (pipe) head -n 1, kausta leidmiseks: sudo du -aBm / 2>/dev/null (pipe) sort -nr (pipe) head -n 10| WindirStat ja windows explorer -> C: -> search Windows (C:) - size:Gigantic  |
|12. Võrrelge terminali käskude: sha1sum /dev/zero  sha1sum /dev/zero ja sha1sum /dev/urandom  sha1sum /dev/urandom protsessori kasutust. Võrdluseks avage teine terminaliaken ja top samaaegseks käivitamiseks. Kirjutage millisele CPU alamtegevusele (us, sy, id, wa, st jne) kulub enim protsessori aega kummagi käsu puhul  | käsu sha1sum /dev/zero (pipe) sha1sum /dev/zero puhul, kulub enamus CPU us peale. Käsu sha1sum /dev/urandom (pipe) sha1sum /dev/urandom , puhul kulub enamus CPUst sy peale (all ka pilt)  |  --- |   |  --- |
|13. Vasta järgnevatele alamküsimustele: (Ainult Windowsis) | --- |   |  --- |   |
|Milline protsess kõige rohkem salvestusseadmele kirjutab? |---   | System  |  --- |Resource Monitor ->Disk -> Processes with Disk activity -> write (B/sec)   |
|Millisesse faili eelmise küsimuse protsess kõige rohkem kirjutab? | ---  | C:\$Mft (NFTS Master File Table)  | ---  |Resource Monitor ->Disk ->Disk activity -> write (B/sec)   |
|Milline protsess kõige rohkem salvestusseadmelt loeb?  |  --- | Chrome.exe  | ---  |  Resource Monitor ->Disk -> Processes with Disk activity -> Read (B/sec) |
|Millisest failist eelmise küsimuse protsess kõige rohkem loeb?   | ---  | C:\Users\karelallik\AppData\Local\Google\Chrome\ User Data\Default\81982491-7bf2-4ac4-b875-a7a22c263a47.tmp  | ---  |  Resource Monitor -> Disk -> Disk activity -> read(b/sec) |
|14. Millise protsessi poolt tekitatud võrguliiklus on suurima mahuga? Vali antud protsessi poolt kasutatavatest ühendustest üks ning kirjuta välja järgnev: kohalik IP-aadress, kohalik port, ühenduse teise poole IP-aadress, port, latents ja antud ühenduse poolt kasutatav võrguliikluse kogumaht. (Ainult Windowsis) Lisa ka ekraanipilt aruande juurde näiteks pärast tabelit. | ---  |  PILT ALL |   | Resource Monitor -> Network -> Process with Network activity -> TCP Connections  |
|15. Sõber kurdab, et tema arvuti on oluliselt aeglasemaks muutunud. Milliseid konkreetseid programme või käsureakäske kasutad põhjustaja tuvastamiseks. Mõlemal juhul kirjuta, mida konkreetselt jälgid (nt mis aken, veerud, numbrid jne). (Vali Linuxis või Windowsis)  |   |Task Manager ->  Processes - vaatan protsesside kasutamist järgmiste veerguda alusel:CPU (kõrge % protsessorist), Memory, Disk, Network. Details alt vaatan: CPU, Memory. Resource Monitor -> CPU -> CPU veerg, Threads veerg. Disk -> Read (b/sec), Write (b/sec). Network -> TCP Connections (võib viidata võrguprobleemidele).|   |  |
|   |   |   |   |   |
|   |   |   |   |   |

14. küsimus-
<img width="715" alt="image" src="https://github.com/user-attachments/assets/943aad19-4b88-433b-b023-4f68259304b7">
12. küsimus -
<img width="798" alt="image" src="https://github.com/user-attachments/assets/e370ff99-976d-447f-98a9-eee7422a5b95">

