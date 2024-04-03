# Dummy

## Dummy unterthema

### konkreter Dummy befehl

Aus Linux-Magazin 04/2007
##LPIC-1-Vorbereitung - Teil 9: Shell anpassen und Skripteschreiben

Von Hans-Georg Eßer

Das LPI-Zertifikat setzt den sicheren Umgang mit der Shell voraus. Administratoren müssen aber auch in der Lage sein, die Bash zu konfigurieren und nützliche Skripte zu programmieren. Die LPIC-Serie stellt diesmal die Prüfungsthemen aus Topic 109 vor.

Die Standardshell unter Linux ist die Bash. Auch wenn es die C-Shell, Tcsh, Korn-Shell und viele weitere gibt, die ebenfalls ihre Anhänger haben, sind für die LPI-Prüfung nur Bash-Kenntnisse relevant. Bei dem dabei abgefragten Wissen geht es um Shellvariablen, Skripte und die Konfiguration des Shellstarts über Profile-Dateien.

Shellvariablen setzt der Anwender mit »Variable=Wert« und ruft sie später durch ein vorangestelltes Dollarzeichen ab, etwa »echo . Häufig enthalten Shellskripte statt dieser einfachen Variante die Form »«. Sie macht zum einen deutlicher, an welcher Stelle der Name aufhört (Was bedeutet ».AZ«?), zum anderen ist es bei Zusammensetzungen manchmal die einzige Möglichkeit, Variablen und Strings zu kombinieren:

´´´
$ X="AAA"; Y="BBB"; XY="CCC"
$ echo $XY; echo ${XY}; echo ${X}Y; echo $X$Y
CCC
CCC
AAAY
AAABBB
´´´

