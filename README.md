Die [Online-IDE](https://github.com/martin-pabst/Online-IDE) von [Martin Pabst](https://github.com/martin-pabst) ist eine komplett im Browser ausgeführte Entwicklungsumgebung für eine Untermenge der Programmiersprache Java.

Die IDE eignet sich besonders für das Erlernen von Java und für interaktive Java-Beispiele - mit [LearnJ](https://www.learnj.de/doku.php) existiert ein solcher interaktiver Java-Kurs, der in Bayern bereits an Gymnasien eingesetzt wird.

Eine etwas abgespeckte Variante der Online-IDE kann als [Embedded-IDE](https://github.com/martin-pabst/Online-IDE#2-embedded-ide) in eigene Web-Seiten integriert werden.

Möchte man auf Basis der "Embedded-IDE" eigene Beispiele oder gar einen eigenen Kurs auf GitHub veröffentlichen, stößt man jedoch bald auf ein grundsätzliches Problem: eine Reihe von HTML-Tags (wie z.B. `<script>` oder `<iframe>`) werden in Markdown-Dateien (wie z.B. README.md) nicht unterstützt und stattdessen wie normaler Text behandelt.

Die "offizielle" (und damit vermutlich dauerhaft unterstützte) Abhilfe ist der Umstieg auf [GitHub Pages](https://pages.github.com/). Zwar werden derartige Seiten ebenfalls aus Markdown-Dateien gespeist, allerdings findet zunächst eine Konvertierung nach HTML statt, die u.a. auch `<iframe>`-Elemente zulässt - und genau auf solche `<iframe>`-Elemente stützt sich das hier vorgestellte Verfahren.

> Nota bene: dieser Beitrag befindet sich gerade in Arbeit und wird vermutlich nicht vor Ende März 2022 fertig sein

## Beispiel ##
  
Hier können Sie sehen, wie das Ergebnis am Ende aussieht:
  
<iframe src="empty_Workspace.html" style="width:620px; height:480px; overflow:hidden"></iframe>

Sollten Sie sich gerade die README-Datei in desem Repository ansehen, werden Sie nur einen Text der Form
  
```
<iframe src="empty_Workspace.html" style="width:620px; height:480px; overflow:hidden"></iframe>
```
  
vorfinden - in diesem Fall wechseln Sie bitte auf die [zugehörige GitHub Page](https://rozek.github.io/online-ide-within-github-pages/), dort werden Sie die tatsächliche "Embedded-IDE" sehen und auch mit ihr arbeiten können.
  
## Integration in eigene Repositories ##

Eine "Embedded-IDE" kann von vorneherein mit einer oder mehreren Java-Dateien ausgestattet werden - zum Beispiel, um ein (nahezu) fertiges Beispiel zu präsentieren und den Benutzer von unnötger Tipparbeit zu entlasten. Es sind aber auch leere IDEs zulässig

### IDE mit leerem Workspace ###

"Leere" IDEs eignen sich besonders gut als "Spielwiese" für eigene Experimente oder um auf die Schnelle eine Idee auszuprobieren - ähnlich den REPLs in anderen Programmiersprachen.

Und so bauen Sie eine leere IDE in Ihre GitHub Page ein:

1. kopieren Sie die Datei [empty_Workspace](empty_Workspace.html) aus diesem Repository z.B. in das Hauptverzeichnis Ihres eigenen Repo - den Dateinamen können Sie dabei nach Belieben ändern
2. mit einem Texteditor (oder der Online-Oberfläche von GitHub) sollten Sie außerdem folgende Details anpassen:
    * die `id` im Attribut `data-java-online` sollte auf einen Wert gesetzt werden, der ggfs. sogar dateiübergreifend (nämlich Ihre gesamte GitHub-"Domäne") eineindeutig ist, damit evtl. im Browser gespeicherte Quelltexte nicht mit denen auf anderen GitHub Pages kollidieren
    * zusätzlich können Sie das Aussehen der "embedded IDE" durch weitere Eintragungen im Attribut `data-java-online` an Ihre Bedürfnisse anpassen (eine [Anleitung](https://github.com/martin-pabst/Online-IDE#das-attribut-data-java-online) dafür finden Sie im GitHub Repository der Online-IDE selbst)
    * zu guter Letzt können Sie im `<style>`-Element der Datei noch die Größe der IDE anpassen. Mit weiteren Änderungen des Aussehens sollte man vorsichtig sein, weil die Stileinstellungen der IDE von einem sehr dunklen Hintergrund ausgehen
3. die derart konfigurierte "embedded IDE" kann nun mithilfe der folgenden Direktive in die GitHub Page aufgenommen werden:<br>&nbsp;<br>`<iframe src="empty_Workspace.html" style="width:620px; height:480px; overflow:hidden"></iframe>`<br>&nbsp;<br>Die in Schritt 2 vorgenommenen Änderungen müssen ggfs. auch in diese Direktive eingepflegt werden:
    * statt des Dateinamens `empty_Workspace.html` sollten Sie den relativen Pfadnamen Ihrer eigenen HTML-Datei eintragen
    * die von Ihnen gewählte Größe für die IDE sollte sich auch in den Ausmaßen des `<iframe>`-Elementes widerspiegeln: tragen Sie aber nicht die tatsächlichen Größen der IDE ein sondern eine etwas größere Breite (z.B. 20px größer, für den vertikalen Rollbalken) und ggfs. eine etwas größere Höhe (z.B. mindestens 80px größer, um Platz für Ausgaben und Tips zu schaffen)

Das Ergebnis kann dann z.B. wie folgt aussehen:

<iframe src="empty_Workspace.html" style="width:620px; height:480px; overflow:hidden"></iframe>

### IDE mit vorgefertigtem Beispiel ###

1 `predefined-workspace.html` kopieren


## License ##

[MIT License](LICENSE.md)
