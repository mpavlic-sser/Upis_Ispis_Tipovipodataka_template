# NIOP02 - Upis i ispis podataka, tipovi podataka u C# jeziku

# UPUTE ZA RAD

## PRIJAVA U GITHUB 
Otvori https://github.com
Prijavi se svojim GitHub računom
Nemoj zatvarati stranicu

## OTVORI ZADATAK NA GITHUB CLASSROOMU
link na zadatak:
npr. https://classroom.github.com/a/xxxxxxx
Klikni Accept assignment 🎓
Pričekaj 5–20 sekundi da Classroom izradi tvoj privatni repozitorij
Klikni Go to your repository
Klikni Code → HTTPS → Copy da kopiraš URL repozitorija


## KLONIRANJE REPOZITORIJA
Otvorite program Visual Studio Code

Otvorite TerminaL pomoću tipkovničke kratice 
```
CTRL + J
```
Klonirajte svoj repo pomoću naredbe git clone KOPIRANI URL npr.
```
git clone https://github.com/ORG/tvoj-repo.git)
```
Uđite u klonirani repozitorij pomoću naredbe 
```
cd zadatak01
```
Provjeri sadržaj pomoću naredbe 
```
ls
```

## OTVARANJE PROJEKTA U VS CODEU
```
code .
```

## POKRETANJE PROGRAMA

Uđi u projekt mapu:
```
cd Zadatak01.Console
```
upišite naredbu:

```
dotnet run
```

## PREDAVANJE ZADATKA (Commit & Push)
Provjeri status:
```
git status
```
Dodaj sve promjene:
```
git add .
```
Napravi commit:
```
git commit -m "Rješenja zadataka 02"
```
Pošalji na GitHub:
```
git push
```

##########################################################################################################


# Komentari u jednom redu u C#

Komentari se koriste za:

-   objašnjavanje koda
    
-   označavanje dijelova programa
    
-   privremeno “isključivanje” linija koda
    
-   davanje uputa učenicima ili sebi
    

C# ima **jednolinijski komentar** koji počinje s:

    //

Primjeri:

      // ZADATAK1
       KOD ZADATKA

      // ZADATAK2
      KOD ZADATKA


# ISPIS I UNOS PODATAKA U C#

U svakom C# programu radimo dvije glavne stvari:

 - Ispišemo nešto korisniku 
 - Pročitamo nešto što je korisnik upisao

To radimo pomoću Console.WriteLine() i Console.ReadLine().

  
## 1. Ispis podataka – Console.WriteLine()

Console.WriteLine() ispisuje tekst ili vrijednost varijable i prelazi u novi red.

Primjeri:

    Console.WriteLine("Pozdrav svijete!");
    
    Console.WriteLine(123);
    
    Console.WriteLine(3.14);
 

Možemo ispisati i više stvari odjednom:

    int godine = 17;
    
    Console.WriteLine("Moje godine su: " + godine);

  

Formatirani ispis:

    int a = 10, b = 20;

    Console.WriteLine("Vrijednosti su: {0} i {1}", a, b);

Interpolacija (najmoderniji način):

    Console.WriteLine($"Vrijednosti su: {a} i {b}");

  

## 2. Unos podataka – Console.ReadLine()

Console.ReadLine() čita tekst koji korisnik upiše i sprema ga u varijablu tipa string.

    Console.WriteLine("Unesi svoje ime:");
    
    string ime = Console.ReadLine();
    
    Console.WriteLine("Pozdrav, " + ime);

🔥 Problem: Korisnik unosi sve kao string
Svi podaci unešeni preko tipkovnice su string – iako izgledaju kao brojevi.
(Pretvorbe tipova ćemo raditi u drugoj lekciji.)

# 📝 Vježba – Ispis i unos

Napiši program koji:

traži od korisnika da upiše svoje ime
traži od korisnika da upiše svoju školu
ispiše poruku
 
PRIMJER:
Upiši svoje ime: Marko
Upiši svoju školu: Tehnička škola Čakovec


------------------------------------------------------------

# TIPOVI PODATAKA U C#

Što je varijabla?

Varijabla je:

mjesto u memoriji
s imenom koje mi odaberemo
određene veličine (ovisno o tipu podatka)
koje može mijenjati vrijednost

   
## Identifikatori (imena varijabli)

Pravila:

✔ počinju slovom

✔ smiju sadržavati slova, brojeve i _

✔ ne smiju sadržavati č, ć, ž, š, đ

✔ ne smiju biti ključne riječi (npr. int, class)

✔ C# razlikuje velika i mala slova (godina ≠ Godina)

Prikladna imena:

    brojUcenika, temperaturaDanas, korisnik1, ukupnaVrijednost

  
## Deklaracija i inicijalizacija varijabli

Deklaracija:

    int godine;
 

Inicijalizacija:

    godine = 17;

Deklaracija + inicijalizacija u jednom redu:

    int godine = 17;

  
## Zašto postoje tipovi podataka?

Tip podataka određuje:

koliko memorije zauzima varijabla
koje vrijednosti može sadržavati
koje operacije možeš raditi nad tom varijablom
 

Bez tipova program ne bi znao:

razlikovati broj od teksta
koliko memorije rezervirati
kako ispisati ili obraditi vrijednost

    
------------------------------------------------------------

## A) CIJELOBROJNI TIPOVI

  Cjelobrojni tipovi (eng. integer types) pohranjuju cijele brojeve bez decimalnog dijela.

Razlikuju se po tome:

koliku količinu memorije koriste
koji raspon vrijednosti mogu spremiti
imaju li predznak (minus) ili ne

###  1. byte / sbyte

| Tip   | Raspon        | Memorija | Predznak      |
|-------|---------------|----------|----------------|
| byte  | 0 — 255       | 1 bajt   | bez predznaka |
| sbyte | –128 — 127    | 1 bajt   | s predznakom  |

  
✔ Zašto koristiti byte?
kad znaš da vrijednost nikad neće biti negativna
kad štediš memoriju (npr. obrada ogromnih nizova podataka, slika, datoteka)
koristi se za RGB boje, bajtove datoteka, sirove binarne podatke

 ✔ Primjeri:

    byte crvena = 255; // maksimalna jačina boje
    
    byte starost = 15; // ne može biti negativno
    
    sbyte temperatura = -12; // može imati minus

  
  ### 2. short / ushort

| Tip    | Raspon               | Memorija | Predznak |
|--------|-----------------------|----------|-----------|
| short  | –32,768 — 32,767      | 2 bajta  | s predznakom |

  ✔ Zašto koristiti short?

kada trebaš malo veći raspon od byte, ali i dalje želiš uštedjeti memoriju

često se koristi u:
grafici (dimenzije, koordinate)
obradi zvuka
senzorskim podacima
 

✔ Primjeri:

    short brojStanovnika = 15000;
    
    ushort velicinaDat = 50000; // samo pozitivne vrijednosti

   

### 3. int – najčešće korišteni tip

| Tip  | Raspon                           | Memorija | Predznak |
|------|----------------------------------|----------|-----------|
| int  | –2,147,483,648 — 2,147,483,647   | 4 bajta  | s predznakom |


✔ Zašto se najviše koristi?

najbolji kompromis između veličine, brzine i raspona
većina matematičkih operacija radi najbrže s int-om

automatski izbor za:
godine
bodove
količinu
broj učenika
iznose koji ne trebaju velike brojeve

✔ Primjeri:

    int godine = 17;
    int brojUcenika = 24;
    int x, y, z; // više varijabli odjednom

  
  
### 4. long / ulong (za ekstremno velike brojeve)

| Tip  | Raspon                                            | Memorija | Predznak |
|------|----------------------------------------------------|----------|-----------|
| long | –9,223,372,036,854,775,808 — 9,223,372,036,854,775,808 | 8 bajtova | s predznakom |

| Tip   | Raspon                                    | Memorija | Predznak      |
|-------|--------------------------------------------|----------|----------------|
| ulong | 0 — 18,446,744,073,709,551,615              | 8 bajtova | bez predznaka |

  
✔ Zašto koristiti long?

Za podatke koji mogu biti enormno veliki, poput:
broja stanovnika svijeta
udaljenosti u astronomiji
velikih brojeva iz računa
brojanje bajtova na disku

   
    L → označava literal tipa long
    
    u → označava literal bez predznaka

✔ Primjeri:

    long populacija = 7800000000L; // 7,8 milijardi
    
    ulong udaljenost = 99999999999999999u; // jako veliki pozitivan broj

 
## B) REALNI BROJEVI (decimalni)

Realni (floating-point) brojevi pohranjuju brojeve s decimalama.
  
### 1. float (7 decimalnih znamenki)

| Tip   | Preciznost       | Memorija | Napomena |
|-------|------------------|----------|-----------|
| float | oko 7 decimala   | 4 bajta  | koristi se za brze, manje precizne izračune; mora imati 'f' |


✔ Zašto koristiti float?

kad ti treba brza obrada, a preciznost nije presudna
često koristi se u:
igrama (pozicije, brzine)
grafici (koordinate)
simulacijama

✔ Primjer:

    float temperatura = 23.45f;
 

👉 mora imati f na kraju da bi C# znao da je to float literal.

  
### 2. double (15 decimalnih mjesta) – najčešća realna vrijednost

| Tip    | Preciznost        | Memorija | Napomena |
|--------|--------------------|----------|-----------|
| double | oko 15 decimala    | 8 bajtova | najčešće korišten decimalni tip |


✔ Zašto koristiti double?

najbolji balans između preciznosti i brzine

koristi se u:
matematici
fizici
izračunima površina, volumena, brzina
većini znanstvenih računa

✔ Primjer:

    double pi = 3.14159265358979;

  
  ### 3. decimal (28–29 decimala) – financije, novac

| Tip     | Preciznost         | Memorija | Napomena |
|---------|---------------------|----------|-----------|
| decimal | 28–29 decimala      | 16 bajtova | koristi se za novac i financije; mora imati 'm' |

  

✔ Zašto koristiti decimal?

iznimno precizan

koristi se za:
financijske izračune
novac
tečajeve valuta
poreze
matematiku gdje tolerancija pogreške mora biti minimalna

  ✔ Primjer:

    decimal cijena = 19.99m;

  👉 mora imati m na kraju (money).

  

### C) ZNAKOVI I TEKST

### 1. char – jedan znak

| Tip  | Vrijednost | Memorija | Napomena |
|------|------------|----------|-----------|
| char | 1 znak     | 2 bajta  | ASCII/Unicode znak |



    char slovo = 'A';
    
    char broj = '7';
    
    char ascii = (char)65; // 65 → 'A'

  

✔ Gdje ga koristimo?

pri analizi znak po znak
pri radu s ASCII tablicom
za inicijale 
za ocjene („A“, „B“, „C“…)

  ### 2. string – niz znakova (tekst)

Najčešće korišteni tip.

| Tip    | Vrijednost       | Memorija     | Napomena |
|--------|-------------------|--------------|-----------|
| string | niz znakova       | varijabilno  | koristi se za tekst |


    string ime = "Ana";
    
    string poruka = "Ovo je moj prvi tekst!";

  

✔ Gdje se koristi?

Svugdje:
imena
prezimena
poruke
adrese e-pošte
opisni tekstovi

**korisnički unos preko ReadLine()**

  
##  D) LOGIČKI TIP (bool)

### Bool (Boolean) pohranjuje samo:

| Tip  | Vrijednosti      | Memorija | Napomena |
|------|------------------|----------|-----------|
| bool | true / false     | 1 bajt   | logičke vrijednosti |

Koristi se za sve situacije s DA / NE, ISTINA / LAŽ, UKLJUČENO / ISKLJUČENO.

    bool upaljeno = true;
    
    bool otvoreno = false;

  
✔ Primjeri iz prakse:

je li korisnik prijavljen?
je li datoteka dostupna?
je li učenik položio test?
je li igra završila?
je li lampica uključena?
  
  

## E) KONSTANTE

Konstante su vrijednosti koje se ne smiju mijenjati tijekom programa.


    const double Pi = 3.14159;
    
    const string Jezik = "C#";

  

✔ Zašto koristiti konstante?

za matematičke vrijednosti (Pi)
konfiguracije koje se ne mijenjaju
nazivi jezika, poruka, API ključevi
izbjegavanje slučajnih promjena vrijednosti

   
  

------------------------------------------------------------

## ZADACI ZA VJEŽBU

Sve zadatke rješavate u istoj Program.cs datoteci s time da svaki zadatak započinjete s jednolinijskim komentarom s brojem zadatka
Primjer:

    //ZADATAK1
    KOD RJEŠENJA ZADATAK1
    //ZADATAK 2
    KOD RJEŠENJA ZADATAK2
    I TAKO DALJE


### ⭐ Zadatak 1 – Digitalna osobna iskaznica

Učenik treba napraviti mini digitalnu osobnu iskaznicu s različitim tipovima podataka.

Zahtjevi:

-   koristi: string, int, float, bool, char  
      
    
-   podatke sam biraš  
      
    
-   sve ispiši kao uređeni “profil”  
      
    

Primjer ispisa:

   
    Ime: Marko
    
    Godine: 17
    
    Visina: 1.81 m
    
    Ocjena iz Informatike: A
    
    Punoljetan: False


### Zadatak 2 – Aplikacija za pozdrav

Učenik radi pravi program koji traži:

-   ime (string)  
      
    
-   prezime (string)  
      
    
-   godinu rođenja (int)  
      
    
-   omiljeno slovo (char)  
      
    
-   je li učenik doručkovao danas (bool — true/false)  
      
    

Te ispisuje personaliziranu poruku (PRIMJER ISPISA):

    Pozdrav Marko Perić!
    
    Rođen si 2007.
    
    Danas si doručkovao: True
    
    Tvoje omiljeno slovo je M


### Zadatak 3 – Mini sustav za pametnu kuću

Simulacija “smart home” uređaja.

Učenik mora:

-   stvoriti 4 bool varijable: svjetlo, tv, alarm, grijanje  
      
    
-   ručno ih postaviti na true/false  
      
    
-   ispisati sustav (PRIMJER ISPISA):  
    
  
    Svjetlo: Upaljeno
    
    TV: Isključen
    
    Alarm: Uključen
    
    Grijanje: Isključeno


### Zadatak 4 – Konstante za fiziku i matematiku

Učenik mora stvoriti 3 konstante:

-   const double Pi = 3.14159;  
      
    
-   const double Gravity = 9.81;  
      
    
-   const string Language = "C#";  
      
    

I ispisati ih (PRIMJER ISPISA):

    Pi = 3.14159
    
    Gravitacijsko ubrzanje = 9.81 m/s²
    
    Programski jezik = C#


#########################################################################################################

## PREDAVANJE ZADATKA (Commit & Push)
Provjeri status:
```
git status
```
Dodaj sve promjene:
```
git add .
```
Napravi commit:
```
git commit -m "Rješenja zadataka 02"
```
Pošalji na GitHub:
```
git push
```
