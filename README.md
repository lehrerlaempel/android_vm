# Tutorial: Wie man Android in einer virtuelle Maschine nutzt (Eine Anleitung)
v 0.2 | Stand: November 2021 | Lizenz: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.de)

Weitere Anleitungen von uns findet man [hier](https://lehrerlaempel.github.io/anleitungen/)!

# Der Plan
Wir wollen Ihnen hier zeigen, wie Sie auf Ihrem Computer ein funktionierendes Android-Betriebssystem in einer Virtuellen Maschine (VM) installieren und nutzen können. So kann man verschiedene Android-Systeme simulieren, ohne sich tatsächlich diverse Smartphones zulegen zu müssen.

Wir nutzen für diese Anleitung für die Virtualisierungs-Software [VirtualBox](https://www.virtualbox.org/), als Betriebsystem [Android x86](https://www.android-x86.org/).


# Vorbereitung
## Virtual Box
Zunächst benötigt man die Software [VirtualBox](https://www.virtualbox.org/wiki/Downloads). Sofern diese noch nicht installiert ist, können Windows-Nutzer:innen einfach über den Link die passende Version (*Windows hosts*) herunterladen und installieren. Vor der Installation nicht vergessen, die Prüfsummen zu vergleichen!
Linux-Nutzer:innen können in der Regel VirtualBox bequem über den vorhandenen AppStore installieren.

## Android
Außerdem benötigen wir noch das Android, das wir später installieren möchten. Wir laden uns also von [hier](https://www.android-x86.org/download.html) die 64bit Version der passenden ISO-Datei herunter. 

Was wir mit passend meinen?

Wer ein klassisches **Google-Android** möchte, läd sich bitte die neuste Android-x86 Version herunter, die dann z.B. so heißt: *android-x86_64-9.0-r2.iso* 

(Derzeit ein Android 9 mit Sicherheitspatch-Stand August 2018...)


Wer hingegen ein **LineageOS** möchte, sucht bitte nach dem neusten CM Release, das dann z.B. so heißt: *cm-x86_64-14.1-r5.iso*

(Derzeit ein Android 7 mit Sicherheispatch-Stand Februar 2021...)

Auch hier nicht vergessen, nach dem Download die Prüfsummen zu vergleichen!

# VM Erstellen
Wir öffnen VirtualBox und erstellen eine neu VM mit folgenden Einstellungen:

- Name: Freie Wahl ;-)
- Typ: Linux
- Version: Linux 2.6 / 3.x / 4.x (64-bit)
- Speichergröße (RAM): Zum Beispiel 4096MB. Wichtig: Für das Host-System mindestens ebenfalls 4GB übrig lassen!
- Platte: dynamische Festplatte erzeugen, je nach späterem Einsatzzweck mit mindestens 10GB

Bevor wir die VM jetzt starten, gehen wir in die Einstellungen unsere VM und ändern folgende Optionen:

- System / Prozessor / Prozessoren: Das maximal mögliche im grünen Bereich auswählen
- Anzeige / Bildschirm / Grafikspeicher: Auf das Maximum erhöhen
- Anzeige / Bildschirm / Grafik-Controller: VBoxVGA
- Massenspeicher: Auf die blaue CD mit dem Namen *leer* klicken, dann rechts hinter *Optisches Laufwerk* auf die blaue CD mit dem Pfeil nach unten klicken. Hier die heruntergeladene ISO auswählen

# Installation
Jetzt starten wir unsere VM und wählen zunächst *Installation - Install Android-x86 to harddisk*.

In dem nun auftauchenden Fester wird vermutlich keine Partition angezeigt. Also wählen wir *Create/Modify partitions* und dann *yes* bei der Frage, ob wir GPT nutzen möchten.

Nun müssten wir *free space* in der vorher gewählten Festplattengröße sehen. Hier einfach *New* wählen und dann die vorgegebenen default Werte eingeben. Als Name dann z.B. *platte* eingeben. Anschließend müsste in der Liste der *free space* deutlich kleiner geworden sein, dafür aber ein *Linux filesystem* in der von uns gewünschten Größe aufgetaucht sein. 

Um diese änderung zu bestätigen, wählen wir nun unten "Write" und bestätigen das durch eine eingabe von *yes* (englisches Tastaturlayout beachten).

Wenn wir jetzt *Quit* wählen, kommen wir zurück zur Partitionsauswahl, wo wir nun unsere Festplatte wählen können.

Dann wählen wir *ext4* als Dateiformat, bestätigen die Formatierung und wählen dann, dass wir *GRUB* installieren möchten. Die Option *system directory as read-write* hingegen lehnen wir ab.

Sobald die Meldung *Adnroid-x86 is installed successfully* erscheint, schließen wir die VM über das X oben rechts und wählen *Die virtuelle Maschine ausschalten*.

Jetzt in den Einstellungen der VM unter *Massenspeicher* die Installationsdatei wieder über einen klick auf die CD mit dem blauen Pfeil entfernen.

# Der erste Start
Jetzt können wir die VM starten. Zunächst wählen wir *Deutsch (Deutschland)* und wählen dann über *alle Netze anzeigen* das W-LAN *VirtWifi*.

Fertig. Alle weiteren Hinweise zur datensparsamen Einrichtung und zum sicheren Betrieb von Android haben wir [hier](https://lehrerlaempel.github.io/androideinrichten/) schonmal ausführich niedergeschrieben, das müssen wir hier jetzt nicht wiederholen.

Fertig. Viel Spaß :-)

# Das Kleingedruckte
## Fehlerteufel
Diese Anleitung wurde von [lehrerlaempel](https://github.com/lehrerlaempel) nach bestem Wissen und Gewissen erstellt. Wir haben die feste Absicht, diese im Laufe der Zeit an Änderungen der erwähnten Software anzupassen und um weitere Aspekte zu ergänzen. Den Stand der Ihnen vorliegenden Version finden Sie ganz am Anfang der Seite.

Ihnen sind Fehler aufgefallen? Sie haben Verbesserungs- oder Änderungswünsche? Dann nehmen Sie gerne [Kontakt](https://lehrerlaempel.github.io/anleitungen/) mit uns auf. Wir sind tatsächlich sehr an Ihrer Rückmeldung interessiert!

Im Rahmen unserer Möglichkeiten haben wir auch versucht sicherzustellen, dass sowohl diese Seite selbst, als auch die von uns verlinkten Seiten sowohl legaler als auch legitimer Natur sind. Sollten uns Fehler unterlaufen sein oder wir änderungen verlinkter Seiten verpasst haben, geben Sie und gerne ein Zeichen, damit wir das zeitnah beheben können.

Wir übernehmen explizit keinerlei Haftung für die hier getroffenen Aussagen oder möglicherweise daraus entstandene Datenverluste oder sonstigen Schäden. Wir haben diese Texte nach bestem Wissen und Gewissen verfasst, sind aber wie alle Menschen fehlbar. Verstehen Sie diese Anleitungen also bitte als aufrichtig wohlmeindende Ratschläge auf Augenhöhe, jedoch ohne jede Gewähr.

## Lizenz
Dieser Text steht unter einer CC-Lizenz, ist also quasi schöpferisches Gemeingut.

Sie dürfen:
- **Teilen** das Material in jedwedem Format oder Medium vervielfältigen und weiterverbreiten
- **Bearbeiten** das Material remixen, verändern und darauf aufbauen

Der Lizenzgeber kann diese Freiheiten nicht widerrufen solange Sie sich an die Lizenzbedingungen halten.

Unter folgenden Bedingungen:
- **Namensnennung** Sie müssen angemessene Urheber- und Rechteangaben machen, einen Link zur Lizenz beifügen und angeben, ob Änderungen vorgenommen wurden. Diese Angaben dürfen in jeder angemessenen Art und Weise gemacht werden, allerdings nicht so, dass der Eindruck entsteht, der Lizenzgeber unterstütze gerade Sie oder Ihre Nutzung besonders.
- **Weitergabe unter gleichen Bedingungen** Wenn Sie das Material remixen, verändern oder anderweitig direkt darauf aufbauen, dürfen Sie Ihre Beiträge nur unter derselben Lizenz wie das Original verbreiten. 
- **Keine weiteren Einschränkungen** Sie dürfen keine zusätzlichen Klauseln oder technische Verfahren einsetzen, die anderen rechtlich irgendetwas untersagen, was die Lizenz erlaubt. 

Hinweise:
- Sie müssen sich nicht an diese Lizenz halten hinsichtlich solcher Teile des Materials, die gemeinfrei sind, oder soweit Ihre Nutzungshandlungen durch Ausnahmen und Schranken des Urheberrechts gedeckt sind.
- Es werden keine Garantien gegeben und auch keine Gewähr geleistet. Die Lizenz verschafft Ihnen möglicherweise nicht alle Erlaubnisse, die Sie für die jeweilige Nutzung brauchen. Es können beispielsweise andere Rechte wie Persönlichkeits- und Datenschutzrechte zu beachten sein, die Ihre Nutzung des Materials entsprechend beschränken.

*Dies war eine allgemeinverständliche Zusammenfassung der [Lizenz](https://creativecommons.org/licenses/by-sa/4.0/legalcode.de), die diese nicht ersetzt.*


