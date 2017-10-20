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

## Cours 3

Présentation des méthodes à un pas du type Runge-Kutta pour ODE. Algorithmes et propriétés de stabilité

## Cours 3

Présentations des méthodes à plusieurs pas du type Adams-Bashworth, Adams-Moulton ou BDF pour ODE. Algorithmes et propriétés de stabilité.

## Cours 4

Adaptation des méthodes numériques à la résolution des équations algébro-différentielles.

## Cours 5

Notion d’index, méthodes de réduction d’index, ordre des méthodes pour résoudre les équations algébro-différentielles.

