1. Andmekandjad vajavad lähtesamist, kuna uus andmekandja ei sisalda vaikimisi failisüsteemi, mis võimaldaks andmeid salvastada
   ja korraldada. Lähtestades luuakse failisüsteem nagu NTFS, mis võimaldabki OS-il andmeid salvestada ja ka lugeda.
   
2. GPT __üheks__ eeliseks on see, et too toetab suuremaid kettaid ja partitsioone, samas kui MBR-i partitsiooni suurus piirdub umbes
   2 TB-ga. __Teiseks__ tuvastab GPT andmete korruptsiooni ja sisaldab vigade kontrollimise mehhanismi, MBR aga kasutab ainult ühte partitsioonitabelit
   mis tähendab, et kui see saab vigastada, siis kogu ketas võib muututda kättesaamatuks. __Kolmandaks__ on GPT-l parem tugi kaasaegstele süsteemidele
   ja UEFI alglaadimisele, MBR sobib ainult BIOS-iga ning sellega ei saa kasutada UEFI turvalisust ja funktsioone.

3. https://kodu.ut.ee/~karelallik/opsys//hdd.png

4. 
   
<img width="958" alt="ubuntus(hdd)" src="https://github.com/user-attachments/assets/e09fadf3-4572-4e31-a08f-790b6a6eff11">
