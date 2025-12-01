<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<title>Freundschafts-Quest</title>
<style>
body {
    background:#0f0f0f;
    color:#fff;
    font-family: Arial, sans-serif;
    padding:20px;
    line-height:1.6;
}
.container {
    max-width:600px;
    margin:auto;
}
h1, h2 { text-align:center; }
.level {
    background:#1a1a1a;
    padding:20px;
    border-radius:8px;
    margin-top:20px;
}
input {
    width: 100%;
    padding: 10px;
    font-size:16px;
    margin-top:10px;
    border-radius:5px;
    border:none;
}
button {
    width: 100%;
    margin-top:10px;
    padding:10px;
    font-size:16px;
    border:none;
    border-radius:5px;
    background:#ffcc00;
    cursor:pointer;
}
.hidden { display:none; }
.message { margin-top:10px; font-weight:bold; }
</style>
</head>
<body>
<div class="container">

<h1>🗝️ Die Freundschafts-Quest</h1>
<p style="text-align:center;">Löse alle Rätsel, um die geheime Botschaft zu finden!</p>

<!-- LEVEL 1 -->
<div class="level" id="lvl1">
    <h2>Level 1 — Binary</h2>
    <p>01000100 01110101</p>
    <p><i>Hinweis: ASCII Code → Text</i></p>
    <input id="input1" placeholder="Lösungswort eingeben">
    <button onclick="check1()">Prüfen</button>
    <p class="message" id="msg1"></p>
</div>

<!-- Zwischentext nach Level 1 -->
<div class="level hidden" id="hint1">
    <p>Sehr gut! Du hast das erste Artefakt gefunden. Aber das Abenteuer geht weiter…</p>
    <button onclick="showLevel('lvl2')">Weiter zu Level 2</button>
</div>

<!-- LEVEL 2 -->
<div class="level hidden" id="lvl2">
    <h2>Level 2 — ROT13</h2>
    <p>znpu fg</p>
    <p><i>Hinweis: Drehe jeden Buchstaben um 13 Stellen</i></p>
    <input id="input2" placeholder="Lösungswort eingeben">
    <button onclick="check2()">Prüfen</button>
    <p class="message" id="msg2"></p>
</div>

<!-- Zwischentext nach Level 2 -->
<div class="level hidden" id="hint2">
    <p>Super! Artefakt 2 liegt vor dir. Nur noch zwei Rätsel und die Botschaft ist enthüllt.</p>
    <button onclick="showLevel('lvl3')">Weiter zu Level 3</button>
</div>

<!-- LEVEL 3 -->
<div class="level hidden" id="lvl3">
    <h2>Level 3 — Base64</h2>
    <p>bWljaA==</p>
    <p><i>Hinweis: Base64 → Text</i></p>
    <input id="input3" placeholder="Lösungswort eingeben">
    <button onclick="check3()">Prüfen</button>
    <p class="message" id="msg3"></p>
</div>

<!-- Zwischentext nach Level 3 -->
<div class="level hidden" id="hint3">
    <p>Fast geschafft! Das letzte Artefakt erwartet dich. Gib nicht auf!</p>
    <button onclick="showLevel('lvl4')">Weiter zu Level 4</button>
</div>

<!-- LEVEL 4 -->
<div class="level hidden" id="lvl4">
    <h2>Level 4 — Morse</h2>
    <p>..-.  .-.  ---  ....</p>
    <p><i>Hinweis: Leerzeichen = neue Buchstaben</i></p>
    <input id="input4" placeholder="Lösungswort eingeben">
    <button onclick="check4()">Prüfen</button>
    <p class="message" id="msg4"></p>
</div>

<!-- Finale Nachricht -->
<div class="level hidden" id="final">
    <h2>🎉 Finale Botschaft</h2>
    <p style="font-size:20px; text-align:center; color:#ffcc00;">
        Du machst mich froh 💛
    </p>
</div>

</div>

<script>
// Funktion zum Anzeigen des nächsten Levels nach Zwischentext
function showLevel(id) {
    document.getElementById(id).classList.remove('hidden');
}

// Überprüfungsfunktionen
function check1() {
    let v = document.getElementById("input1").value.trim().toLowerCase();
    if(v === "du") {
        document.getElementById("msg1").innerHTML="✔️ Richtig!";
        document.getElementById("lvl1").classList.add("hidden");
        document.getElementById("hint1").classList.remove("hidden");
    } else { document.getElementById("msg1").innerHTML="❌ Versuch es nochmal!"; }
}

function check2() {
    let v = document.getElementById("input2").value.trim().toLowerCase();
    if(v === "machst") {
        document.getElementById("msg2").innerHTML="✔️ Richtig!";
        document.getElementById("lvl2").classList.add("hidden");
        document.getElementById("hint2").classList.remove("hidden");
    } else { document.getElementById("msg2").innerHTML="❌ Versuch es nochmal!"; }
}

function check3() {
    let v = document.getElementById("input3").value.trim().toLowerCase();
    if(v === "mich") {
        document.getElementById("msg3").innerHTML="✔️ Richtig!";
        document.getElementById("lvl3").classList.add("hidden");
        document.getElementById("hint3").classList.remove("hidden");
    } else { document.getElementById("msg3").innerHTML="❌ Versuch es nochmal!"; }
}

function check4() {
    let v = document.getElementById("input4").value.trim().toLowerCase();
    if(v === "froh") {
        document.getElementById("msg4").innerHTML="✔️ Geschafft!";
        document.getElementById("lvl4").classList.add("hidden");
        document.getElementById("final").classList.remove("hidden");
    } else { document.getElementById("msg4").innerHTML="❌ Versuch es nochmal!"; }
}
</script>

</body>
</html>

