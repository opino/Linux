# LPIC-1-Vorbereitung


Aus Linux-Magazin 04/2007 - https://www.linux-magazin.de/ausgaben/2007/04/grosser-shell-atlas/
## LPIC-1-Vorbereitung - Teil 9: Shell anpassen und Skripteschreiben
Von Hans-Georg Eßer

Das LPI-Zertifikat setzt den sicheren Umgang mit der Shell voraus. Administratoren müssen aber auch in der Lage sein, die Bash zu konfigurieren und nützliche Skripte zu programmieren. Die LPIC-Serie stellt diesmal die Prüfungsthemen aus Topic 109 vor.

Die Standardshell unter Linux ist die Bash. Auch wenn es die C-Shell, Tcsh, Korn-Shell und viele weitere gibt, die ebenfalls ihre Anhänger haben, sind für die LPI-Prüfung nur Bash-Kenntnisse relevant. Bei dem dabei abgefragten Wissen geht es um Shellvariablen, Skripte und die Konfiguration des Shellstarts über Profile-Dateien.

Shellvariablen setzt der Anwender mit »Variable=Wert« und ruft sie später durch ein vorangestelltes Dollarzeichen ab, etwa »echo . Häufig enthalten Shellskripte statt dieser einfachen Variante die Form »«. Sie macht zum einen deutlicher, an welcher Stelle der Name aufhört (Was bedeutet ».AZ«?), zum anderen ist es bei Zusammensetzungen manchmal die einzige Möglichkeit, Variablen und Strings zu kombinieren:

```
$ X="AAA"; Y="BBB"; XY="CCC"
$ echo $XY; echo ${XY}; echo ${X}Y; echo $X$Y
CCC
CCC
AAAY
AAABBB
```
Jeder Prozess besitzt eine eigene Umgebung, in der Umgebungsvariablen definiert sind. Über den »export«-Befehl der Bash wird eine Shell- zur Umgebungsvariablen. Letztere gibt das System beim Erzeugen neuer Prozesse weiter: Nach dem Start eines Programms aus der Shell erbt der neue Prozess alle Umgebungsvariablen, nicht aber die Shellvariablen, wie folgendes Beispiel zeigt:

```
$ SHELLVAR=Test1
$ export UMGEBUNGSVAR=Test2
$ bash
$ echo $SHELLVAR
$ echo $UMGEBUNGSVAR
Test2
```

Das »export«-Kommando wandelt eine bereits definierte Shellvariable zur Umgebungsvariablen: »export Variable«. Der Befehl »env« zeigt die Liste aller exportierten Variablen an (Abbildung 1), »set« tut das auch, liefert aber außerdem die definierten Shellfunktionen zurück. Das Exportieren ist übrigens keine Einbahnstraße: Der Befehl »export -n Variable« macht aus einer Umgebungs- wieder eine Shellvariable, nimmt also einen früheren »export«-Aufruf zurück. Um eine Variable ganz zu löschen, bietet die Bash das Kommando »unset«.

Eine andere Möglichkeit, gestarteten Prozessen eine Variable zu übergeben, ist es, die Variablenzuweisung unmittelbar vor den Programmaufruf zu setzen:

```
Variable=Wert Kommando
```

Ein Beispiel dafür ist »VISUAL=nedit less lpi-shell.txt«. Dieser Befehl zeigt die Textdatei in »less« an und definiert vorher die Variable »VISUAL«, die der Dateibetrachter auswertet, wenn er einen Editor startet.

### Startdateien
Zahlreiche Shellvariablen sind schon nach dem Shellstart definiert, dafür sind die Startdateien verantwortlich, welche die Shell aufruft. Dabei spielt es eine Rolle, ob die Shell eine Login-Shell oder eine normale interaktive (aber nicht durch Login gestartete) ist: Es gibt einige Skripte, die nur beim Login – also beim ersten Aufruf einer Shell in einer neuen Benutzersitzung – relevant sind, während die Shell andere Skripte bei jedem Start liest. Eine nicht interaktive Shell ist eine, die nur läuft, um beispielsweise eine Skriptdatei auszuführen, sie liest darum keine Startskripte ein.

Jede Login-Shell arbeitet zunächst die »/etc/profile«-Datei ab, wenn es sie gibt. Danach sucht die Shell im Homeverzeichnis nach »~/.bash_profile«, »~/.bash_login« und »~/.profile«. Die in dieser Reihenfolge zuerst aufgefundene erhält den Zuschlag. Ist die Shell keine Login-Shell, führt sie stattdessen die Dateien »/etc/bash.bashrc« und »~/.bashrc« aus, sofern vorhanden.

Je nach Distribution gibt es noch mehr Startup-Dateien. So sucht die Bash unter Suse Linux nach »/etc/profile.local« und »/etc/profile.dos«. Außerdem gibt es ein Verzeichnis »/etc/profile.d/«: Jedes Shellskript, das darin liegt und dessen Name auf ».sh« endet, führt »/etc/profile« zusätzlich aus.

Auch beim Verlassen einer Login-Shell finden letzte Aktivitäten statt, wenn es eine Datei »~/.bash_logout« gibt. Wer herausfinden will, welche Datei die Shell wann ausführt, trägt einfach kurze Statusmeldungen der Form »echo in /etc/profile« in die Startdateien ein (siehe Kasten “Bash-Startupskripte”).

### LPI-Aufgabengruppen

Das Linux Professional Institute gliedert die Prüfungsfragen in Aufgabengruppen. Dieser Artikel erklärt die Abschnitte:

1.109.1 Anpassung und Benutzung der Shellumgebung
1.109.2 Anpassen oder Schreiben einfacher Skripte


### Bash-Startupskripte

Wer herausfinden will, wann die Shell welche Startskripte abarbeitet, kann nach folgender Anleitung vorgehen. Sie ergänzt (beispielhaft auf einem Suse-Linux-System) die globalen Dateien »/etc/bash.bashrc« und »/etc/profile« sowie die benutzereigenen Dateien »~/.profile«, »~/.bashrc« und »~/.bash_logout« um Hello-World-Zeilen der Form:

echo ... in Dateiname
Für Login-Shells ergibt sich folgendes Bild:

login: Username
Password:
Last login: Thu Feb 15 16:39:55 from localhost
Have a lot of fun...
... in /etc/profile
... in /etc/bash.bashrc
... in ~/.bashrc
... in ~/.profile
$ logout
... in ~/.bash_logout
Für normale Shells sieh es hingegen so aus:

$ bash
... in /etc/bash.bashrc
... in ~/.bashrc
$ exit
Beim Start von Shellskripten, die ja selbst auch den Aufruf einer neuen Shell bewirken, erscheinen gar keine Meldungen, da es sich um keine interaktiven Shells handelt. Wer auch in einem Shellskript das Ausführen dieser Dateien erzwingen will, setzt in die erste Zeile zusätzlich die Bash-Option »-i« (interaktiv) oder »–login« (Login-Shell):

#!/bin/bash --login
Dann verhält sich die Shell entsprechend der gesetzten Option.

### Rückgabewerte
Externe Programme wie auch eingebaute Funktionen geben einen Wert an die Shell zurück: Der steht nach dem Aufruf in der Spezialvariablen »$?«, aber nur bis zum nächsten Befehlsaufruf:

$ gfdgfd; echo $?
bash: gfdgfd: command not found
127
Der Rückgabewert »0« bedeutet, dass der Befehlsaufruf erfolgreich war; alle anderen Werte stehen für einen Fehler. Je nach Programm haben die Fehlerwerte unterschiedliche Bedeutungen.


Über die Operatoren »||« (logisches Oder) und »&&« (logisches Und) ist eine bedingte Verknüpfung mehrerer Kommandos möglich: So führt »Befehl1 && Befehl2« dazu, dass die Shell den zweiten Befehl nur dann ausführt, wenn der erste Aufruf erfolgreich war, also »Befehl1« den Rückgabewert »0« hatte. Ein Beispiel dafür ist die Verknüpfung der Befehle aus dem klassischen Kompilier-Dreischritt: Schreibt der Anwender

./configure && make && make install
dann startet »make« nur, falls das Configure-Skript erfolgreich durchgelaufen ist. Genauso verzichtet die Shell auf den Aufruf von »make install«, wenn es bei den vorherigen zwei Kommandos zu Fehlern kam. Der »||«-Operator arbeitet ähnlich. Hier führt die Shell in der Sequenz »Befehl1 || Befehl2« das zweite Kommando aber nur dann aus, wenn das erste mit einem Fehler endete:

$ cat /etc/shadow 2>/dev/null || echo Darf Shadow-Datei nicht lesen
Darf Shadow-Datei nicht lesen
Die obige Ausgabe ist ein Beispiel für diesen Zusammenhang.

### Shell-Programmierung
Shellskripte enthalten in ihrer einfachsten Form Befehle und führen sie nacheinander aus. Programmierer verwenden aber außerdem Kontrollstrukturen, die den Programmfluss ändern – zum Beispiel If-Abfragen sowie For- und While-Schleifen. Um ein Shellskript als solches zu kennzeichnen, schreibt der Programmierer in die erste Zeile der Datei den so genannten She-Bang (»#!«) und den Pfad zur Shell, die dieses Skript interpretieren soll. Für Bash-Skripte lautet die erste Zeile also »#!/bin/bash«, während C-Shell- und Perl-Skripte mit »#!/bin/csh« oder »#!/usr/bin/perl« beginnen.

Um Shellskripte wie binäre Programme ausführbar zu machen, erhalten sie mit »chmod a+x Datei« Ausführrechte. Wer sie einfach beim Namen aufrufen will, kopiert sie in ein Verzeichnis, das im Pfad – definiert durch » – liegt. Für private Skripte könnte das »~/bin« sein, für systemweit verfügbare bietet sich »/usr/local/bin« an. Wer versucht mit »chmod u+s Skript« das SUID-Bit zu setzen, um normalen Anwendern die Skriptausführung mit Root-Rechten zu erlauben, scheitert: Zwar erscheint bei »ls« das SUID-Bit brav, es bleibt aber wirkungslos. Anders als bei einigen Unix-Versionen können Skripte unter Linux nicht die effektive User-ID ändern.

### Kontrollstrukturen
Ohne bedingte Code-Ausführung ist an Programmieren nicht zu denken. Ein elementares Konzept in allen Programmiersprachen ist der If-Then-Else-Block. In der Shell sieht er so aus:

```
if Bedingung
then
    Kommandos
else
    Kommandos
fi
```
Der »else«-Zweig ist optional. Um Platz zu sparen, darf alles in einer Zeile stehen – dann sind zusätzliche Semikola nötig:

if Bedingung; then Kommandos; else Kommandos; fi
Wichtig für das Verständnis der If-Anweisung ist vor allem eines: Die Bedingung nach dem Schlüsselwort »if« ist selbst ein Kommando. Wenn es mit Fehlercode »0« zurückkehrt, interpretiert die Shell dies als Wahrheitswert True und springt in den Then-Zweig, andernfalls in den Else-Zweig. Für Tests bieten sich die beiden Befehle »true« und »false« an, die nichts tun und die Rückgabewerte »0« beziehungsweise »1« haben.

Gern nutzen Programmierer in If-Anweisungen das interne Shellkommando »test«, das über zahlreiche Optionen (Tabelle 1) unter anderem Zahlen und Strings vergleicht sowie Prüfzugriffe auf Dateien und Verzeichnisse absolviert. Hier prüft »test«, ob eine Datei existiert:


$ if test -a /etc/fstab; then echo "Fstab ist da"; fi
Fstab ist da
Um Skripte besser lesbar zu machen, ist statt »test Optionen« auch die Schreibweise »[ Optionen ]« erlaubt. Der obige Aufruf hieße damit »[ -a /etc/fstab ]«. Plausibler wird der Nutzen dieser Darstellung bei String-Vergleichen: Der Versuch, zwei Variablen auf Gleichheit zu überprüfen, sieht in normaler »test«-Syntax und in Alternativnotation folgendermaßen aus:

if test $VAR1 = VAR2; then ...
if [ $VAR1 = $VAR2 ]; then ...
Neben den If-Then-Else-Blöcken sind vor allem For und While wichtig, um komplexere Programme zu schreiben. Die For-Schleife hat folgenden Aufbau:

for Variable in Werte; do Befehle ; done
Dabei nimmt die Variable nacheinander alle hinter »in« genannten Werte an und führt jeweils die Befehle aus. Diese können die Variable auslesen und abhängig vom Wert handeln. Ein Minibeispiel:

$ for i in 1 2 3; do echo $i; done
1
2
3
Die Werte dürfen Wildcards enthalten. So listet »for i in *; do echo ; done« alle Dateien und Verzeichnisse im Arbeitsverzeichnis. Die While-Schleife funktioniert ähnlich wie die If-Anweisung:

while Bedingung; do Befehle; done
Die Bedingung ist dabei wieder ein Kommando, dessen Rückgabewert »while« als Wahrheitswert interpretiert wird und entweder einen neuen Schleifendurchlauf startet oder die Schleife beendet.

Tabelle 1:
»test«-Optionen

 
Option

Funktion

-a Datei

Datei existiert

-d Datei

Datei ist ein Verzeichnis

-f Datei

Datei existiert und ist eine reguläre Datei

-r Datei

Datei existiert und ist für den aufrufenden Benutzer
lesbar

-w Datei

Datei existiert und ist für den aufrufenden Benutzer
schreibbar

-x Datei

Datei existiert und ist für den aufrufenden Benutzer
ausführbar

-z String

String ist leer (»””«)

-n String

String ist nicht leer

String1 = String2

Strings sind gleich

String1 != String2

Strings sind ungleich

String1 -lt String2

Erster String ist kleiner (»lt«: less than) als der
zweite; analog »le«: kleiner oder gleich

String1 -gt String2

Erster String ist größer (»gt«: greater
than) als der zweite; analog »ge«: größer
oder gleich

Backticks oder Klammern
Ein besonders nützliches Feature der Shell ist die Möglichkeit, die Ausgabe externer Programme unmittelbar als Argumente für andere Befehle weiterzuverwenden. Ein Beispiel dafür:

echo Test > log-$(date +%F).txt
Bei dieser Befehlszeile wertet die Shell zunächst den Befehl »date +%F« aus, der in »$( … )« eingeklammert ist. Das Ergebnis, beispielsweise »2007-02-15«, setzt die Bash dann an Stelle von »$(date +%F)« in die Zeile ein. Dadurch wandelt sich der Befehl im ersten Schritt zu:

echo Test > log-2007-02-15.txt
Hier sind keine weiteren Ersetzungen nötig, die Bash führt das Kommando aus und schreibt eine Testnachricht in die Datei. Neben der Schreibweise mit Dollarzeichen und öffnenden und schließenden Klammern existiert noch die ältere Notation, die Backticks (»`«) verwendet und den auszuwertenden Befehl damit einklammert. Der Beispielbefehl lautet in Backtick-Notation:

echo Test > log-`date +%F`.txt
Die geklammerte Variante hat den großen Vorteil, dass sie auch das Schachteln erlaubt, beispielsweise:

for i in $(find -name log-$(date +%F).txt)
do
   echo $i
done
Mit dem kleinen Tool »seq«, das aufeinander folgende Zahlen ausgibt, sind klassische For-Schleifen möglich, die eine Variable von einem Start- bis zu einem Endwert durchzählen: So wird aus dem C-Konstrukt »for (i=1; i<=MAX; i++) { … };« eine Shellschleife »for i in `seq 1 MAX`; do …; done«.

Funktionen in der Bash
Nicht immer muss es ein Skript sein, das die Shell erst auf der Festplatte sucht und startet – für viele Aufgaben eignen sich Shellfunktionen besser. Das sind kleine Skript-ähnliche Blöcke von Befehlen, die die Bash – in eine Funktionsdeklaration verpackt – wie Shellvariablen speichert. Manche Aufgaben kann überhaupt nur eine Shellfunktion lösen, etwa solche, bei denen lokale Variablen der Shell zu ändern sind. Versucht ein Administrator etwa, ein Skript namens »up« zu schreiben, das eine Verzeichnisebene nach oben springt, kommt er nicht zum Ziel. Sein »up«-Skript

#!/bin/bash
echo "Eine Ebene hoch"
cd ..
bewirkt nichts. Das liegt daran, dass beim Aufruf des Skripts eine neue Shell startet. In ihr führt das Skript zwar erfolgreich das »cd«-Kommando aus, aber dann beendet sich die Shell. Zurück in der aufrufenden Shell ist der Verzeichniswechsel nicht sichtbar, denn das Arbeitsverzeichnis ist (wie die Variablen) eine prozesseigene Eigenschaft. Mit einer Shellfunktion hingegen funktioniert es. Sie könnte wie folgt programmiert sein:

up () {
  echo "Eine Ebene hoch"
  cd ..
}
Oder kürzer in einer Zeile: »up () { echo “Eine Ebene hoch”; cd .. ; }«. Für die allgemeine Syntax gibt es zwei Möglichkeiten:

Funktionsname () { Befehle ; }
function Funktionsname { Befehle ; }
Dem Funktionsnamen folgen in der ersten Notation öffnende und schließende Klammern und dann in geschweiften Klammern der Funktionsrumpf, also die eigentlichen Befehle. Vor der schließenden geschweiften Klammer muss ein Semikolon stehen, falls Befehl und »}« in derselben Zeile stehen, und zwischen die öffnende geschweifte Klammer und den ersten Befehl gehört ein Leerzeichen, sonst ist die Funktionsdefinition syntaktisch falsch.

Shellfunktionen verstehen auch Funktionsargumente; der Zugriff darauf funktioniert genau wie bei Shellskripten, also über »$1«, »$2« und so weiter. Auch hier geben »$0« den Programmnamen, das ist immer der Name der Shell, und »$@« sämtliche Argumente zurück.

Das Kommando »set« zeigt neben den Variablen auch definierte Funktionen an. Die Beispielfunktion erscheint in der Ausgabe hübsch mit Einrückungen formatiert:

$ set
[...]
up ()
{
    echo "Eine Ebene hoch";
    cd ..
}
Ähnlich wie Variablen- finden auch Funktionsdeklarationen, die dauerhaft sein sollen, in den Startup-Dateien der Bash ihren Platz, etwa in »/etc/profile«.

Mit gutem Beispiel voran
Beispiele für alle beschriebenen Techniken finden sich an vielen Stellen eines Linux-Systems. Die erste Anlaufstelle ist das Verzeichnis »/etc/rc.d« oder »/etc/init.d«. Abbildung 2 zeigt ein Stück aus dem Init-Skript für VMware, das eine Funktionsdeklaration sowie eine While-Schleife, »if«, »then«, »else« und »test«-Abkürzungen mit »[ … ]« enthält


