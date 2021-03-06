---
theme: gaia
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.jpg')
marp: true
---


# **Informacioni sistem za minimizaciju otpatka hrane**

Student: Nikola Selić
Asistent: Nikola Todorović

---
---
#### **Motivacija - postupak merenja**

![bg left:40% 80%](https://uspto.report/patent/app/20190186986/US20190186986A1-20190620-D00000.png)

### Vremenski zahtevan proces
- Ugostitelji moraju da izdvoje dosta vremena svakoga dana zarad merenja otpada

---
#### **Motivacija - postupak merenja**

### Rucno obradjivanje podataka
- Pomoću ovog informacionog sistema, korisnici su u mogućnosti da pomoću kamere i vage sistem sam detektuje i izračuna količinu otpada od hrane
- Najčešće ovaj proces se obavlja ručno od strane kuhinjskih pomoćnika ili se uopšte ne radi.
- Nedostatak informacije o količini otpada, i njeno dalje recikliranje, može uticati na dalje poslovanje ugostiteljskog objekta.

---
#### **Motivacija - postupak merenja**

![bg left:40% 80%](https://miro.medium.com/max/600/0*7PgQsp0nYHjMpLXX.png)
### Neblagovremeno obavestavanje
- Ne postoji povratna informacija u realnom vremenu o kolicini otpada od hrane i njenoj vrednosti, što prouzrokuje da klijent ne može reagovati u datom trenutku i izmeni stanje u kuhinji


---
### **Motivacija**
##### **Ekološka svest i minimizacija troškova**

- Istraživanje u **Švajcarskoj** govori da ugostiteljski objekti za sada doniraju samo **5%** svojih ostataka hrane, dok ukupno **2.6 miliona tona otpada** od hrane se zabeleži svake godine. Računica govori da skoro **190 kg** otpada hrane se stvori za godinu dana po glavi stanovnika. [1]

---
### **Motivacija**
##### **Ekološka svest i minimizacija troškova**

- Istaživnaje u **SAD** govori da su u blagoj prednosti u odnosu na prethodno pomenutu državu,  i da svaki stanovnik godišnje stvori oko **100kg** hrane završi medju otpatke. [2]

---
### **Motivacija**
##### **Ekološka svest i minimizacija troškova**

- Istraživanje radjeno na teritoriji **Republike Srbije** govori da je skoro **247,000 tona** hrane bačeno svake godine, tj. **676 tona** hrane svakog gana. 
- Podatak je poražavajuć ako se uzme u obzir da je prosečna plata u Srbiji manja od **500 evra mesečno**. 
- Dalja računica govori da prosečan stanovnik za godinu dana odbaci hranu od vrednosti od **85 evra.** [3]

---
### **Motivacija**
##### **Ekološka svest i minimizacija troškova**

Najčešći otpad je hleb (**10.18kg**), meso (**7.18kg**) i mleko(**6.74 litara**).

Razlog odbacivanja hrane je: 
- stvaranje budji (67%)
- neodgovarajuća hrana (17%)
- strah od lošeg kvaliteta (11%)

---
### **Ciljevi**

- **Pojednostavljanje procesa merenja hrane**
- **Brže informisanje ugostitelja o otpadu hrane**
- **Smanjenje hrane u otpadu, i samim tim smanjenje troškova**
- **Dodatne povratne informacije o hrani koja je služena gostima**
- **Implementacija sistema preporuke**
- **Prepoznavanje trenda**

---

### **Funkcionalni zahtevi**
#### Postojanje menija

Svaki restoran ima svoji **meni**, i na tom meniju različite vrste mesa, povrća, voća i žitarica.

Tako da, svaki restoran ima skup jela koji je moguće imati u datom restoranu.

Svaku sliku pre svega model mora da prepozna i klasifikuje da li je to komad odgovarajuće hrane i njegovu količinu tj. težinu.

---

### **Funkcionalni zahtevi**
#### Treniranje modela za prepoznavanje hrane

Učenje nad podacima se odvija na već obeleženim slikama informacionog sistema i odvija se u sistemu za obradu podataka.

Ljudi koji su odgovorni za klasifikaciju i obeležavanja slika su podeljeni u više grupa po merodovnosti (*eng. level* ).

Dolazi do koncenzusa i odgovarajuća slika se smatra kao dobro ocenjena slika

---

### **Funkcionalni zahtevi**
#### Treniranje modela za prepoznavanje hrane

---
### **Funkcionalni zahtevi**

- **Postavljanje nove vage i registrovanje novog restorana**
- **Izveštaj klijentu o dnevnoj, nedeljnoj, i mesešnoj potrošnji**
- **Samo prepoznavanje hrane i kojoj kategoriji pripada**
- **Povratna informacija ugostitelju o potencijalnom trošku**
- **Sistem za preporuku novog menija**

---
### **Tehnologije**
#### Arhitektura sistema

- Uredjaj registruje promene *event* i šalje podatak o merenju serverskoj aplikaciji.
- Serverska aplikacija upisuje novu izmenu u bazi podataka sa svim informacijama vezane za vagu i merenje.
- Prikaz podataka radi se preko web aplikacije preko koje korisnik može pristupiti sa svojim nalogom

![bg left:40% 80%](../../Downloads/Food waste - ISA (2).jpg)

---
### **Tehnologije**
#### Arhitektura sistema

- U zavisnosti od broja korisnika i mogućnosti da li možemo priuštiti odgovarajuće servere, koristićemo *cloud* servise - *AWS*

- Prikaz podataka bi trebao biti nezavistan od uredjaja na kome se prikazuje i to nam trenutno omogućuje web tehnologija i web aplikacije

---
### **Tehnologije**
#### Arhitektura sistema

- Serverska aplikacija bi trebala biti izgradjena u tehnologiji sa dobrom podrškom i ekosistemom npr. Java Spring

- Softver može biti izgrađen u stilu mikroservisne arhitekture, bar izdvojiti zaseban servis za preporuku. 


---
### **Literatura**
[1] https://www.rts.com/resources/guides/food-waste-america/#:~:text=Here's%20some%20%E2%80%9Cfood%E2%80%9D%20for%20thought,tons%20of%20food%20every%20year.&text=That's%2080%20billion%20pounds%20of,of%20the%20US%20food%20supply.

[2] https://www.swissinfo.ch/eng/environment_households-the-biggest-sources-of-swiss-food-waste/44928344

[3] https://www.serbianmonitor.com/en/247000-tonnes-of-food-thrown-away-in-serbia-each-year/#:~:text=Every%20year%20some%20247%2C000%20tonnes,news%20agency%20reported%20on%20Wednesday.&text=The%20reasons%20for%20throwing%20away,quality%20(11%20per%20cent).

---
### **Hvala na pažnji!**


