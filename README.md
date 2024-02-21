# Diagramas de Flujo Reto 2 y 3
<table cellspacing="1" bgcolor="">
  <tr bgcolor="#252582">
    <th><b>Reto 2</b></th>
  </tr>
  <tr bgcolor="#e4e4ed">
    <td style="color:#141414" align="center">A partir del algoritmo de identificación de los divisores plantear la serie de pasos para determinar los números primos hasta un natural n.</td>
  </tr>
</table>

<p>Los números primos son números enteros mayores que 1 y que solo tienen dos divisores distintos: 1 y el propio número primo; es decir, un número primo solo es divisible por él y por sí mismo. Sin embargo, una característica que los hace fascinantes en el mundo de las matemáticas es su distribución aparentemente aleatoria, la cual dificulta la tarea al momento de encontrar números primos grandes, puesto que no existe una formula para obtener todos estos números. Es por ello, que, en el planteamiento del algoritmo, me base en la división por todos los números menores a n, en caso de que alguno de estos coeficientes sea entero el número no es primo, lo que nos lleva a un largo proceso en donde se realizan n-1 divisiones.</p>

<p><b>Algoritmo planteado:</b></p>

```mermaid
flowchart TD;
    A[Inicio] -->|Ingrese un número n diferente de 1| B(m = 2)
    B --> C(n/m = c)
    C --> D{c es un número entero}
    D -->|Sí| E{m = n}
    E -->|Sí| G(n es primo)
    E -->|No| H(n no es primo)
    D -->|No| F[m+1 = m] --> C
    H -->I(Fin)
    G -->I(Fin)
```
<table cellspacing="1" bgcolor="">
  <tr bgcolor="#252582">
    <th><b>Reto 3</b></th>
  </tr>
  <tr bgcolor="#e4e4ed">
    <td style="color:#141414" align="center">Revise el procedimiento matemático para hallar raíces cuadradas (son divisiones y restas), plantee el algoritmo en pseudocódigo y en diagrama de flujo.</td>
  </tr>
</table>

<b>Método Newton-Raphson</b>
<p>El algoritmo planteado se basa en el método Newton-Raphson desarrollado por dos matemáticos de manera independiente en el siglo XVII. Este método es una técnica de iterativa que se utiliza para aproximar raíces de una función, en el caso del reto, la raíz cuadrada. Este procedimiento comienza con la suposición de una raíz y luego se mejora repetidamente esta suposición utilizando la regla de la tangente de la curva de la función en el punto actual; lo cual nos da como resultado la formula de iteración del método Newton-Raphson:</p>
<p>$$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}$$</p>

<p>Lo cual se traduce en:</p>
<p>$$x_{n+1} = \frac{x_n + \frac{m}{x_n}}{2}$$</p>
<p>Donde:</p>
<ul type="circle">
  <li>La suposición actual de la raíz cuadrada es:</li>
  $$x_{n}$$
  <li>La siguiente aproximación de la raíz cuadrada es:</li>
  $$x_{n+1}$$
  <li>El número del cual se quiere calcular la raíz cuadrada es:</li>
  $$m$$
</ul>
<br>
<p>Isaac Newton, uno de los científicos más influyentes de la historia, postuló esté método como una técnica para encontrar raíces de ecuaciones en su obra "Método de las Fluxiones" (escrita alrededor de 1669). Sin embargo, Newton nunca publicó formalmente sus trabajos de método numéricos y cálculo en su tiempo. Por otro lado, Joseph Raphson, un matemático y teólogo inglés, fue el primero en publicar formalmente el método de Newton en su libro "Análisis Aritmético" (1690), lo que le valió el reconocimiento por este método y llevó a que se le conociera con su nombre.</p>

<p><b>Algoritmo planteado:</b></p>

```mermaid
flowchart TD;
    A[Inicio] -->|Ingrese un número n| B(a = n/2)
    B --> C(b = 0)
    C --> D{b != a}
    D -->|Sí| E{a = b}
    E --> G(a + n /a)
    G --> H(a/2)
    H --> D
    D -->|No| F(a = raiz cuadrada del número)
    F --> I(Fin)
```
<h2>Bibliografía</h2>
    <div class="bibliografia">
        <table>
            <tr>
                <th>Referencia</th>
            </tr>
            <tr>
                <td>Hacker Noon. (s.f.). Cómo Calcular la Raíz Cuadrada de un Número Usando el Método de Newton-Raphson: Una Guía de Cómo Hacer. Recuperado de <a href="https://hackernoon.com/es/calcular-la-raiz-cuadrada-de-un-numero-usando-el-metodo-de-newton-raphson-una-guia-de-como-hacer-yr4e32zo">https://hackernoon.com/es/calcular-la-raiz-cuadrada-de-un-numero-usando-el-metodo-de-newton-raphson-una-guia-de-como-hacer-yr4e32zo</a></td>
            </tr>
            <tr>
                <td>Manual de LaTeX. (s.f.). Ecuaciones. Recuperado de <a href="https://manualdelatex.com/tutoriales/ecuaciones">https://manualdelatex.com/tutoriales/ecuaciones</a></td>
            </tr>
            <tr>
                <td>Mermaid Live Editor. (s.f.). Editor de Mermaid. Recuperado de <a href="https://mermaid.live/edit#pako:eNpNkEFOwzAQRa8yeBVEq1YsIxWJNk2bBWzKDrOY2Ka1aMaVsYUgyZG4ANteDMdxEV5Zb_7_M_otE0YqlrPXo_kQB7QOngpOEN79c0VaaPMC0-ldV9HeqncFnoDOP42yBqiDZYawAJrdXo-e5aCFVVYHOk9sFVnR1nC1AOxHWMTQ3fm7g3U7ZNRpsI7qTci9AYIZppBNxNsM_1Ztx9j_cY-mgzJeZFF_gfAoLUoEqY6Xo5O5jOYqKzUlwiYszBvUMpTRDowzd1CN4iwPX4n2jTNOfdChd2b3SYLlzno1Yf4k0alC495ic4FKamfsw1hu7Lj_BbtyalI">https://mermaid.live/edit#pako:eNpNkEFOwzAQRa8yeBVEq1YsIxWJNk2bBWzKDrOY2Ka1aMaVsYUgyZG4ANteDMdxEV5Zb_7_M_otE0YqlrPXo_kQB7QOngpOEN79c0VaaPMC0-ldV9HeqncFnoDOP42yBqiDZYawAJrdXo-e5aCFVVYHOk9sFVnR1nC1AOxHWMTQ3fm7g3U7ZNRpsI7qTci9AYIZppBNxNsM_1Ztx9j_cY-mgzJeZFF_gfAoLUoEqY6Xo5O5jOYqKzUlwiYszBvUMpTRDowzd1CN4iwPX4n2jTNOfdChd2b3SYLlzno1Yf4k0alC495ic4FKamfsw1hu7Lj_BbtyalI</a></td>
            </tr>
        </table>
    </div>
