**Ülesanne 14-1**
<img width="959" alt="14-1" src="https://github.com/user-attachments/assets/cf8eb961-ab21-4127-bdf2-fea0dd399d4f" />


**Ülesanne 14-2**
<img width="959" alt="14-2" src="https://github.com/user-attachments/assets/54e776c5-adb8-4a4e-ba47-46d735c900cf" />


**Ülesanne 14-3**
<img width="959" alt="14-3" src="https://github.com/user-attachments/assets/118b6ab2-4ef8-4b3a-9ffb-507e44f01724" />


**Ülesanne 14-4**

1. Hääletades krüpteeritakse valija hääl avaliku võtmega, see kuulub serveri võtmepaari avalikku osasse. 
   Hääle krüpteerimine toimub valija seadmes enne hääle saatmist ning kellelgi peale valimiste serveri privaatvõtme 
   pole võimalik krüpteeritud häält dekrüpteerida, näiteks mingi vahel oleval serveril või interneti pakkujal. Lisaks
   eemaldatakse kõik valijaga seotud info enne seda, kui hääl loetakse, et tagada valija anonüümsus. Hääletades kasutatakse
   digiallkirjastamist ainult selle jaoks, et identifitseerida.

2. Esiteks annab valija oma hääle, vastavalt kas ID-kaardi, Mobiil-ID või Smart-IDga. Peale hääletust tekib kontrollkood ja
   krüpteeritud hääl. Nüüd kuvatakse valijale, tema seadmes QR-kood, mille kaudu tal on võimalik vaadata oma hääletustulemust. 
   Ehk QR-koodi skanneerides saadetakse krüpteeritud päring valimisserverisse ja sealt kaudu saabki kätte hääletustulemuse.  
   See on turvaline, sest server ei tea, kes häält kontrollis ega ka kontrollrakendus ei edasta infot, mis tähendab, et pole teada,
   et ma üldse häält kontrollisin. 

3. Seadusandluse poole pealt on nüüdseks Smart-ID samaväärne ID-kaardi või Mobiil-IDga ehk see on ka võrdväärne käsitsi antud allkirjaga.
   Elektroonilise identifitseerimise määrus eIDAS lubab kvalifitseeritud allkirjavahendit isiku digiallkirjastamiseks ja tuvastamiseks 
   ning Smart-ID teenus on ka  QES-tasemel. Varasemalt oli Smart-ID tasemel, mis ei on sobilik e-valimiste seaduslikele nõuetele, kuid 2023
   aastast on Smart-ID Qualified ehk kvalifitseeritud elektrooniline allkiri e. QES. Turvalisuse poole pealt ei asi privaatvõti seadmes, 
   vaid on hoopis laiali SK serverites (teenusepakkuja serverites). Lisaks sellele  toimub kahefaktoriline autentimine. Üks asi on seada 
   ning seal olev konto ja teiseks on kaks pin koodi (PIN1 ja PIN2).

4. Väga keeruline on öelda, kas üks on parem kui teine just seetõttu, et mõlemal on omad plussid ja miinused. Reaalelus on hääletamisel nii palju 
   erinevaid asjaolusid ja tegureid, mis võivad muuta paberhääletamise ebaturvaliseks. Korraldajate enda hoiak või suunitlus võib mõjutada 
   tulemusi, hääled võivad kaduma minna, näiteks lugemise käigus, häälte transportimisel (näiteks kast võib kaduma minna). Samuti võib olla
   võimalik manipuleerida kellegi teise häält, või näiteks teise eest sedel täita. Samas on ka e-hääletamisel oma nõrkused. Nimelt nutiseade,
   mis on pahavaraga nakatanud võib olla suuteline logima sinu hääle valikut või takistada kandidaadi poolt hääletamast. Teisest küljest võib 
   olla ka valimisserver haavatav. Näiteks Ddos rünnakutele, kus server ei ole rahvale enam kättesaadav või Man-in-the-middle rünnakule, 
   kus ründaja manipuleerib häälte edastamist. Viimaks on mingil määral haavatav ka hääle kontrollitavus ja salajasus, sest 100% turvalisusega 
   ei saa hääl samal ajal mõlemat olla, krüptograafiliselt on seda vägagi keeruline saavutada.


