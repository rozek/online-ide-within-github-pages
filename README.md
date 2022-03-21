Die [Online-IDE](https://github.com/martin-pabst/Online-IDE) von [Martin Pabst](https://github.com/martin-pabst) ist eine komplett im Browser ausgeführte Entwicklungsumgebung für eine Untermenge der Programmiersprache Java.

Die IDE eignet sich besonders für das Erlernen von Java und für interaktive Java-Beispiele - mit [LearnJ](https://www.learnj.de/doku.php) existiert ein solcher interaktiver Java-Kurs, der in Bayern bereits an Gymnasien eingesetzt wird.

Eine etwas abgespeckte Variante der Online-IDE kann als [Embedded-IDE](https://github.com/martin-pabst/Online-IDE#2-embedded-ide) in eigene Web-Seiten integriert werden.

Möchte man auf Basis der "Embedded-IDE" eigene Beispiele oder gar einen eigenen Kurs auf GitHub veröffentlichen, stößt man jedoch bald auf ein grundsätzliches Problem: eine Reihe von HTML-Tags (wie z.B. `<script>` oder `<iframe>`) werden in Markdown-Dateien (wie z.B. README.md) nicht unterstützt und stattdessen wie normaler Text behandelt.

Die "offizielle" (und damit vermutlich dauerhaft unterstützte) Abhilfe ist der Umstieg auf [GitHub Pages](https://pages.github.com/). Zwar werden derartige Seiten ebenfalls aus Markdown-Dateien gespeist, allerdings findet zunächst eine Konvertierung nach HTML statt, die u.a. auch `<iframe>`-Elemente zulässt - und genau auf solche `<iframe>`-Elemente stützt sich das hier vorgestellte Verfahren.

> Noch ein kleiner Hinweis: falls Sie diesen Beitrag mögen und selbst einsetzen, überlegen Sie doch, ob Sie ihn mit einem "Stern" versehen wollen (Sie finden die entsprechende Schaltfläche rechts oben auf der Seite mit dem [GitHub Repository](https://github.com/rozek/javascript-interface-library) - allerdings nicht auf der zugehörigen "GitHub Page"). Auf diese Weise kann ich erkennen, welche meiner Beiträge am häufigsten zum Einsatz kommen und dementsprechend mit höherer Priorität gepflegt werden sollten.

## Beispiel ##
  
Hier können Sie sehen, wie das Ergebnis am Ende aussieht:
  
<iframe src="Hello_World.html" style="width:600px; height:400px; overflow:hidden"></iframe>

Sollten Sie sich gerade die README-Datei in desem Repository ansehen, werden Sie nur einen Text der Form
  
```
<iframe src="Hello_World.html" style="width:600px; height:400px; overflow:hidden"></iframe>
```
  
vorfinden - in diesem Fall wechseln Sie bitte auf die [zugehörige GitHub Page](https://rozek.github.io/online-ide-within-github-pages/), dort werden Sie die tatsächliche "Embedded-IDE" sehen und auch mit ihr arbeiten können.
  
## Integration in eigene GitHub Pages ##

Eine "Embedded-IDE" kann von vorneherein mit einer oder mehreren Java-Dateien ausgestattet werden - zum Beispiel, um ein (nahezu) fertiges Beispiel zu präsentieren und dem Benutzer unnötige Tipparbeit zu ersparen. Es sind aber auch leere IDEs zulässig.

> Nota bene: bitte beachten Sie, daß Änderungen an Dateien im GitHub Repository erst nach einigen Minuten auf der zugehörigen GitHub Page erscheinen!

### IDE mit leerem Workspace ###

"Leere" IDEs eignen sich besonders gut als "Spielwiese" für eigene Experimente oder um auf die Schnelle eine Idee auszuprobieren - ähnlich den REPLs in anderen Programmiersprachen.

Und so bauen Sie eine leere IDE in Ihre GitHub Page ein:

1. kopieren Sie die Datei [empty_Workspace](empty_Workspace.html) aus diesem Repository z.B. in das Hauptverzeichnis Ihres eigenen Repo - den Dateinamen können Sie dabei nach Belieben ändern
2. mit einem Texteditor (oder der Online-Oberfläche von GitHub) sollten Sie außerdem folgende Details anpassen:
    * die `id` im Attribut `data-java-online` sollte auf einen Wert gesetzt werden, der ggfs. sogar dateiübergreifend (nämlich Ihre gesamte GitHub-"Domäne") eineindeutig ist, damit evtl. im Browser gespeicherte Quelltexte nicht mit denen auf anderen GitHub Pages kollidieren
    * zusätzlich können Sie das Aussehen der "embedded IDE" durch weitere Eintragungen im Attribut `data-java-online` an Ihre Bedürfnisse anpassen (eine [Anleitung](https://github.com/martin-pabst/Online-IDE#das-attribut-data-java-online) dafür finden Sie im GitHub Repository der Online-IDE selbst)
3. die derart konfigurierte "embedded IDE" kann nun mithilfe der folgenden Direktive in die GitHub Page aufgenommen werden:<br>&nbsp;<br>`<iframe src="empty_Workspace.html" style="width:600px; height:400px; overflow:hidden"></iframe>`<br>&nbsp;<br>Falls Sie die HTML-Datei nach dem Kopieren umbenannt (oder in einem Unterverzeichnis abgelegt) haben, müssen Sie anstelle von "empty_Workspace.html" natürlich den (relativen) Pfadnamen der von Ihnen angelegten Datei eintragen. Auch die Größe des `<iframe>` können Sie an Ihre Bedürfnisse anpassen - der Inhalt passt sich entsprechend an.

Das Ergebnis kann dann z.B. wie folgt aussehen:

<iframe src="empty_Workspace.html" style="width:600px; height:400px; overflow:hidden"></iframe>

Auch hier gilt wieder: Sie müssen sich auf der [GitHub Page](https://rozek.github.io/online-ide-within-github-pages/) zu diesem Repo befinden, um die IDE wirklich sehen zu können.

### IDE mit vorgefertigten Dateien ###

Wie zuvor schon erwähnt, kann eine "embedded IDE" jedoch auch mit bereits vorgefertigten Dateien ausgestattet werden, damit Benutzer nicht immer bei Null anfangen müssen. Der [predefined_Workspace](predefined_Workspace.html) ist ein Beispiel dafür und kann wie folgt in eine GitHub Page integriert werden:

1. kopieren Sie die Datei [predefined_Workspace](predefined_Workspace.html) aus diesem Repository z.B. in das Hauptverzeichnis Ihres eigenen Repo - den Dateinamen können Sie dabei nach Belieben ändern
2. mit einem Texteditor (oder der Online-Oberfläche von GitHub) sollten Sie außerdem folgende Details anpassen:
    * die `id` im Attribut `data-java-online` sollte auf einen Wert gesetzt werden, der ggfs. sogar dateiübergreifend (nämlich Ihre gesamte GitHub-"Domäne") eineindeutig ist, damit evtl. im Browser gespeicherte Quelltexte nicht mit denen auf anderen GitHub Pages kollidieren
    * die vorgefertigten Dateien können Sie als `<script>`-Elemente innerhalb der IDE anlegen - die [Dokumentation zur Online-IDE](https://github.com/rozek/Online-IDE#beispiel-mit-dateiliste-console-fehlerliste-und-tipp) enthält Beispiele hierfür
    * zusätzlich können Sie das Aussehen der "embedded IDE" durch weitere Eintragungen im Attribut `data-java-online` an Ihre Bedürfnisse anpassen (eine [Anleitung](https://github.com/martin-pabst/Online-IDE#das-attribut-data-java-online) dafür finden Sie im GitHub Repository der Online-IDE selbst)
3. die derart konfigurierte "embedded IDE" kann nun mithilfe der folgenden Direktive in die GitHub Page aufgenommen werden:<br>&nbsp;<br>`<iframe src="predefined_Workspace.html" style="width:600px; height:400px; overflow:hidden"></iframe>`<br>&nbsp;<br>Falls Sie die HTML-Datei nach dem Kopieren umbenannt (oder in einem Unterverzeichnis abgelegt) haben, müssen Sie anstelle von "predefined_Workspace.html" natürlich den (relativen) Pfadnamen der von Ihnen angelegten Datei eintragen. Auch die Größe des `<iframe>` können Sie an Ihre Bedürfnisse anpassen - der Inhalt passt sich entsprechend an.

Das Ergebnis kann dann z.B. wie folgt aussehen:

<iframe src="predefined_Workspace.html" style="width:600px; height:400px; overflow:hidden"></iframe>

Wie üblich gilt auch hier: Sie müssen sich auf der [GitHub Page](https://rozek.github.io/online-ide-within-github-pages/) zu diesem Repo befinden, um die IDE tatsächlich sehen zu können.

## Lizenz ##

Dieser Beitrag steht unter [MIT Lizenz](LICENSE.md)
