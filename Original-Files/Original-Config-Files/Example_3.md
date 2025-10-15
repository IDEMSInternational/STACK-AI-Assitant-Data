*** Question Variables ***
/* Generating random values for aa, bb, cc, dd */
aa: rand(2)+1;
bb: rand(6)-3;
cc: rand(8)-4;
dd: rand(4)-2;

/* Defining the initial equation with absolute values */
expr: abs(aa*x+bb)+cc=dd;
arg: aa*x+bb;
x_condition: -bb/aa;

/* Defining the expressions without absolute values */
expr_plus: aa*x+bb+cc=dd;
expr_minus: -aa*x-bb+cc=dd;

/* Solving the simplified equations */
splus: rhs(solve(expr_plus)[1]);
sminus: rhs(solve(expr_minus)[1]);
unchecked_a: union({splus}, {sminus});

/* Check if the solutions satisfy the original equation */
check_splus: is(ev(expr, x=splus));
check_sminus: is(ev(expr, x=sminus));

/* Collecting consistent solutions */
ta1: if check_splus then {splus} else {};
ta2: if check_sminus then {sminus} else {};

/* Merging both consistent solutions */
ta: union(ta1, ta2);


*** Question Text ***
<h3 style="text-align: center;"><br>

<p>Solve the following equation:<br> <br>{@expr@}</p>

</h3><br>
<p style="text-align: center;"><br>
Enter the set of solutions below.<br>
Hint: To type a set of numbers, use curly braces, like <code>{1, 2, 3 }</code>. If there are no solutions, type <code>{ }</code>.<br><br>
[[input:ans1]] [[validation:ans1]][[feedback:prt1]]</p>


*** General Feedback ***
<h3>Worked solution</h3>
<p>1) <strong>Identify the conditions:</strong></p><p>Since the expression inside the absolute value can be positive or negative, we may have a solution if either:</p><p></p><ul><li>\({@arg@}\geq0\) hence if \(x\geq{@x_condition@}\) and in this case we remove the absolute value and get {@expr_plus@} <br>or if</li><li>\({@arg@} < 0 \) hence if \( x < {@x_condition@} \) and in this case we remove the absolute value, change the signs of the terms in it and get {@expr_minus@}.</li></ul><p>2) <strong>Solve the equations:</strong></p>
<p>In the first case, we get \(\displaystyle {@splus@}\) as a possible solution.</p>
<p>Similarly, in the second case, we get \(\displaystyle {@sminus@}\) as another possible solution. </p><p>3) <strong>Check if the solutions are acceptable:</strong></p><p>We can accept a solution only if it satisfies its corresponding condition, therefore the set of solutions is: \(\displaystyle {@ta@}\)</p>
