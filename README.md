Die [Online-IDE](https://github.com/martin-pabst/Online-IDE) von [Martin Pabst](https://github.com/martin-pabst) ist eine komplett im Browser ausgeführte Entwicklungsumgebung für eine Untermenge der Programmiersprache Java.

Die IDE eignet sich besonders für das Erlernen von Java und für interaktive Java-Beispiele - mit [LearnJ](https://www.learnj.de/doku.php) existiert ein solcher interaktiver Java-Kurs, der in Bayern an Gymnasien eingesetzt wird.

Eine etwas abgespeckte Variante der Online-IDE kann als [Embedded-IDE](https://github.com/martin-pabst/Online-IDE#2-embedded-ide) in eigene Web-Seiten integriert werden.

Möchte man auf Basis der "Embedded-IDE" eigene Beispiele oder gar einen eigenen Kurs auf GitHub veröffentlichen, stößt man jedoch bald auf ein grundsätzliches Problem: eine Reihe von HTML-Tags (wie z.B. <script> oder <iframe>) werden in Markdown-Dateien (wie z.B. README.md) nicht unterstützt und stattdessen wie normaler Text behandelt.

Die "offizielle" (und damit vermutlich dauerhaft unterstützte) Abhilfe ist der Umstieg auf [GitHub Pages](https://pages.github.com/). Zwar werden derartige Seiten ebenfalls aus Markdown-Dateien gespeist, allerdings findet zunächst eine Konvertierung nach HTML statt, die u.a. auch <iframe>-Elemente zulässt.

wie man die Online-IDE in GitHub Pages integriert

<iframe src="Template.html" style="width:620px; height:480px; overflow:hidden"></iframe>
