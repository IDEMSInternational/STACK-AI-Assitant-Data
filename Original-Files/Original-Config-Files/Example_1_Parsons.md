*** Question Variables ***
stack_include("contribl://prooflib.mac");
ta2:p;
ta3:1;
ta4:1;

/* Definire i passaggi della prova */
proof_steps: [
    ["block1", "Supponiamo che l'identità sia vera per un certo \\( n \\geq p \\), cioè:
\\[
\\sum_{j=p}^{n} \\binom{j}{p} = \\binom{n+1}{p+1}
\\]
Dobbiamo dimostrare che l'identità è vera anche per \\( n+1 \\), cioè:
\\[
\\sum_{j=p}^{n+1} \\binom{j}{p} = \\binom{n+2}{p+1}.
\\]"],

    ["block2", "Espandiamo la somma per \\( n+1 \\):
\\[
\\sum_{j=p}^{n+1} \\binom{j}{p} = \\left( \\sum_{j=p}^{n} \\binom{j}{p} \\right) + \\binom{n+1}{p}
\\]"],

    ["block3", "Usando l'ipotesi induttiva:
\\[
\\sum_{j=p}^{n+1} \\binom{j}{p} = \\binom{n+1}{p+1} + \\binom{n+1}{p}
\\]"],

    ["block4", "Utilizzando le proprietà del binomiale:
\\[
\\binom{n+1}{p+1} + \\binom{n+1}{p} = \\binom{n+2}{p+1}
\\]
Quindi:
\\[
\\binom{n+1}{p+1} = \\binom{n+2}{p+1} - \\binom{n+1}{p}
\\]"],

    ["block5", "Sostituendo si ottiene:
\\[
\\sum_{j=p}^{n+1} \\binom{j}{p} = \\binom{n+2}{p+1}
\\]"],

    ["block6", "Abbiamo così dimostrato che se l'identità è vera per \\( n \\), allora è vera anche per \\( n+1 \\).
"]
];

/* Definire la struttura della prova */
ta: proof("block1", "block2", "block3", "block4", "block5", "block6");
ta1: proof_alternatives(ta);

/* Randomizzare l'ordine dei passaggi della prova */
proof_steps: random_permutation(proof_steps);


*** Question Text ***
<h3 style="text-align: center;"><br>
<p>Sia \( p \geq 0 \) un numero naturale fissato. <br>
Dimostrare che per ogni \( n \geq p \) si ha:</p>
\[
\sum_{j=p}^{n} \binom{j}{p} = \binom{n+1}{p+1}.
\]</h3><br>
<p style="text-align: center;"><br>Puoi affrontare l'esercizio per conto tuo e/o visualizzare una soluzione interattiva: </p><br>

<div style="text-align: center;">
  <span style="display: inline-block;"><br>
    [[hint title="MOSTRA ESERCIZIO GUIDATO"]]<br>
    <div style="text-align: left;">

<p>Il caso base si ha con \(n\)=[[input:ans2]]. [[validation:ans2]] Sostituendo in questo caso si ottiene:</p> 
[[input:ans3]]\(=\)[[input:ans4]] 
[[validation:ans3]][[validation:ans4]]
<p>Quindi il caso base è verificato.</p>

<p>Cominciamo il prossimo passo ricordando che una delle proprietà dei coefficienti binomiali è \(\binom{n+1}{j} = \binom{n}{j-1} + \binom{n}{j}\) ed utilizzando l'induzione questa proprietà sembra particolarmente promettente data la relazione fra \(n\) ed \(n+1\).</p>

<p>[[parsons input="ans1"]] {# stackjson_stringify(proof_steps) #} [[/parsons ]]</p>
<p></p>
<p style="display: none;">[[input:ans1]] [[validation:ans1]] [[feedback:prt1]]</p>
    [[/hint]]
</div>
</span>
</div>


*** General Feedback ***

<p>{@proof_display(ta, proof_steps)@}</p>
