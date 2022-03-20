Die [Online-IDE](https://github.com/martin-pabst/Online-IDE) von [Martin Pabst](https://github.com/martin-pabst) ist eine komplett im Browser ausgeführte Entwicklungsumgebung für eine Untermenge der Programmiersprache Java.

Die IDE eignet sich besonders für das Erlernen von Java und für interaktive Java-Beispiele - mit [LearnJ](https://www.learnj.de/doku.php) existiert ein solcher interaktiver Java-Kurs, der in Bayern bereits an Gymnasien eingesetzt wird.

Eine etwas abgespeckte Variante der Online-IDE kann als [Embedded-IDE](https://github.com/martin-pabst/Online-IDE#2-embedded-ide) in eigene Web-Seiten integriert werden.

Möchte man auf Basis der "Embedded-IDE" eigene Beispiele oder gar einen eigenen Kurs auf GitHub veröffentlichen, stößt man jedoch bald auf ein grundsätzliches Problem: eine Reihe von HTML-Tags (wie z.B. `<script>` oder `<iframe>`) werden in Markdown-Dateien (wie z.B. README.md) nicht unterstützt und stattdessen wie normaler Text behandelt.

Die "offizielle" (und damit vermutlich dauerhaft unterstützte) Abhilfe ist der Umstieg auf [GitHub Pages](https://pages.github.com/). Zwar werden derartige Seiten ebenfalls aus Markdown-Dateien gespeist, allerdings findet zunächst eine Konvertierung nach HTML statt, die u.a. auch `<iframe>`-Elemente zulässt - und genau auf solche `<iframe>`-Elemente stützt sich das hier vorgestellte Verfahren.

> Nota bene: dieser Beitrag befindet sich gerade in Arbeit und wird vermutlich nicht vor Ende März 2022 fertig sein

## Beispiel ##
  
Hier können Sie sehen, wie das Ergebnis am Ende aussieht:
  
<iframe src="Template.html" style="width:620px; height:480px; overflow:hidden"></iframe>

Sollten Sie sich gerade die README-Datei in desem Repository ansehen, werden Sie nur einen Text der Form
  
```
<iframe src="Template.html" style="width:620px; height:480px; overflow:hidden"></iframe>
```
  
vorfinden - in diesem Fall wechseln Sie bitte auf die [zugehörige GitHub Page](https://rozek.github.io/online-ide-within-github-pages/), dort werden Sie die tatsächliche "Embedded-IDE" sehen und auch mit ihr arbeiten können.
  
## Integration in eigene Repositories ##

### IDE mit leerem Workspace ###

* `empty-Workspace.html` aus diesem Repo in das eigenen Repository kopieren (und ggfs. umbenennen
* ggfs. Größe in `empty-Workspace.html` anpassen
* folgende Zeile in Markdown-Datei einfügen<br>`<iframe src="empty-Workspace.html" style="width:620px; height:480px; overflow:hidden"></iframe>`

ggfs. Größenangaben darin anpassen

### IDE mit vorgefertigtem Beispiel ###

1 `predefined-workspace.html` kopieren


## License ##

[MIT License](LICENSE.md)
