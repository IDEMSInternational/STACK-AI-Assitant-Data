*** Question Variables ***
/*Parte a*/
// Generazione di due intervalli casuali
aa: rand(20) - 10;
bb: aa + rand(4) + 1;
cc: rand(20) - 10;
dd: cc + rand(4) + 1;

// Calcolo del sup e del max
if bb >= dd then (sup: bb, max: bb) else (sup: dd, max: []);

// Calcolo dell'inf e del min
if aa <= cc then (inff: aa, min: aa) else (inff: cc, min: []);

// Variabili di risposta
ta_max: max;
ta_min: min;
ta_magg: co(sup, +inf);  // insieme dei maggioranti
ta_minn: oc(-inf, inff);  // insieme dei minoranti
ta_sup: sup;
ta_inff: inff;



*** Question Text ***
<h3 style="text-align: center;">
<br>Dei seguenti insiemi si dica se hanno massimo e minimo, se ne determini l’insieme dei maggioranti e dei minoranti, si determini sup e inf:<br>
a) \( [{@aa@}, {@bb@}] \ \cup \ ]{@cc@}, {@dd@}[ \) <br><br>
</h3>
<p style="text-align: center;">
max: [[input:ans_max]] min: [[input:ans_min]][[validation:ans_max]][[validation:ans_min]]<br>
maggioranti: [[input:ans_magg]] minoranti: [[input:ans_minn]][[validation:ans_magg]][[validation:ans_minn]]<br>
sup: [[input:ans_sup]] inf:[[input:ans_inff]][[validation:ans_sup]][[validation:ans_inff]] <br>
 <br>

Se un certo elemento non esiste inserire parentesi quadre vuote: [].<br>
La seguente tabella indica come inserire gli intervalli con estremi aperti/chiusi:
<table width="250" cellspacing="1" cellpadding="0" border="1" style="margin: 0 auto;">
  <tr>
    <th style="text-align: center;">Intervalli</th>
    <th style="text-align: center;">Sintassi da inserire</th>
  </tr>
  <tr>
    <td style="text-align: center;">\( [a,b] \)</td>
    <td style="text-align: center;"><code>cc(a,b)</code></td>
  </tr>
  <tr>
    <td style="text-align: center;">\( (a,b) \)</td>
    <td style="text-align: center;"><code>oo(a,b)</code></td>
  </tr>
  <tr>
    <td style="text-align: center;">\( [a,b) \)</td>
    <td style="text-align: center;"><code>co(a,b)</code></td>
  </tr>
  <tr>
    <td style="text-align: center;">\( (a,b] \)</td>
    <td style="text-align: center;"><code>oc(a,b)</code></td>
  </tr>
 <tr>
    <td style="text-align: center;">\( (a, \infty) \)</td>
    <td style="text-align: center;"><code>oo(a,inf)</code></td>
  </tr>
 <tr>
    <td style="text-align: center;">\( [a, \infty) \)</td>
    <td style="text-align: center;"><code>co(a,inf)</code></td>
  </tr>
 <tr>
    <td style="text-align: center;">\( (-\infty, b] \)</td>
    <td style="text-align: center;"><code>oc(-inf,b)</code></td>
  </tr>
 <tr>
    <td style="text-align: center;">\( (-\infty, \infty) \)</td>
    <td style="text-align: center;"><code>oo(-inf,inf)</code></td>
  </tr>
</table>
</p>


*** General Feedback ***
SOLUZIONE:<br>

I maggioranti/minoranti sono elementi maggiori/minori o uguali ad ogni elemento dell'insieme in esame. \(sup\) e \(min\) sono il minimo dei maggioranti (oppure \(-\infty\) e \(\infty\)) ed il massimo dei minoranti e questi esistono sempre grazie al 'maggiori/minori <b>o uguali</b>' nella definizione.<br>
Se \(sup\) e/o \(min\) appartengono all'insieme in analisi, allora essi coincidono con \(max\) e \(min\) dell'insieme stesso, altrimenti \(max\) e \(min\) non esistono.<br><br>

IN QUESTO CASO: <br>

{@sup@} è il minore dei maggioranti, ovvero il \(sup\). Il massimo è {@max@} a causa dell'apertura/chiusura dell'insieme.<br>
Similmente, in questo caso {@inff@} è il maggiore dei minoranti, ovvero l' \(inf\). Il minimo è {@min@} a causa dell'apertura/chiusura dell'insieme.
