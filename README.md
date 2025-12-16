# vicenterbs.github.io[AmigoSecreto.html](https://github.com/user-attachments/files/24177432/AmigoSecreto.html)
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <meta http-equiv="Content-Style-Type" content="text/css">
  <title></title>
  <meta name="Generator" content="Cocoa HTML Writer">
  <meta name="CocoaVersion" content="2299">
  <style type="text/css">
    p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Times; -webkit-text-stroke: #000000}
    p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Times; -webkit-text-stroke: #000000; min-height: 14.0px}
    span.s1 {font-kerning: none}
  </style>
</head>
<body>
<p class="p1"><span class="s1">&lt;!DOCTYPE html&gt;</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">&lt;div class="card"&gt;</span></p>
<p class="p1"><span class="s1">&lt;h1&gt;🎄 Amigo Secreto 🎁&lt;/h1&gt;</span></p>
<p class="p1"><span class="s1">&lt;p&gt;Selecciona quién eres para saber a quién te toca regalar.&lt;/p&gt;</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">&lt;select id="personSelect"&gt;</span></p>
<p class="p1"><span class="s1">&lt;option value=""&gt;-- Selecciona tu nombre --&lt;/option&gt;</span></p>
<p class="p1"><span class="s1">&lt;/select&gt;</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">&lt;button onclick="drawName()"&gt;Descubrir mi amigo secreto&lt;/button&gt;</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">&lt;div id="result" class="result" style="display:none"&gt;&lt;/div&gt;</span></p>
<p class="p1"><span class="s1">&lt;/div&gt;</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">&lt;script&gt;</span></p>
<p class="p1"><span class="s1">const people = [</span></p>
<p class="p1"><span class="s1">"Vicente Erbs (padre)",</span></p>
<p class="p1"><span class="s1">"Vicente Erbs (hijo)",</span></p>
<p class="p1"><span class="s1">"Catalina Erbs",</span></p>
<p class="p1"><span class="s1">"Guillermo Cantin",</span></p>
<p class="p1"><span class="s1">"Angela Gonzalez",</span></p>
<p class="p1"><span class="s1">"Oliva Loyo",</span></p>
<p class="p1"><span class="s1">"Cristobal Erbs",</span></p>
<p class="p1"><span class="s1">"Soledad Barros"</span></p>
<p class="p1"><span class="s1">];</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">const assignmentsKey = "amigoSecretoAssignments";</span></p>
<p class="p1"><span class="s1">const assignments = JSON.parse(localStorage.getItem(assignmentsKey)) || {};</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">const select = document.getElementById("personSelect");</span></p>
<p class="p1"><span class="s1">people.forEach(p =&gt; {</span></p>
<p class="p1"><span class="s1">if (!assignments[p]) {</span></p>
<p class="p1"><span class="s1">const opt = document.createElement("option");</span></p>
<p class="p1"><span class="s1">opt.value = p;</span></p>
<p class="p1"><span class="s1">opt.textContent = p;</span></p>
<p class="p1"><span class="s1">select.appendChild(opt);</span></p>
<p class="p1"><span class="s1">}</span></p>
<p class="p1"><span class="s1">});</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">function drawName() {</span></p>
<p class="p1"><span class="s1">const selected = select.value;</span></p>
<p class="p1"><span class="s1">if (!selected) {</span></p>
<p class="p1"><span class="s1">alert("Por favor selecciona tu nombre");</span></p>
<p class="p1"><span class="s1">return;</span></p>
<p class="p1"><span class="s1">}</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">if (assignments[selected]) {</span></p>
<p class="p1"><span class="s1">showResult(assignments[selected]);</span></p>
<p class="p1"><span class="s1">return;</span></p>
<p class="p1"><span class="s1">}</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">const alreadyTaken = Object.values(assignments);</span></p>
<p class="p1"><span class="s1">let available = people.filter(p =&gt; p !== selected &amp;&amp; !alreadyTaken.includes(p));</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">if (available.length === 0) {</span></p>
<p class="p1"><span class="s1">alert("No quedan opciones disponibles");</span></p>
<p class="p1"><span class="s1">return;</span></p>
<p class="p1"><span class="s1">}</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">const chosen = available[Math.floor(Math.random() * available.length)];</span></p>
<p class="p1"><span class="s1">assignments[selected] = chosen;</span></p>
<p class="p1"><span class="s1">localStorage.setItem(assignmentsKey, JSON.stringify(assignments));</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">showResult(chosen);</span></p>
<p class="p1"><span class="s1">}</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1">function showResult(name) {</span></p>
<p class="p1"><span class="s1">const result = document.getElementById("result");</span></p>
<p class="p1"><span class="s1">result.style.display = "block";</span></p>
<p class="p1"><span class="s1">result.innerHTML = `</span></p>
<p class="p1"><span class="s1">&lt;h3&gt;🎁 Te toca regalar a:&lt;/h3&gt;</span></p>
<p class="p1"><span class="s1">&lt;strong&gt;${name}&lt;/strong&gt;</span></p>
<p class="p1"><span class="s1">&lt;p style="margin-top:1rem"&gt;</span></p>
<p class="p1"><span class="s1">📍 Los regalos se entregan la noche del &lt;strong&gt;24 de diciembre&lt;/strong&gt;&lt;br&gt;</span></p>
<p class="p1"><span class="s1">🏠 En la casa de &lt;strong&gt;Catalina Erbs&lt;/strong&gt;&lt;br&gt;</span></p>
<p class="p1"><span class="s1">💰 Presupuesto máximo: &lt;strong&gt;$30.000 por persona&lt;/strong&gt;</span></p>
<p class="p1"><span class="s1">&lt;/p&gt;</span></p>
<p class="p1"><span class="s1">&lt;p&gt;&lt;em&gt;No compartas este resultado 😉&lt;/em&gt;&lt;/p&gt;</span></p>
<p class="p1"><span class="s1">`;</span></p>
<p class="p1"><span class="s1">}</span></p>
<p class="p1"><span class="s1">&lt;/script&gt;</span></p>
<p class="p1"><span class="s1">&lt;/body&gt;</span></p>
<p class="p1"><span class="s1">&lt;/html&gt;</span></p>
</body>
</html>
