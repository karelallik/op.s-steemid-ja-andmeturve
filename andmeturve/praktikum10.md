***Ülesanne 10-1***
```
  GNU nano 7.2                                                  skript.sh *                                                         
#!/bin/sh
iptables -F
iptables -X naabrid 2>/dev/null    # eemaldame vana ahela, kui see eksisteerib
iptables -N naabrid                # loome uue ahela

# Põhifiltrid
iptables -A INPUT -i lo -j ACCEPT
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT


iptables -A INPUT -s 172.20.10.2 -j naabrid
iptables -A INPUT -s 172.20.10.3 -j naabrid


iptables -A naabrid -j LOG --log-prefix "Allik-NAABRID-ahel: "


# ICMP (ping)
iptables -A naabrid -p icmp --icmp-type echo-request -j ACCEPT
# SSH
iptables -A naabrid -m state --state NEW -p tcp --dport 22 -j ACCEPT
# SMTP
iptables -A naabrid -m state --state NEW -p tcp --dport 25 -j ACCEPT
# HTTP
iptables -A naabrid -m state --state NEW -p tcp --dport 80 -j ACCEPT
# HTTPS
iptables -A naabrid -m state --state NEW -p tcp --dport 443 -j ACCEPT

# INPUT ahelasse
iptables -A naabrid -j RETURN

iptables -A INPUT -j LOG --log-prefix "input-reject: "
iptables -A INPUT -j REJECT

```

**Ülesanne 10-2**
<img width="959" alt="10-2-ÕIGE" src="https://github.com/user-attachments/assets/d57af885-fdaa-4aca-8985-b3a2d7427f04" />



**Ülesanne 10-3**
<img width="650" alt="10-3" src="https://github.com/user-attachments/assets/f5dcdf9f-d344-415b-ae3e-3bdc28fdc628" />


**Ülesanne 10-4**
1. IPv6 aadresside seadmepõhisus -  Kuna igale seadmele antakse unikaalne avalik IPv6 aadress (NAT ei varja aadresse), muutuvad need seadmed otse Internetist ligipääsetavaks.

2. Fragmentatsiooni rünnakud - IPv6 ei luba marsruuteritel pakette fragmenteerida. Kogu fragmentatsioon peab toimuma lähtepunktis, mis teeb võimalikuks pahatahtliku fragmentide loomise. See rünnak aitab tulemüüri reeglistest mööda hiilida.

3. DoS/DDoS IPv6 aadressidele - Avalikud IPv6 aadressid võimaldavad ründajal sihtida kindlaid seadmeid suure liikluse või ressursi kasutusega, mis võib põhjustada süsteemi hangumise või ka teenuse katkemise. IPv6 puhul puudub NAT-i vahekiht, mis IPv4 puhul mõnevõrra hajutas sellist mõju.

**Ülesanne 10-5**
Linux ja macOS süsteemid ei aktiveeri vaikimisi tulemüüri, sest: Need süsteemid on traditsiooniliselt mõeldud tehnilisemate kasutajate jaoks,Linux ja macOS ei paku vaikimisi mitmeid teenuseid. Kuid windows on populaarne lauaarvutite ja koduvõrkude süsteem, mis on sageli pättide sihtmärk ning see tõttu pakub Microsoft suuremat kaitset.

**Ülesanne 10-6**

IPv6 analoog ARP spoofingule on "Neighbor Discovery Protocol (NDP) spoofing"
IPv6 ei kasuta ARP-protokolli, vaid selle asemel kasutatakse NDP (Neighbor Discovery Protocol) aadresside ja MAC-aadresside sidumiseks. Ründaja saab luua võltsitud "Neighbor Advertisement" sõnumeid.

https://en.wikipedia.org/wiki/Neighbor_Discovery_Protocol#Security
