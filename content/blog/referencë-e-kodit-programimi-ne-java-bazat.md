---
path: java-programimi
date: 2020-04-12T20:27:00.882Z
title: Referencë e Kodit - "Programimi ne Java - Bazat"
---

### 1. Një Program i Thjeshtë në Java

```java
public class MyClass {
  public static void main(String[] args) {
    System.out.println("Hello World");
  }
}
```

------



### 2. Komentet

Përdoren për të dhënë informacion për kodin brenda fajllit. Komentet brenda kodit kompajlleri i injoron gjatë ekzekutimit të programit.

```java
/* Komentet
me shume 
Rreshta*/

// Komentet vetem nje ne rresht

// Nje koment tjeter
```

------



### 3. Tipet e Të Dhënave

- #### PRIMITIVE:

Numrat e Plotë :

```java
byte num1 = 20;
short num2 = 34;
int num3 = 293;
long num4 = 293;
```



Numrat me Presje :

```java
float num1 = 100.34f;
double num2 = 3021.232;
```



Char :

```java
char a = 'a';
char b = 'B';
char c = '/';
```



Boolean ( ka vetem dy vlera) :

```java
boolean llampaEshteNdezur = true;
boolean televizioniEshteFikur = false;
```



| Tipi    | Madhëesia (në memorie)  | Rangu                                                        |
| ------- | ----------------------- | ------------------------------------------------------------ |
| byte    | **8-bit**    (1 byte)   | Nga **-128** deri **127**.                                   |
| short   | **16-bit**    (2 bytes) | Nga **-32,768** deri **32,767**.                             |
| int     | **32-bit**    (4 bytes) | Nga **-2,147,483,648** deri **2,147,483,647**.               |
| long    | **64-bit**    (8 bytes) | Nga **-9,223,372,036,854,775,808** deri **9,223,372,036,854,775,807**. |
| float   | **32-bit**    (4 bytes) | Deri në **7** shifra decimale.                               |
| double  | **64-bit**    (8 bytes) | Deri në **15** shifra decimale.                              |
| boolean | **1-bit**               | Vetem dy vlera: **true**, **false**                          |
| char    | **16-bit**    (2 bytes) | Varësisht nga standardi i enkodimit për sistemin përkatës.   |



- #### REFERENCIALE (JO-PRIMITIVE):

String (bashkesi e disa variablave primitive te tipit **char**) :

```java
String myName = "Ermal Abiti";
```



- #### Konstantet (Përcaktohen vetëm një herë dhe nuk ndryshojnë më) :

```java
final double PI = 3.1415;
PI = 3.14111; // Kjo linje e kodit na shfaq error sepse PI eshte variabel konstante dhe nuk guxon te ndryshohet
```

------



### 4. Primitive Data Conversion (Konvertimi i të Dhënave Primitive)

- Nga variabla me madhësi më të vogël në atë më të madhe (**Widening Casting**) - automatike:

```java
byte x = 10; //  x: 10
int y = x; //  y: 10

int a = 120; //  a: 120
double b = a; //  b: 120.0
```



- Nga variabla me madhësi me të madhe në atë më të vogël **(Narrowing Casting**) - duhet të bëhet në mënyrë manuale:

```java
int x = 10; //  x: 10
byte y = (byte) x; //  y: 10

double a = 543.232; //  a: 543.232
int b = (int) a; //  b: 543
```

​	** Tek ky lloj i konvertimit mund të kemi humbje të informates. p.sh nëse tentojmë numrin e plotë 32-bit (int), 129, ta kthejmë në numër të plotë 8-bit (byte), numri i konvertuar do të jetë -127, për shkak se rangu i numrave të plotë 8-bit ështe prej -128 e deri 127. Pra numri 129 nuk është i përfshirë në këtë rang dhe numrimi fillon nga numri më i vogel dhe na e kthen numrin e konvertuar me vlerën -127*: 

```java
int x = 129; //  x: 129
byte y = (byte) x; //  y: -127
```

------



### 5. Operatorët

- Operatorët Aritmetikë :

```java
int x = 23, y = 71;

// Mbledhja (+)
int mbledhja = x + y;    // mbledhja: 94

// Zbritja (-)
int zbritja = y - x;    // zbritja: 48

// Prodhimi (*)
int prodhimi = x * 3;    // prodhimi: 69

// Pjestimi (/)
int pjestimi1 = 10 / 2;    // pjestimi1: 5

int pjestimi2 = 3 / 2;    // pjestimi2: 1
double pjestimi3 = 3 / 2;    // pjestimi3: 1.5

double pjestimi4 = 3 / 2;    // pjestimi4: 1.0
double pjestimi5 = (double) 3 / 2;    // pjestimi5: 1.5
double pjestimi6 = 3 / (double) 2;    // pjestimi6: 1.5

// Moduli (%) *rikthehet mbetja
int mbetja1 = 7 % 2;    // mbetja1: 1
int mbetja2 = 20 % 6;    // mbetja2: 2
```



- Operatorët Inkrementues dhe Përcaktues:

```java
// Inkrementimi për 1 vlerë (p.sh. ++x dhe x++):
int x = 10;
x++;    // x: 11
++x;    // x: 12

System.out.println(x++);    // Shfaq vleren e tanishme të x (12), e pastaj e inkrementon x-in për 1 (x bëhet 13)

System.out.println(++x);    // E inkrementron x-in për 1 (x bëhet 14), e pastaj e shfaq vleren e tanishme të x (14)

// Inkrementimi me qfarëdo vlere (Operatorët Përcaktues)
int y = 120;
y += 3;    // y: 123
y = y + 3;    // (e njejte me "y += 3")  -  y: 126
```

Lista e Operatorëve Përcaktues:

| OPERATORI |
| :-------: |
|     =     |
|    +=     |
|    -=     |
|    *=     |
|    /=     |
|    %=     |
|    &=     |
|    \|=    |
|    ^=     |
|   \>\>=   |
|    <<=    |



- Oeratorët Krahasues (rikthejnë TRUE ose FALSE nëse pohimet matematikore janë të sakta) :

```java
int x = 30;
int y = 24;

// Barazim Me (==)
boolean barazimMe = (x == y);            // barazimMe: false
boolean barazimMe2 = (y == 24);          // barazimMe2: true

// E Ndryshme Nga (!=)
boolean ndryshmeNga = (x != y);          // ndryshmeNga: true

// Me e Madhe (>)
boolean meEMadhe = (x > y);              // meEMadhe: true

// Me e Vogel (<)
boolean meEVogel = (x < y);              // meEVogel: false

// Me e Madhe ose Barazim (>=)
boolean meEMadheBarazim = (x >= 30);    // meEMadheBarazim: true

// Me e Vogel ose Barazim (<=)
boolean meEVogelBrazim = (x <= y);      // meEVogelBarazim: false
```



- Operatorët Logjikë (rikthejnë TRUE ose FALSE) :

```java
boolean on = true;
boolean off = false;

// Operatori AND(dhe) - (&&)
boolean and1 = (on && off);     // and1: false
boolean and2 = (off && off);    // and2: false
boolean and3 = (on && on);      // and3: true

// Operatori OR(ose) - (||)
boolean or1 = (on || off);     // or1: true
boolean or2 = (off || off);    // or2: false
boolean or3 = (on || on);      // or3: true

// Operatori NOT(jo/e kunderta) - (!)
boolean not1 = !(on);          // not1: false
boolean not2 = !(off);         // not2: true
```

------



