Question Variables:
aa: rand_with_prohib(-5, 5, [0]);  /* Coefficiente di x^3 */
bb: rand(5)+1;                     /* Coefficiente di x */
f: aa*x^3 + bb*x;  /* Definizione del polinomio */

Question Text:
[[jsxgraph]]
    var board = JXG.JSXGraph.initBoard(divid, {
        boundingbox: [-10, 10, 10, -10],  // Definisci i limiti del grafico
        axis: true,  // Mostra gli assi cartesiani
        showCopyright: false
    });

    // Usa la funzione definita nelle Question Variables
    var f = board.jc.snippet('{#f#}', true, 'x', true);

    // Disegna il grafico della funzione tra x = -10 e x = 10
    board.create('functiongraph', [f, -10, 10]);
[[/jsxgraph]]
