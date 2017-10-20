# Intégration numérique

## Cours 1

Introduction et presentation du problème de la simulation numérique. Présentation d’un moteur de simulation.

1. ODE : ordinary diffecential equation f(t, y, dydt, dy2dt2, ...) = 0
* IVP : initial value problem y(0) = const, dydt(0) = const, ...

2. Simulink
Kind of functions
* The output function
* The update function of discret-time state
* The update function of continuous-time state

3. DAE : differential algebraic equation f(t, y(t), x(t))=0
To make distinction, we rewrite it in the semi-explicit form:
(1) x'(t) = f(x(t), y(t), t)
(2) 0 = g(x(t), y(t), t) - free of derivatives => algebraic
On trouve la solution de la terme algebraic et ensuite la mettre à la prémière terme.

## Cours 2

Présentation des méthodes à un pas du type Runge-Kutta pour ODE. Algorithmes et propriétés de stabilité

1. Runge-Kutta methods
* It is naturally a format to present the numerical solution for a IVP.
* It is based on the Butcher table. 

|     |			|
|-----|-----------------|
| c1  | a11 a12 ... a1s |
| c2  | a21 a22 ... a2s |
| ... | ...             |
| cs  | as1 as2 ... ass |
|     | b1 b2 ... bs    |
|     | c1 c2 ... cs    | 
||ki = f(tn+ci*h, yn+h*sigma*(aij*kj)), yn+1 = yn+h*sigma*biki|

2. ExplicitRK - y'=f(t, y): En utilisant la condition de Taylor expansion 
* 1 stage - Euler's method (order 1) - Single-step fixed step-size ERK
* 2 stage - Heun's method (order 2) - Single-step fixed step-size ERK
* 4 stage - Bogacki-Shamine (ode23) - Single-step VARIABLE  step-size ERK

3. ImplicitRK - y'=f(y): s-stage method has order [less than] 2s
* Gauss IRK 2s, order 4, s=2
* Radau family 2s-1, order 3, s=2
* Lobatto family 2s-2, order 4, s=3 
* SDIRK family, order 4, s=5

4. 
* Step size control: success->increse h, failure->decrease h
* Total stability of IVP: small pertubation could not largely change the result
* Stiffness: The effect of the change of h to what extend it could change the final result

## Cours 3

Présentations des méthodes à plusieurs pas du type Adams-Bashworth, Adams-Moulton ou BDF pour ODE. Algorithmes et propriétés de stabilité.

### l'idée générale: 

reduire le nombre d'evaluer la fonc f(...) en reutilisant les résultats ce que on a déjà eu.

### Two difference operate - forward / backward

#### Adams Family

ExplicitAB formule: we do the integration for both sides of equation.
* n-order one could only be used after n-1 previous steps (not self starting method)
* step-size control is complicate 

ImplicitAM formule: similar to EAB, but not start from the t_k but t_k+1

ONLY for non-stiff problem!!!(except for AM1 AM2)

#### ImplitBackwardDifferenceFormule - for industrial codes Dymola

Not by integration but relay on the y_n, y_n-1, y_n-2...

### Summary
* they are computationaly cheaper than Runge-Kutta methods 
* they can vary in order

but
* variation of the step-size is possibly more computationnaly involve
* the properties of stability are weaker than Runge-Kutta methods
(may be sufficient for most of the problems)

## Cours 4

Adaptation des méthodes numériques à la résolution des équations algébro-différentielles.

We consider the DAE problem as infinitely stiff and thus we use stiffly stable ODE method to resolve DAE, such as BDF or Radau5.

## Cours 5

Notion d’index, méthodes de réduction d’index, ordre des méthodes pour résoudre les équations algébro-différentielles.

