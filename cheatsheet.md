# CHEATSHEET

Pythondatei erstellen: .py
Kommentare mit #

# Variablen in Python 
Definieren und ausgeben einer Variable (int, Texts oder boolschen Werten)
, Variablentyp wird bis auf "" und TRUE automatisch definiert, 
Groß- und Kleinschreibung unterschieden, _ okay,
nicht erlaubt sind Zahlen, -, Leer- und Sonderzeichen

```python
>>> x = 1
>>> print(x)
1

>>> abc = "das ist test"
>>> print(abc)
>>> print("das ist text")
"das ist text"

>>> is_weekday = True
>>> print(is_weekday)
True
````
Lösung für das Ausgeben unterschiedlicher Variablentypen hintereinander
```python
>>> print(f"{x}{abc}{is_weekday}")
1das ist ein testTrue

```

Mehrere Variablen gleichzeitig benennen
```python
>>> x, y, z = 1,2,3
>>> a = b = 5
```

Übersicht über die Datentypen
- Text: 
    *- str (Strings)
 - Zahlen: 
    *- int (ganze Zahlen)
    *- float (Gleitkommazahlen)
     - complex (komplexe Zahlen)
 - Logische Wahrheitswerte:
    *- bool (wahr / falsch)

 - Folgen
    *- list (geordnete Menge von Elementen)
     - tuple (geordnetes Menge von Elementen, unveränderlich)
     - range  (steigende Zahlenfolge mit gleichen Abständen)
 - Abbildungen
    *- dict (Wörterbuch mit Abbildung name -> Beschreibung)
     - set (ungeordnete Menge von Elementen)
     - frozenset (ungeordnete Menge von Elementen, unveränderlich) 

 - Binäre Datentypen
     - bytes
     - bytearray
     - memoryview
 

Ausgabe von Datentypen

einfache Datentypen
````python
>>> x = "Universität Mannheim"
>>> type(x)
<class 'str'>

# wenn ' in String vorkommt, dann double quotes verwenden
"I don't know"

>>> d = int(3.0) #oder int("3")
>>> type(d)
<class 'int'>

>>> print(bool(1)) #oder print(bool(0))
True #oder False
````


Listen und besondere Funktionen, anhängen (append), Ausgaben an bestimmten Stellen, umdefinieren von Elementen, geschachtelte/mehrdimensionale Listen
```python
#Liste
>>> wochentage = ["mo", "di", "mi", "do", "fr", "sa", "so"]
>>> print(wochentage[0])            #achtung: erste Position ist Index 0
mo

>>> meineListe = ["hi", 1, [1,2]]
>>> print(meineListe)
['hi', 1, [1, 2]]

#etwas an Listen anhängen
>>> meine_liste.append('d')
>>> print(meineListe)
['hi', 1, [1, 2], "d"]

#Ausgaben an bestimmter Stelle der Liste
>>> print(meineListe[0])
hi
>>> print(meineListe[1:]) #nehme Stellen ab und einschließlich Index 1
[1, [1, 2], "d"]

>>> print(meineListe[:1]) #nehme nur die Stellen bis und ohne Index 1
hi

#Elemente in Liste umdefinieren
>>> meineListe[0] = "NEU" #hi wird mit NEU ersetzt
>>> print(meineListe)
['NEU', 1, [1, 2], 'd']

#geschachtelte Listen bzw mehrdimensionale Listen
>>> nest = [1,2,3,[4,5,['target']]]
>>> print(nest[3])
[4, 5, ['target']]
>>> print(nest[3][2])
['target']
>>> print(nest[3][2][0])
'target'

#Listenelement fallen lassen
>>> lst = [1,2,3]
>>> print(lst.pop())
3
>>> print(lst)
[1, 2]

#überprüfen, ob Element in Liste enthalten ist
>>> 'x' in ['x','y','z']
True

````

Tuple: ähnlich zu Listen, aber () verwendet, können nicht erweitert/angepasst werden
````python
>>> t = (1, 2, 3)
>>> t[0]
1
t[0] = "NEU" #führt zu einem Error
````

Mengen: jedes Element kann nur einmal vorkommen
````python
>>> c = {1, 1, 1, 2, 2, 3, 4, 4, 4}
>>> print(c)
{1, 2, 3, 4}

>> print(type(c))
set
````

Dictionaires (key-value-pairs ohne Reihenfolge) und ihre besonderen Funktionen, mehrdimensionale dictionaires,
keys und items ausgeben
````python
# Dictionaries
>>> wochentage = {1: "Montag", 2: "Dienstag", 3: "Mittwoch", 4: "Donnerstag",
              5: "Freitag", 6: "Samstag", 7: "Sonntag"}
>>>print(wochentage[6])         
Samstag

>>> studiengaenge = {       # oder hier 4.0: "" geht auch
        "Wifo": "Wirtschaftsinformatik", 
        "Wima": "Wirtschaftsmathematik",
        "BWL": "Betriebswirtschaftslehre",
        "MMDS": "Mannheim Master in Data Science"
        }
print(studiengaenge["BWL"])
Betriebswirtschaftslehre

>>> d = {'k1':[1,2,3,{'tricky':['oh','man','inception',{'target':[1,2,3,'hello']}]}]}
>>> d["k1"][3]["tricky"][3]["target"][3]
'hello'

#keys und items ausgeben
>>> print(studiengaenge.keys())
dict_keys(['Wifo', 'Wima', 'BWL', 'MMDS'])

>>> print(studiengaenge.items()) #gibt liste in Tupeln(Items) aus
dict_items([('Wifo', 'Wirtschaftsinformatik'), ('Wima', 'Wirtschaftsmathematik'), ('BWL', 'Betriebswirtschaftslehre'), ('MMDS', 'Mannheim Master in Data Science')])

#da dict_items keine eigenständige Liste ist, wo wir Elemente nach Index abfragen können, hier eine Möglichkeit
dict_items = studiengaenge.items()
out = []
for item in dict_items:
    out.append(item)
print(out)

[('Wifo', 'Wirtschaftsinformatik'), ('Wima', 'Wirtschaftsmathematik'), ('BWL', 'Betriebswirtschaftslehre'), ('MMDS', 'Mannheim Master in Data Science')]

print(out[1])
('Wima', 'Wirtschaftsmathematik')
````

Ausgabe von zusammengesetzten Texten
````python
>>> num = 12
>>> name = "Sam"
>>> print("Meine Zahl ist:{one}, und mein Name ist: {two}".format(one=num, two=name))
#oder print("Meine Zahl ist:{}, und mein Name ist: {}".format(num,name))
Meine Zahl ist: 12, und mein Name ist: Sam
````

Prüfen von Variablentypen
````python
>>> if type(x) == str:
        print("x ist vom typ str")
x ist vom typ str #else: pass automatisch erzeugt
````

logische Funktionen
````python
1+1
1*3
1/2
2**4 #Potenz
4%2  #Restdivision =0
5%2  #=1
5//2 #Ganzzahldivision =2
(2+3)*(3+5)
````

Vergleichsoperatoren
````python
>>> 1>2
False
>>> 1 >= 1
True
>>> 1 == 1
True
>>> 1! = 2 #ungleich
True
>>> "hi" == "Bye"
False
````

logische Operatoren
````python
>>> (1 > 2) and (2 < 3)
False
>>> (1 > 2) or (2 < 3)
True
````

if-Schleifen: Einrücken ist wichtig, wenn nichts pasieren soll, dann pass, elif, else
````python
if 0>1:
    pass
    print("dieser Text gehört nun nicht mwehr zur If-Schleife dazu")

#if-else-Schleife
if 1<2:
    print("first")
else:
    print("last")
    
first

#if-elif-else-Schleifen: der erste Block mit dwer gültigen elif-Anweisung wird ausgeführt
if 1>2:
    print("first")
elif 3==3:
    print("middle")
else:
    print("last")

middle
````

for-Schleifen: erlaubt einem, durch eine Liste/Sequenz zu iterieren
````python
seq = [1,2,3,4,5]
for item in seq:
    print(item) #print("yep")
    
1 #yep

2 #yep
3 #yep
4 #yep
5 #yep

for num in seq:
    print(num + num)
    
2
4
6
8
10
````

while-Schleifen: zum Iterieren und Erhöhen
````python
i = 1
while i<5:
    print("i is: {}".format(i))
    i = i+1

i is: 1
i is: 2
i is: 3
i is: 4

# Berechne nun den Mittelwert und den Median der davor ausgewählten Elemente einer normalverteilten Matrix mit filter(x = normal[normal>2.5]
a = 0
i=0
while i<len(x):
    a = x[i] + a
    print(a)
    i = i+1
print(a)
mittelwert = a/len(x) # bzw np.mean(x)
median = np.median(x)
print(mittelwert)
print(median)
````

range()-Funktion: auflisten von Zahlen 0 bis x ohne selbst zu schreiben
````python
range(5)
for i in range (5):
    print(i)

0
1
2
3
4

list(range(5))
[0, 1, 2, 3, 4]
````

list comprehension: Liste zerstückeln, Funktion darauf anwenden und in neuer Liste anhängen,
Liste nach bestimmten Eigenschaften filtern
````python
x = [1,2,3,4]
out = []
for item in x:
    out.append(item**2)
        print(out) #oder in neue Zeile ohn einrücken, dann nur die letzte Ausgabe

[1]
[1, 4]
[1, 4, 9]
[1, 4, 9, 16]

#andere option
print([item**2 for item in x #if item%2 == 0])
[1, 4, 9, 16] #[4, 16]

# noch eine andere option mit Zusatzeigenschaften
print([item**2 if item%2==0 else item for item in x])
[1, 4, 3, 16]
````

enummerate und zip: enummerate fügt Listenelementen oder anderen Iterablen einen counter hinzu, output ist eine Sequenz von Indexwerten tupeln,
zip fügt Listen zu zip Objekt zusammen
````python
>>> kurse = ['Analysis 1','Stochastik1', 'Funktionalanalysis', 'Analysis2']
>>> semester = [1,3,5,2]
>>> ects = [10,9,8,4]

>>> print(list(enumerate(kurse)))
[(0, 'Analysis 1'), (1, 'Stochastik1'), (2, 'Funktionalanalysis'), (3, 'Analysis2')]

for index1,value1 in enumerate(kurse, start=1): #start könnte den Startindex ändern, andernfalls einfach weglassen
    print(index1, value1)

1 Stochastik1
2 Funktionalanalysis
3 Analysis2

>>> kurse_daten = list(zip(kurse,semester, ects))
>>> print(zip(kurse,semester, ects)
<zip object at 0x000001ECDB464BC0>

>>> print(kurse_daten)
[('Analysis 1', 1, 10), ('Stochastik1', 3, 9), ('Funktionalanalysis', 5, 8), ('Analysis2', 2, 4)]

#formatieren
for value1, value2, value3 in kurse_daten:
    print("Kurs: {}, Semester: {}, ECTS: {}".format(value1, value2, value3))

Kurs: Analysis 1, Semester: 1, ECTS: 10
Kurs: Stochastik1, Semester: 3, ECTS: 9
Kurs: Funktionalanalysis, Semester: 5, ECTS: 8
Kurs: Analysis2, Semester: 2, ECTS: 4

#decomposing: zip datei wieder in Liste umwandeln und wieder schön machen/formatieren
>>> print(*kurse_daten)
('Analysis 1', 1, 10) ('Stochastik1', 3, 9) ('Funktionalanalysis', 5, 8) ('Analysis2', 2, 4)

>>> out1, out2, out3 = zip(*kurse_daten)
>>> print(out1)
('Analysis 1', 'Stochastik1', 'Funktionalanalysis', 'Analysis2')
````

Funktionen: quadratfunktion, String teilen in Funktion, Suche nach einem Wort, wörter zählen,
funktion mit if, else und extra eigenschaften
````python
def myfunc(parameter="default"):
    """
    hier kommt die funktion, docstring
    """
    print(parameter) #gibt parameter nur aus, wenn nicht auf default gesetzt, ? , ??myfunc

#parameter einsetzen
>>> print(myfunc("new parameter"))
new parameter

#beispiel funktion
def square(x):
    return x**2

print(square(2))

#beispielfunktion: string teilen
def domainGet(x):
    print(x.split('@')[1]) # gibt Liste mit zwei Elementen

print(domainGet("user@domain.com"))

#beispielfunktion: suche nach einem Wort
def look_for_money(parameter="default"):
    return "money" in parameter.lower().split()
print(look_for_money('Ich habe soviel Money in meinen Taschen, digga!'))

#Beispielfunktion: Wörter zählen
def count_money(parameter="default"):
    return sum([word in "money" for word in parameter.lower().split()]) #Achtung: for "money" in ... funktioniert nicht!
print(count_money('Money all I need is money Money, dude!'))
2

#beispielfunktion: mit els, if und anderen ausgefallenen eigenschaften
def caught_speeding(speed, is_birthday):
    if is_birthday:
        speed -= 10
    if speed <= 100:
        return "Kein Ticket"
    elif speed <= 120:
        return "Kleines Ticket"
    else:
        return "Grosses Ticket"
caught_speeding(101,True)
'Kein Ticket'
````

Lambda-Ausdruck: bei Funktion als Abkürzung, lambda arguments : expression
````python
>>> x = lambda x : x**2
>>> print(x(4))
16
````

map und filter: map führt Funktion in Liste aus, filter führt Funktion in Liste mit Zusatzeigenschaften aus,
filtern nach Anfangsbuchstaben
````python
>>> seq = [1,2,3,4,5]
>>> list(map(lambda x: x**2, seq)) #oder
>>> print(list(map(square, seq)))
[1, 4, 9, 16, 25]

>>> print(list(filter(lambda item: item%2 == 0, seq)))
[2, 4]

#filtern nach Anfangsbuchstaben
seq = ['schatz','freund','sind','immer','wichtig']
print(list(filter(lambda item: item[:1] != "s", seq)))
['freund', 'immer', 'wichtig']
````

Methoden: groß, klein schreibung, teilen von str
````python
>>> str = "hello, my name is Sam."
>>> print(str.lower()) #alles klein
hello my name is sam.

>>> print(str.upper()) #alles groß
HELLO MY NAME IS SAM.

>>> print(str.split(',')) #bei , teilen und in Liste einfügen, wenn nichts in (), dann bei Leerzeichen geteilt
['hello', ' my name is Sam.']

>>> print(str.split(',')[1]) #nur Element mit bestimmten Index angeben
 my name is Sam.

#
````

error-Handling: automatisch Errorausgabe bei ungültigem Eingabewert, try ... except
````python
def wurzel(x): 
    ''' Berechne die Quadrat-Wurzel von x'''
    try: #testes code nach errors
        if x < 0:
            raise ValueError('x muss größer gleich 0 sein')
        else: #wenn kein error vorhanden (hier in return)
            return x**0.5
    except TypeError: #umgang mit errors
        print('x muss vom Typ int oder float sein')
    #finally: regardless of error tue dies hier
````

numpy: Vektoren, Arrays, Matrizen
````python
import numpy as np

#array erstellen
>>> liste = [1,2,3,4,5]
>>> print(np.array(liste))
[1 2 3 4 5 6]

#matrix erstellen
>>> matrix = [[1,2,3],[4,5,6],[7,8,9]]
>>> print(np.array(matrix))
[[1 2 3]
 [4 5 6]
 [7 8 9]]
````

numpy: arange Befehl: np.arrange(start, stop, steps) erzeugt array automatisch, achtung: [start,stop)
````python
>>> print(np.arange(0,10))
[0 1 2 3 4 5 6 7 8 9]
````

numpy: arrays mit zeros and ones, eye Einheitsmatrix
````python
>>> print(np.zeros(10))
[0. 0. 0. 0. 0. 0. 0. 0. 0. 0.]

>>> print(np.ones((3,4))) #doppelklammer beachten, mxn
[[1. 1. 1. 1.]
 [1. 1. 1. 1.]
 [1. 1. 1. 1.]]

>>> print(np.eye(4))
[[1. 0. 0. 0.]
 [0. 1. 0. 0.]
 [0. 0. 1. 0.]
 [0. 0. 0. 1.]]
````

numpy: linspace liefert gleichmäßig verteilte Zahlen über ein bestimmtes Intervall
````python
>>> print(np.linspace(0, 10, 5)) #anfang, ende, stückzahl
[ 0.   2.5  5.   7.5 10. ]
````


numpy: Zufallszahlgenerator

np.random.default_rng() - Zufallszahlengenerator
random(m,n) - erstellt Array über [0,1) in gleichmäßiger Verteilung
randn(loc = Erwartungswert, scale = Standardabwieiochung, size = Anzahl) - Stichprobe der Normalverteilung
randint(low=, high=, size=) - ganze Zahlen von niedrig bis hoch 
andere beispiele:

beta(a,b,size)

bonomial(n,p,size)

chisquare(degree_of_freedom, size)

poisson(lambda, size)
````python
>>> rng = np.random.default_rng()   #muss zuerst initialisiert werden
>>> print(rng.random(2))            #random
[0.78834514 0.84862696]

>>> print(rng.normal(2))            #randn, normalverteilung
1.6206484239032068
>>> print(rng.normal(loc=10, scale=2, size=5))
[11.13319643 10.95807026 10.39000661  7.21192158 10.34231416]

>>> print(rng.integers(low=1, high=100, size=10)) #randint
[43 58 94 80 65 44 89 88 49 73]

# Lasse dir eine 6x6-Matrix ausgeben, mit normalverteilten Werten mit Mittelwert 2.5 und Varianz 2
print(rng.normal(2.5, 2, (6,6)))
````

numpy: reshape array, verändere die Form des arrays, transpose für Matrixtransformation
````python
>>> arr = np.arange(25)
>>> arr.reshape(5,5) # fügt einzeiliges array zu 5x5 matrix zusammen
[[ 0  1  2  3  4]
 [ 5  6  7  8  9]
 [10 11 12 13 14]
 [15 16 17 18 19]
 [20 21 22 23 24]]

#reshape mit -1
>>> print(arr.reshape(-1))
[ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
 24]
>>> print(arr.reshape(-1).shape)
(25,)

#matrixtransformation: sei normal eine durch rng initiierte 5x5 Matrix mit normalverteilten Zufallswerten, np.transpose()
>>> normal_transpose = np.transpose(normal)
>>> print(normal_transpose) #gibt normal ^T
````

numpy: max, min, argmax (Indexposition des größten), argmin
````python
>>> rng = np.random.default_rng()
>>> ranarr = rng.normal(5)
#[3.80935383 1.00542583 2.90539786 2.9625605  6.28119695]
>>> print(ranarr.max())
6.28119695
>>> print(ranarr.argmax())
4
>>> print(ranarr.min())
1.00542583
>>> print(ranarr.argmin())
1
````

numpy: shape gibt die Form des arrays zurück
````python
>>> print(arr.shape)
(25,)
>>> arr.reshape(5,5)
>>> print(arr.reshape(5,5).shape)
(5,5)
````
numpy: dtype gibt datentyp des arrays aus
````python
>>> print(arr.dtype)
int32
````
numpy: indexing und selection
````python
>>> print(arr[4])
4
>>> print(arr[1:5]) # zahlen von [1,5)
[1 2 3 4]
````

numpy: broadcasten aka anpassen der Größen von Arrays, umbenennen von Einträgen,
Achtung: numpy macht keine Kopien sondern ändert alles direkt im Original
````python
#arr von vorhin ist 0 bis 24, indizes ersetzen
>>> arr[0:6] = 100
>>> print(arr) # ersetze erste 6 indizes
[100 100 100 100 100 100   6   7   8   9  10  11  12  13  14  15  16  17
  18  19 
 20  21  22  23  24]

#nur Teil des arrays ausgeben
>>> slice_of_arr = arr[0:6]
>>> print(slice_of_arr)
[100 100 100 100 100 100]

#Ausschnitt des slice_of_arrays ändern
>>> slice_of_arr[:] = 10
>>> print(arr)
[10 10 10 10 10 10  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
 24]

# Lasse dir die 6. Zeile und dort die 2.-3. Spalte von normalmatrix ausgeben
print(normalmatrix[5, 1:3])
````

numpy: zweidimensionales Array arr[row, col] oder arr[row][col]
````python
>>> arr_2d = np.array([[5,10,15],[20,25,30]]) #doppelklammer [[ ist wichtig
>>> print(arr_2d[1])
[20 25 30]
>>> print(arr_2d[1][0])
20
>>> print(arr_2d[1,0])
20
````

numpy: array mit Daten befüllen
````python
for i in range(len(arr_2d)):
    arr_2d[i] = i
print(arr_2d)
[[0 0 0]
 [1 1 1]
 [2 2 2]]

#nur einen Teil daraus ausgeben: statt arr_2d printe arr_2d[[1,2]]
````

numpy: Selection praktisch wie filtern nach > oder =
````python
>>> arr = np.arange(1,11)
>>> bool_arr = arr > 4
>>> print(bool_arr)
[False False False False  True  True  True  True  True  True]

#ausgabe von den wahren Teilen des bool_arr
>>> print(arr[bool_arr])
[ 5  6  7  8  9 10]

#abgekürzte Schreibweise
>>> print(arr[arr>4])

#oder in Schleife
x = 4
arr[arr>x]
````

numpy: operationen Arithmetik, addition, division, multiplikation, wurzel ziehen, e^ nerechnen, logarithmus
quadrat Achtung: Division durch 0 gibt keinen Error, Unendlich (1/0) auch nicht

````python
import numpy as np
>> > print(arr + arr)  # arr oben mit (1,11) definiert
[2  4  6  8 10 12 14 16 18 20]

# Division durch 0 gibt keinen Fehler, nur nan, infinity/unendlich: 1/0 auch keinen Fehler
>> > print(arr / arr)
[1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
>> > print(1 / arr)
[1.         0.5        0.33333333 0.25       0.2        0.16666667
 0.14285714 0.125      0.11111111 0.1]

# multiplikation
>> > print(arr ** 4)
[1    16    81   256   625  1296  2401  4096  6561 10000]

# wurzel ziehen
>>> print(np.sqrt(arr))
[1.         1.41421356 1.73205081 2.         2.23606798 2.44948974
 2.64575131 2.82842712 3.         3.16227766]

#e^ berechnen
>>> print(np.exp(arr))
[2.71828183e+00 7.38905610e+00 2.00855369e+01 5.45981500e+01
 1.48413159e+02 4.03428793e+02 1.09663316e+03 2.98095799e+03
 8.10308393e+03 2.20264658e+04]

#logarithmus
>>> print(np.log(arr)) #log(0) gibt -unendlich, keinen Fehler
[0.         0.69314718 1.09861229 1.38629436 1.60943791 1.79175947
 1.94591015 2.07944154 2.19722458 2.30258509]
````



PANDAS
importieren von pandas
````python
import pandas as pd 
````

pandas: serie erstellen, gibt geordnete Liste mit Indexbezeichnung wieder und Datentyp
````python
>>> liste = [1,2,3]
>>> print(pd.Series(data=liste))
0    1
1    2
2    3
dtype: int64

#erweiterung mit Voreinstellung zur Zeilennbezeichnung
>>> labels = ["a", "b", "c"]
>>> print(pd.Series(data=liste, index = labels))
a    1
b    2
c    3
dtype: int64
#bzw Abkürzung: pd.Series(liste,labels)
````

pandas: Serie aus numpy arrays erstellen (Tabelle)
````python
>>> arr = np.array([10,20,30])
>>> print(pd.Series(arr)) #bzw wieder arr,labels
0    10
1    20
2    30
dtype: int32
````

pandas: Serie aus Dictionary erstellen
````python
>>> d = {"a":10, "b":20, "c":30}
>>> print(pd.Series(d))
a    10
b    20
c    30
dtype: int64
````

pandas: Index verwenden und operationen anwenden
````python
>>> serie = pd.Series([1,2,10,8], index=["arthur", "sven", "seb", "tom"])
>>> print(serie)
arthur     1
sven       2
seb       10
tom        8
dtype: int64

>>> print(serie["sven"])
2

#operationen anwenden
>>> print(serie + serie)
arthur     2
sven       4
seb       20
tom       16
dtype: int64
````

pandas: Dataframe als Serien mit gleichen Indizes, also Tabellen

````python
import pandas as pd
>>> rng = np.random.default_rng()
>>> df = pd.DataFrame(rng.random((6,5)), index ='A B C D E F'.split(), columns="V W X Y Z". split())
>>> print(df)
          V         W         X         Y         Z
A  0.744184  0.331558  0.314333  0.075259  0.859382
B  0.764789  0.610421  0.673408  0.142206  0.060001
C  0.345292  0.205862  0.917841  0.728803  0.421772
D  0.554484  0.293408  0.028504  0.443440  0.318862
E  0.905323  0.009317  0.716804  0.173853  0.663635
````

pandas: indexing, gibt Spalte mit Index zurück, spalten zu neuem Dataframe addieren,
Spalten löschen, Zeilen löschen, Reihe auswählen, Teilmenge von Zeilen und Spalten auswählen
````python
>>> print(df[["W", "X"]]) #gibt Spalte mit Index X
#oder andere Syntax df.X
          W         X
A  0.882205  0.338800
B  0.601648  0.253952
C  0.619131  0.046281
D  0.508118  0.865768
E  0.809130  0.230298
F  0.559382  0.106292

#dataframes zusammenfügen: Zahlen in Spalten addieren
>>> df["neu"] = df["X"] + df["Z"]
>>> print(df["neu"])
A    1.203048
B    1.191318
C    0.466737
D    1.015356
E    0.346071
F    0.936984
Name: neu, dtype: float64
>>> print(df)
          V         W         X         Y         Z       neu
A  0.971910  0.873752  0.813065  0.899294  0.387157  1.200222
B  0.776715  0.929806  0.151118  0.178193  0.089497  0.240614
C  0.715438  0.107837  0.594136  0.916342  0.471081  1.065217
D  0.688933  0.193049  0.333849  0.884834  0.405843  0.739692
E  0.382959  0.946693  0.601188  0.776263  0.170814  0.772002
F  0.697817  0.942114  0.902190  0.523530  0.836689  1.738879

#spalte löschen aus der Ansicht
>>> print(df.drop("neu", axis=1))
#ausgabe gibt wieder altes df noch mit Spalte "neu" zurück, da nur nicht mehr sichtbar, aber noch vorhanden

#spalte richtig aus Dataframe löschen
>>> df.drop("neu", axis = 1, inplace=True) #wichtig: True groß
>>> print(df)
#ausgabe gibt wieder df zurück, jetzt aber Eintrag wieder richtig gelöscht

#Zeilen löschen
>>> df.drop("F", axis=0 #, inplace = True)
#gibt mit inplace Tabelle ohne F aus, ohne inplce gesamte df

#Reihe auswählen
>>> print(df.loc["A"]) #gibt gesamte Zeile A sortiert nach Spaltennamen aus
V    0.480910
W    0.494661
X    0.683016
Y    0.919471
Z    0.435113
Name: A, dtype: float64

#andere Schreibweise für Zeilenausgabe nach Index der Zeile
>>> print(df.iloc[4])
V    0.255919
W    0.885266
X    0.009861
Y    0.143775
Z    0.288592
Name: E, dtype: float64

#Teilmengen von Zeilen und Spalten auswählen
>>> print(df.loc["A","B"]["Y", "Z"])
          Y         Z
A  0.796800  0.529589
B  0.015128  0.462515
# Lasse dir für Baden-Württemberg die Zahlen von 01. Oktober bis einschließlich 15. Oktober ausgeben
print(df.loc["Baden-Württemberg"]["2020-10-01":"2020-10-15"])
````

pandas: selection
````python
>>> print(df>0) #gibt boolsche Werte zurück
      V     W     X     Y     Z
A  True  True  True  True  True
B  True  True  True  True  True
C  True  True  True  True  True
D  True  True  True  True  True
E  True  True  True  True  True
F  True  True  True  True  True

>>> print(df[df>0]) #gibt Werte bei denen das gültig ist zurück. hier wegen Normalvertielung gesamtes df

#if Schleifen selection: gibt die Spalten Y und Z nur zurück, wenn die Werte in df(V) >0
>>> print(df[df["V"]>0][["Y","Z"]]) #hier alle wegen normalverteilung
          Y         Z
A  0.030689  0.150597
B  0.385051  0.628120
C  0.674608  0.334418
D  0.695256  0.675513
E  0.031502  0.344392
F  0.226581  0.366205

#doppelte selektion:
>>> newdf = df[(df["W"]>0.65)&(df["Z"]>=0.3)]
>>> print(newdf)
          V         W         X         Y         Z
A  0.025582  0.784382  0.945218  0.366547  0.785223
D  0.176390  0.740029  0.948083  0.908172  0.694972
F  0.635234  0.764433  0.338804  0.007535  0.921280
````

pandas: weitere Index Veränderungen, index zurücksetzen auf o,...,n, neue Spalte einfügen, spalte als Index auswählen
````python
>>> print(df.reset_index()) #wieder nicht inplace
  index         V         W         X         Y         Z
0     A  0.122108  0.185878  0.625279  0.922214  0.317246
1     B  0.603928  0.774649  0.140145  0.658846  0.916991
2     C  0.952380  0.444299  0.951437  0.383439  0.692474
3     D  0.911802  0.333292  0.087371  0.291530  0.291998
4     E  0.798027  0.058633  0.720500  0.543466  0.388159
5     F  0.140708  0.501846  0.349097  0.791373  0.803043

#neue Spalte einfügen
>>> index_neu = "1 2 3 4 5 6".split()
>>> df['neue Spalte'] = index_neu
>>> print(df)
          V         W         X         Y         Z neue Spalte
A  0.779513  0.822283  0.797532  0.339169  0.981907           1
B  0.044096  0.402051  0.465760  0.262354  0.236557           2
C  0.122887  0.669163  0.746637  0.694865  0.200882           3
D  0.156573  0.119362  0.920719  0.434532  0.801665           4
E  0.014523  0.962629  0.094893  0.214785  0.147377           5
F  0.572640  0.741676  0.081227  0.634064  0.915735           6

#spalte als Index auswählen, wieder nicht inplace
>>> print(df.set_index("neue Spalte" #,inplace = True))
                    V         W         X         Y         Z
neue Spalte                                                  
1            0.137404  0.934151  0.870252  0.582429  0.010591
2            0.485848  0.987563  0.529741  0.989542  0.701505
3            0.934716  0.162685  0.346401  0.596732  0.837848
4            0.184042  0.530896  0.443141  0.666713  0.309706
5            0.416079  0.751974  0.714719  0.236098  0.013531
6            0.361524  0.554114  0.795491  0.127765  0.521038
````

Multi-index und Hierarchie: miltiindex erstellen, mit Zahlen befüllen
````python
>>> hoch = ["L1", "L1", "L1", "L2", "L2", "L2"]
>>> niedrig = [1, 2, 3, 1, 2, 3]
>>> index_hier = list(zip(hoch, niedrig))
>>> print(index_hier) #gibt Tupel zurück
[('L1', 1), ('L1', 2), ('L1', 3), ('L2', 1), ('L2', 2), ('L2', 3)]

# multiindex daraus machen
>>> index_hier = pd.MultiIndex.from_tuples(index_hier)
MultiIndex([('L1', 1),
            ('L1', 2),
            ('L1', 3),
            ('L2', 1),
            ('L2', 2),
            ('L2', 3)],
           )

#multiindex mit daten befüllen
>>> df = pd.DataFrame(np.random.randn(6,2), index=index_hier, columns=["A","B"])
>>> print(df)
             A         B
L1 1  0.967596  0.072901
   2  0.583223  1.946513
   3  0.090642 -0.512257
L2 1 -0.038205 -1.116977
   2 -1.427860  1.318796
   3  0.133737 -1.810089

#ausgabe von subebene der hierarchie
>>> print(df.loc["L1"])
          A         B
1  2.656606 -0.629275
2 -0.344897  0.760714
3 -0.246059  0.995130

>>> print(df.loc["L1"].loc[2]) #hier nicht index, also 2 = 3 sondern hier ist 2 der Name der Zeile 2
A -0.344897
B 0.760714
Name: 2, dtype: float64
#andere Notationsweise: df.xs(['L1',2])
````

pandas: missing data, data preprocessing,
löschen von zeilen bzw spalten mit fehlenden Daten, threshold, wie viele n pro Zeile mindestens vorhanden sein müssen,
how: any- droppe, wenn überhaupt nan enthalten; all - droppe, wenn nur nan in zeile enthalten
füllen von df mit fehlenden Daten
````python
>>> df = pd.DataFrame({"A": [1,2,np.nan]
                   "B": [5,np.nan,np.nan]
                   "C": [1,2,3]}) #achtung: df transformiert mit A,B,C als Spalten

#löschen von Zeilen mit fehlenden Daten
>>> print(df.dropna())
     A    B  C
0  1.0  5.0  1
# wenn keine Daten mehr enthalten dann
Empty DataFrame
Columns: [A, B, C]
Index: []

#löschen von Spalten mit fehlenden Daten
>>> print(df.dropna(axis=1))
   C
0  1
1  2
2  3

#threshold = 2 -> maximal ein wert darf fehlen
>>> print(df.dropna(thresh=2))
     A    B  C
0  1.0  5.0  1
1  2.0  NaN  2

#how
print(df.dropna(how="any"))
     A    B  C
0  1.0  5.0  1

#umgang mit fehlenden Werten - füllen mit Mittelwert
>>> print(df["A"].fillna(value=df["A"].mean()))
0    1.0
1    2.0
2    1.5
Name: A, dtype: float64
````
pandas: Gruppe bilden - GroupBy nach subkategorie, standardabweichung, minimum, maximum, anzahl count, weiteren Informationen describe(),
allgemeine Infoabfrage
````python
# Daten für das DataFrame
>>> data = {"Uni": ["UniMa", "UniMa", "LMU", "LMU", "KIT", "KIT"],
        "Person": ["Simon", "Fred", "Felix", "Sofie", "Sarah", "Celine"],
        "Spende": [2500, 50000, 3000, 750, 1500, 500000]}
>>> df = pd.DataFrame(data)

#gruppieren nach subkategorie
>>> by_uni = df.groupby("Uni")
>>> print(by_uni) #gibt noch keine Ausgabe, nur dass Gruppierung erstellt
<pandas.core.groupby.generic.DataFrameGroupBy object at 0x000001696F1CED70>

#Durchschnitt der Gruppe als Funktion über Variable by_uni
>>> print(by_uni.mean()) oder #df.groupby("Uni").mean()
         Spende
Uni            
KIT    250750.0
LMU      1875.0
UniMa   26250.0

#mit Standardabweichung
>>> print(df.groupby("Uni").std())
              Spende
Uni                 
KIT    352492.730421
LMU      1590.990258
UniMa   33587.572106

#mit Minimum/max 
>>> print(df.groupby("Uni").min())
       Person  Spende
Uni                  
KIT    Celine    1500
LMU     Felix     750
UniMa    Fred    2500

#mit Anzahl 
>>> print(df.groupby("Uni").count())
       Person  Spende
Uni                  
KIT         2       2
LMU         2       2
UniMa       2       2

#describe() um mehr informationen zu erhalten
>>> print(df.groupby("Uni").describe())
      Spende                           ...                              
       count      mean            std  ...       50%       75%       max
Uni                                    ...                              
KIT      2.0  250750.0  352492.730421  ...  250750.0  375375.0  500000.0
LMU      2.0    1875.0    1590.990258  ...    1875.0    2437.5    3000.0
UniMa    2.0   26250.0   33587.572106  ...   26250.0   38125.0   50000.0

[3 rows x 8 columns]

#besser lesbar machen: transpose
>>> print(df.groupby("Uni").describe().transpose())
Uni                     KIT          LMU         UniMa
Spende count       2.000000     2.000000      2.000000
       mean   250750.000000  1875.000000  26250.000000
       std    352492.730421  1590.990258  33587.572106
       min      1500.000000   750.000000   2500.000000
       25%    126125.000000  1312.500000  14375.000000
       50%    250750.000000  1875.000000  26250.000000
       75%    375375.000000  2437.500000  38125.000000
       max    500000.000000  3000.000000  50000.000000

#allgemeine Info Abfrage über das dataframe
>>> print(df.info())
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 6 entries, 0 to 5
Data columns (total 3 columns):
 #   Column  Non-Null Count  Dtype 
---  ------  --------------  ----- 
 0   Uni     6 non-null      object
 1   Person  6 non-null      object
 2   Spende  6 non-null      int64 
dtypes: int64(1), object(2)
memory usage: 272.0+ bytes
None


# Gruppiere nach Wochentagen (Mo-Fr), und bilde den jeweiligen Mittelwert über alle Observationen an dem Wochentag für jedes Bundesland
df_weekdaymean = df.groupby(df.columns.weekday, axis=1).mean()
print(df_weekdaymean)
                                0          1  ...          5          6
Bundesland                                    ...                      
Baden-Württemberg        7.326868   7.716542  ...   7.012084   6.971357
Bayern                   8.962397   9.158606  ...   8.860385   8.655081
Berlin                  13.449923  13.172378  ...  12.147638  12.989505
Brandenburg              2.606341   2.585652  ...   2.526994   2.490515
Bremen                  13.414321  13.771129  ...  12.501713  13.382308
Hamburg                  7.743725   7.798201  ...   7.264307   7.625467
Hessen                   8.967048   9.142380  ...   8.451201   8.833253
Mecklenburg-Vorpommern   1.491201   1.842421  ...   1.658749   1.515526
Niedersachsen            5.731704   6.095722  ...   5.675481   5.528455
Nordrhein-Westfalen     10.539832  10.945355  ...  10.133877  10.276137
Rheinland-Pfalz          5.850875   5.930647  ...   5.473392   5.325406
Saarland                 4.643860   4.854604  ...   4.054315   4.498620
Sachsen                  3.413033   3.444043  ...   3.209200   3.256207
Sachsen-Anhalt           2.467123   2.488683  ...   2.094369   2.348774
Schleswig-Holstein       3.527600   3.661075  ...   3.584672   3.578639
Thüringen                3.929650   3.925918  ...   3.696079   3.787640

# Verwende das Ergebnis des letzten Schritts und berechne den Mittelwert über alle Bundesländer für die jeweiligen Wochentage
df_bundesland = df_weekdaymean.mean() #mean berachnet schon die Summe, nicht doppelt summieren
print(df_bundesland)

````

pandas: concatenation - verkettung
````python
#Daten dür df1 und df2, df3
>>> df1 = pd.DataFrame({"A": ["A0", "A1", "A2", "A3"],
                    "B": ["B0", "B1", "B2", "B3"],
                    "C": ["C0", "C1", "C2", "C3"],
                    "D": ["D0", "D1", "D2", "D3"]},
                    index=[0, 1, 2,3])
>>> df2 = pd.DataFrame({"A": ["A4", "A5", "A6", "A7"],
                        "B": ["B4", "B5", "B6", "B7"],
                        "C": ["C4", "C5", "C6", "C7"],
                        "D": ["D4", "D5", "D6", "D7"]},
                         index=[4, 5, 6, 7]) 

>>> print(df1)
    A   B   C   D
0  A0  B0  C0  D0
1  A1  B1  C1  D1
2  A2  B2  C2  D2
3  A3  B3  C3  D3

#concatenation - verkettung
>>> print(pd.concat([df1,df2,df3]))
      A    B    C    D
0    A0   B0   C0   D0
1    A1   B1   C1   D1
2    A2   B2   C2   D2
3    A3   B3   C3   D3
4    A4   B4   C4   D4
5    A5   B5   C5   D5
6    A6   B6   C6   D6
7    A7   B7   C7   D7

#verkettung mit Spalten axis = 1
>>>print(pd.concat([df1,df2,df3], axis=1))
     A    B    C    D    A    B    C    D
0   A0   B0   C0   D0  NaN  NaN  NaN  NaN
1   A1   B1   C1   D1  NaN  NaN  NaN  NaN
2   A2   B2   C2   D2  NaN  NaN  NaN  NaN
3   A3   B3   C3   D3  NaN  NaN  NaN  NaN
4  NaN  NaN  NaN  NaN   A4   B4   C4   D4
5  NaN  NaN  NaN  NaN   A5   B5   C5   D5
6  NaN  NaN  NaN  NaN   A6   B6   C6   D6
7  NaN  NaN  NaN  NaN   A7   B7   C7   D7
````

pandas: merging - merge funktion erlaubt es, Dataframes basierend auf bestimmten Kriterium 
zu fusionieren
````python
>>> left = pd.DataFrame({"key1": ["K0", "K0", "K1", "K2"],
                     "key2": ["K0", "K1", "K0", "K1"],
                        "A": ["A0", "A1", "A2", "A3"],
                        "B": ["B0", "B1", "B2", "B3"]})

>>> right = pd.DataFrame({"key1": ["K0", "K1", "K1", "K2"],
                               "key2": ["K0", "K0", "K0", "K0"],
                                  "C": ["C0", "C1", "C2", "C3"],
                                  "D": ["D0", "D1", "D2", "D3"]})

>>> print(left)
  key1 key2   A   B
0   K0   K0  A0  B0
1   K0   K1  A1  B1
2   K1   K0  A2  B2
3   K2   K1  A3  B3

#on als kriterium, wenn nur on="key" gegben, noch how="inner" dazuschreiben
>>> print(pd.merge(left,right, on=["key1","key2"]))
#merget nur die, die sowohl key1 gleich haben, als auch zusätzliche spalten von key2
  key1 key2   A   B   C   D
0   K0   K0  A0  B0  C0  D0
1   K1   K0  A2  B2  C1  D1
2   K1   K0  A2  B2  C2  D2

#how = "outer" merget alle und füllt lücken mit nan
>>> print(pd.merge(left,right, how="outer", on=["key1","key2"]))
  key1 key2    A    B    C    D
0   K0   K0   A0   B0   C0   D0
1   K0   K1   A1   B1  NaN  NaN
2   K1   K0   A2   B2   C1   D1
3   K1   K0   A2   B2   C2   D2
4   K2   K1   A3   B3  NaN  NaN
5   K2   K0  NaN  NaN   C3   D3


#how="right" merget alle basierend auf keys von right und füllt lücken von left mit nan
>>> print(pd.merge(left,right, how="right", on=["key1","key2"]))
  key1 key2    A    B   C   D
0   K0   K0   A0   B0  C0  D0
1   K1   K0   A2   B2  C1  D1
2   K1   K0   A2   B2  C2  D2
3   K2   K0  NaN  NaN  C3  D3
````

pandas: joining
````python
>>> left = pd.DataFrame({"A": ["A0", "A1", "A2"],
                     "B": ["B0", "B1", "B2"]},
                      index=["K0", "K1", "K2"]) 

>>> right = pd.DataFrame({"C": ["C0", "C2", "C3"],
                    "D": ["D0", "D2", "D3"]},
                      index=["K0", "K2", "K3"])

>>> print(left)
     A   B
K0  A0  B0
K1  A1  B1
K2  A2  B2

#join funktion, ohne how werden nur die Indizes Ki übernommen, die in beiden Tabellen gleich sind
>>> print(left.join(right, how="outer")) #füllt alle indizes, die in left und right sind, wenn nicht mit nan
      A    B    C    D
K0   A0   B0   C0   D0
K1   A1   B1  NaN  NaN
K2   A2   B2   C2   D2
K3  NaN  NaN   C3   D3
````

pandas: Operatoren, gib die ersten 5 einträge heraus, finde eindeutige Einträge, bzw sortiere dopplete
Werte aus, count die Anzahl der eindeutigen Werte
````python
>>> df = pd.DataFrame({"col1":[1,2,3,4],"col2":[11,44,66,11],"col3":["abc","def","ghi","xyz"]})

#df.head() gibt die ersten 5 zeilen aus
>>> print(df.head())
   col1  col2 col3
0     1    11  abc
1     2    44  def
2     3    66  ghi
3     4    11  xyz

#eindeutige werte herausfinden, sortiert doppelte Werte aus
>>> print(df["col2"].unique())
[11 44 66]

#finde Anzahl eindeutiger Werte
>>> print(len(df["col2"]).unique())
3 #3 eindeutige Werte
#oder mit df["col2"]).nunique()

#zähle/count, wie oft die eindeutigen Werte vorkommen
>>> print(df["col2"].value_counts())
44.0    1
66.0    1
11.0    1
Name: col2, dtype: int64
````

pandas: Funktionen auf DataFrame anwenden df.apply(),
summe bilden, Funktion zum Löschen von Spalten
````python
>>> def times2(x):
        return x*2

>>> print(df.apply(times2))
   col1   col2    col3
0     2   22.0  abcabc
1     4   88.0  defdef
2     6  132.0  ghighi
3     8   22.0  xyzxyz

#logarithmieren von ganzen Datensätzen Achtung: log() ist keine Funktion in df.apply(np.log)
>>> print(df.apply(np.log)

#oder kurzschreibweise 
>>> print(df(["col1"].apply(lambda x: x*2)))
0    2
1    4
2    6
3    8
Name: col1, dtype: int64

#summe aller einträge einer Spalte
>>> print(df["col1"].sum())
10

#eine Spalte richtig löschen über Funktion
>>> del df["col1"]
>>> print(df)
   col2 col3
0  11.0  abc
1  44.0  def
2  66.0  ghi
3  11.0  xyz
````

pandas: Spalten und Indexnamen zurückgeben
````python
>>> print(df.columns)
Index(['col2', 'col3'], dtype='object')

>>> print(df.index)
RangeIndex(start=0, stop=4, step=1)

>>> print(df.values)
[[11 'abc']
 [44 'def']
 [66 'ghi']
 [11 'xyz']]
````

pandas: DataFrame sortieren
````python
#Spalte 2 nach absteigend sortieren, ascending=False -> aufsteigend, inplace=False bei default
>>> print(df.sort_values(by="col2", ascending=True))
   col2 col3
0    11  abc
3    11  xyz
1    44  def
2    66  ghi
````

pandas: Nullwerte finden über boolsche Werte,
Zeilen mit Nullwerten löschen df.dropna()
````python
>>> print(df.isnull()) #bool, kombination mit .all(), .any() möglich
    col2   col3
0  False  False
1  False  False
2  False  False
3  False  False

#Zeilen mit Nullwerten löschen
>>> df.dropna()
````




pandas: Dateneingabe und Datenausgabe
laden von Datensätzen: pd.read_csv('myfile.csv'), pd.read_excel, pd.read_html,
rad funktionen können nicht als ganzes abgefragt werden, nur als dataset.head()
Umwandeln in csv datei über csv Ausgabe
````python
#CSV Eingabe
>>> tips_dataset = pd.read_csv("https://raw.githubusercontent.com/pandas-dev/pandas/master/doc/data/tips.csv")
>>> print(tips_dataset.head())
   total_bill   tip     sex smoker  day    time  size
0       16.99  1.01  Female     No  Sun  Dinner     2
1       10.34  1.66    Male     No  Sun  Dinner     3
2       21.01  3.50    Male     No  Sun  Dinner     3
3       23.68  3.31    Male     No  Sun  Dinner     2
4       24.59  3.61  Female     No  Sun  Dinner     4

#CSV Ausgabe/ Objekte als kommagetrennte Einträge in CSV Date schreiben
>>> tips_dataset.to_csv("tips_dataset.csv", index=False)
````
pandas: excel: pandas kann excel lesen und schreiben, aber nur importieren von reinen int/str Daten möglich
als voraussetzung murr xlrd installiert sein

````python
#excel Eingabe
>>> excelbeispiel = pd.read_excel("02_pandas_excelbsp.xlsx", sheet_name="BL_7-Tage-Inzidenz")
>>> print(excelbeispiel.head())
          Bundesland  ...  2020-10-25 00:00:00
0  Baden-Württemberg  ...                  NaN
1             Bayern  ...                  NaN
2             Berlin  ...                  NaN
3        Brandenburg  ...                  NaN
4             Bremen  ...                  NaN

[5 rows x 174 columns]

#excel ausgabe
>>> df.to_excel('beispiel_neu.xlsx', sheet_name='Sheet1')

# Lade aus der Datei `02_pandas-excelbsp.xlsx` das Sheet `BL_7-Tage-Inzidenz` als `pd.DataFrame` ein.
# Verwende das Argument `index_col=0`, um die Bundesländer als Index zu setzen für die Zeilen.
>>> df = pd.read_excel('02_pandas_excelbsp.xlsx', sheet_name="BL_7-Tage-Inzidenz", index_col=0)

# Lasse dir das Bundesland ausgeben, in dem die höchste Inzidenz geherrscht hat am 13. Oktober
>>> print(df["2020-10-13"].idxmax())
Bremen

# Berechne nun den Median für jedes Bundesland über alle Beobachtungen
>>> df_logdiff.median(axis=1, skipna=True)
````


HTML

````python
# html eingabe
>>> test = pd.read_html('https://www.taschenhirn.de/politik-und-religion/deutsche-bundeskanzler/')
>>> print(test[0]) #reicht aus, um alles zu bekommen, da das file nach import eine Liste ist
        Deutsche Bundeskanzler  ... Video/Film
0        Konrad Adenauer (CDU)  ...        NaN
1          Ludwig Erhard (CDU)  ...        NaN
2   Kurt Georg Kiesinger (CDU)  ...        NaN
3           Willy Brandt (SPD)  ...        NaN
4          Walter Scheel (FDP)  ...        NaN
5                          NaN  ...        NaN
6         Helmut Schmidt (SPD)  ...        NaN
7            Helmut Kohl (CDU)  ...        NaN
8                          NaN  ...        NaN
9       Gerhard Schröder (SPD)  ...        NaN
10         Angela Merkel (CDU)  ...        NaN
11           Olaf Scholz (SPD)  ...        NaN

[12 rows x 7 columns]

>>> print(len(test)) #Beweis, dass es eine Liste ist
1
````


Matplotlib: importieren
````python
>>> import matplotlib.pyplot as plt
>>> plt.show() #WICHTIG am Ende des Codes hinzufügen, Grafik öffnet sich in neuem Fenster
````


matplotlib: einfache komandos

````python
# eingabe der Daten
import matplotlib.pyplot as plt
>> > import numpy as np
>> > x = np.linspace(0, 5, 11)  # 11 gleichmäßig verteilte Werte über [0,5]
>> > y = x ** 2

# einfache plots
>> > plt.plot(x, y, 'b')  # b ... blau Farbe
>> > plt.xlabel('X Achse Titel')
>> > plt.ylabel('Y Achse Titel')
>> > plt.title('Titel')

# mehrere plots in derselben Ausgabe
>>> plt.subplot(1,2,1) #(zeile,spalte,plotnr) als Tabellenform ausgeben, spalte muss imemr 2 sein
>>> plt.plot(x,y, 'r--') #'r--' steht für rot
>>> plt.subplot(1,2,2) #wenn beide in gleicher plotnr dann in einem diagramm ausgegeben
>>> plt.plot(x,y, 'g*-') #'g*-' steht für Grün mit * linie
````

matplotlib: objektorientierte Methoden, Instanz figure erzeugen, plot im plot ausgeben,
achsen im hauptkoordinatensystem erzeugen
````python
#erzeuge instanz figure
fig = plt.figure()

#achsen erzeugen: add_axes([links, unten, breite, höhe im intervall [0,1]
axes1 = fig.add_axes([0.1,0.1,0.8,0.8]) #Hauptkoordinatensystem
axes2 = fig.add_axes([0.2,0.5,0.4,0.3]) #inneres Koordinatensystem

#hauptkoordinatensystem
axes1.plot(x,y,'b')
axes1.set_xlabel("X Label Plot 1")
axes1.set_ylabel("Y Label Plot 1")
axes1.set_title("Titel Plot 1")

#hauptkoordinatensystem
axes2.plot(x,y,'b')
axes2.set_xlabel("X Label Plot 2")
axes2.set_ylabel("Y Label Plot 2")
axes2.set_title("Titel Plot 2"); #semikolon vielleich notwendig!

#help(fig.add_axes) gibt befehle für methode matplotlib.figure
````

matplotlib: subplots() ähnlich wie figure() als automatischer Achsenmanager, aber mit pythons tuple unpacking,
nrow, ncol gibt wie in figure Zeilen und Spalten, Iteration möglich
````python
fig, axes = plt.subplots(nrows=1, ncols=2) #fig, axes als Tupel von Variablennamen werden Werte rechts neben zuweisung zugewiesen

#mit iterationen arbeiten
for ax in axes:
    ax.plot(x,y,'r')
    ax.set_xlabel('x') #nimmt als achsenbeschriftung die werte von x
    ax.set_ylabel('y')
    ax.set_title('title')
    
fig #zur rückgabae vom Objekt fig notwendig!

#andere ausgabe mit angepassten abständen und spielerein in den Farben
fig,axes = plt.subplots(nrows=1, ncols=2)
axes[0].plot(x,y, color='blue', lw=3, ls='dashed')
axes[1].plot(x,z, color='red', lw=3)

fig.tight_layout()
fig

````

matplotlib: Überlappung von subplots verhindern
````python
#siehe oben und noch hinzufügen:
fig.tight_layout() #andere Notation: plt.tight_layout()

````

matplotlib: Abbildungsgröße (figure size), Seitenverhältnis (aspect ratio) und DPI
````python
#figsize ist ein Tupel aus der Breite und Höhe der Figur in Zoll,
#dpi ist die Punktzahl pro Zoll
fig = plt.figure(figsize=(10,5), dpi=200)
#oder notation
fig, axes = plt.subplots(figsize=(10,5))
````

matplotlib: Grafik speichern
````python
fig.savefig("filename.jpg" #, dpi=200)
````

matplotlib: legenden über legend(), label="Namedeslabels" zur Beschriftung des Graphen, Positionsveränderung mit loc
````python
fig = plt.figure()
ax = fig.add_axes([0,0,1,1])
ax.plot(x,x**2,label="x**2")
ax.plot(x,x**3,label="x**3")
ax.legend(); #wichtig, um Label mit auszugeben

#Positionsveränderung der Legende
ax.legend(loc=1) #oben rechts
ax.legend(loc=2) #oben links
ax.legend(loc=3) #unten links
ax.legend(loc=4) #unten rechts
ax.legend(loc=0) #automatisch eingestellt, wo am besten passt
fig #wichtig für ausgabe
````

matplotlib: einstellen von fraben, linienbreiten und linientypen
````python
#farbe und transparenz
fig, ax = plt.subplots() 
ax.plot(x, x**3, color="blue", alpha=0.2) #colorparameter akzeptiert auch #FFFFFF, alpha gibt transparenz

#linienbreite und stil
ax.plot(x,x+1, linewidth=0.25)
ax.plot(x,x+1, lw=3, linestyle=':') #ls, '-.', '-', '--'

#marker= '+', 'o', '*', 's', ',', '.', '1', '2', '3', '4', ...
ax.plot(x,x+1, lw=3, ls='-', marker='0', markersize=2, markerfacecolor='red', markeredgewidth=3, markeredgecolor='green');

````

matplotlib: plotbereich, set_xlim setzt Achsenlänge, oder axis('tight") gibt tightly fitted achsenbereiche
````python
fig, axes = plt.subplots(1, 3, figsize=(12, 4))

axes[0].plot(x, x**2, x, x**3)
axes[0].set_title("default Achsenbereich")

axes[1].plot(x, x**2, x, x**3)
axes[1].axis('tight')
axes[1].set_title("enge Achse")

axes[2].plot(x, x**2, x, x**3)
axes[2].set_ylim([0, 60])
axes[2].set_xlim([2, 5])
axes[2].set_title("definierter Achenbereich"); #zoomt in das Diagramm auf die gesetzten Achsenbereiche rein
````

matplotlib: spezielle Plottypen
````python
plt.scatter(x,y); #gibt punkt-Diagramm

from random import sample
data = sample(range(1,1000),100)
plt.hist(data) #gibt Balkendiagramm
````

seaborn: import
````python
import seaborn as sns

#daten
tips = sns.load_dataset('tips')
print(tips.head())
````

Seaborn: Verteilungsdiagramme
````python
import matplotlib.pyplot as plt
import seaborn as sns

#daten
tips = sns.load_dataset('tips')
print(tips.head())

#seaborn: distplot als univartiate Verteilung, plotten in seaborn
sns.distplot(tips['total_bill'])
#bzw sns.histplot(tips['total_bill'], kde=True, stat='density', linewidth = 0)
#kde entfernt linie
plt.show()

#seaborn: jointplot() - zwei displot für bivariate Daten vergleichen, kind parameter gibt art des plots an
sns.jointplot(x='total_bill', y='tip', data = tips, kind = 'scatter')
#kind: scatter, hex, reg

#seaborn: pairplot() - paarweis ebeziehungenübver gesamtes dataframe (mxm matrix)
sns.pairplot(tips #, hue='sex',palette='coolwarm') #hue gibt weitere unterscheidungsmöglichkeiten an


#seaborn: rugplot() - zeigenlediglih eine Strichmarkierung für jeden punkt einer univariaten Verteilung
sns.rugplot(tips['total_bill'])

#seaborn: kdeplot() - kerndichteschätzer, ersetzen einzelen Beobachgtung durch gaußsche normalverteilung
sns.kdeplot(tips['total_bills'])
````

Seaborn: kategorische Daten
````python
import matplotlib.pyplot as plt
import seaborn as sns

#daten
tips = sns.load_dataset('tips')
print(tips.describe())
titanic = sns.load_dataset('titanic')
print(titanic.head())

#catplot: allgemeine form eines kategorischen plots, kind gibt art an
sns.catplot(x='sex',y='total_bill',data=tips,kind='bar')

#barplot: gibt Daten als getrennte Balken in Diagramm wieder
sns.barplot(x='sex',y='total_bill',data=tips #, estimator=np.std) #sex ist w oder m -> w und m balken, estimator gibt 

#countplot: Schätzer zählt exakt
sns.countplot(x='sex',data=tips)

#boxplot: vertrilung quantitativer Daten, quartile des datensatz in box
sns.boxplot(x="day", y="total_bill", data=tips,palette='rainbow')
sns.boxplot(data=tips,palette='rainbow',orient='h') #transformiert auf y achse, auch hier wieder hue möglich

#violinplot: verteilung quantitativer daten in bauchform
sns.violinplot(x="day", y="total_bill", data=tips, palette='rainbow' #,hue='sex', split=True)

#stripplot: scatterplot in streifenform
sns.stripplot(x="day", y="total_bill", data=tips,jitter=True,hue='sex',palette='Set1',split=True) #oder jitter = 0.4 gibt breite der punkte

#swarmplot: wie stripplot aber ohne überlappung der punkte
sns.swarmplot(x="day", y="total_bill",hue='sex',data=tips, palette="Set1", split=True)

#kategorische plots können auch kominiert werden, indem gleiche achsen ausgewählt
sns.violinplot(x="tip", y="day", data=tips,palette='rainbow')
sns.swarmplot(x="tip", y="day", data=tips,color='black',size=3)
````

seaborn: matrixplots - Daten als fabkodierte Matrizen/heatmaps darstellen
````python
import seaborn as sns

#daten
flights = sns.load_dataset('flights')
tips = sns.load_dataset('tips')
print(tips.head())
print(flights.head())

#heatmap: erstelle zuerst korellationsmatrix, dann heatmap
tips.corr() #korrelliert alle variablen von tips mit allen variablen von tips
sns.heatmap(tips.corr(),cmap='plasma',annot=True) 

#clustermap: geordnete heatmap
sns.clustermap(pvflights #,cmap='coolwarm',standard_scale=1) #daten auf beiden achsen nicht mehr geordnet
````

seaborn: grids - Gitter
````python
import seaborn as sns
import matplotlib.pyplot as plt

#daten
iris = sns.load_dataset('iris')
iris.head()
iris.species.unique()

#pairgrid: Teilplotgitter zum darstellen von paarweisen Beziehungen in einem Datensatz
g = sns.PairGrid(iris) #daten einfügen
g.map(plt.scatter) #darstellungsweise wählen
g.map_diag(plt.hist) #macht diagonale einträge zu histogramm
g.map_upper(plt.scatter) #über diagonale zu scatter
g.map_lower(sns.kdeplot) #unter diagonale zu Mengendiagramm

#pairplot: einfache version von pairgrid, 
sns.pairplot(iris,hue='species',palette='rainbow')

#facet grid: raster von plots erstellen, die auf einem feature basieren (yes no x yes no matrix)
tips = sns.load_dataset('tips')
tips.head()
g = sns.FacetGrid(tips, col="time",  row="smoker")
g = g.map(plt.hist, "total_bill")

#jointgrid - wie jointplot nur als grid
g = sns.JointGrid(x="total_bill", y="tip", data=tips)
g = g.plot(sns.regplot, sns.histplot)
````

seaborn: regressionsplots, implot() zeigt lineare modelle an und kann diagramme nach merkmalen aufteilen udn farbton ändern
````python
import seaborn as sns
tips = sns.load_dataset('tips')
tips.head()

sns.lmplot(x='total_bill',y='tip',data=tips,hue='sex',palette='ocean') #lineare regression

#marker
# http://matplotlib.org/api/markers_api.html
sns.lmplot(x='total_bill',y='tip',data=tips,hue='sex',palette='ocean',
           markers=['o','v'],scatter_kws={'s':2})

#man kann hier auch gitter (grids) benutzen
sns.lmplot(x='total_bill',y='tip',data=tips,col='day',hue='sex',palette='coolwarm')

#größe und seitenverhältnis ändenr
sns.lmplot(x='total_bill',y='tip',data=tips,col='day',hue='sex',palette='coolwarm',
          aspect=0.6,size=8)
````

seaborn: stil und farbe ändern
````python
import seaborn as sns
import matplotlib.pyplot as plt
tips = sns.load_dataset('tips')

sns.set_style('darkgrid') #mache hintergrund gräulich
sns.set_style('ticks') #umrame box
sns.despine() #umrahmung löschen
sns.despine(left=True) #nur links die umrahmung löschen
sns.set_context('poster',font_scale=4) #set_context überschreibt standardparameter, wie die schriftgröße
````

seaborn: plot abspeichern
````python
fig3 = scatter_plot.get_figure() #scatter plot zu figure machen, damit gespeichert werden kann
fig3.savefig("/Users/lucaslinden/Pythonkurs/plot2.png")
````