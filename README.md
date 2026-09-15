# C2 — Manejo de Base de Datos

Tarea C2 (Capítulo 2: lógica combinacional, SOP/POS, márgenes de ruido, timing y hazards).

José Daniel Cuá Fagiani — Carné 21200

## Contenido

1. [Ejercicio 2.24 — Ecuación a partir de un circuito](docs/2.24-ecuacion.md)
2. Ejercicio 2.28 — SOP, POS, Digikey, margen de ruido y timing
   - [2.1 — Construcción del circuito por SOP y por POS](docs/2.28-sop-pos.md)
   - [2.2, 2.3, 2.4 — Compuertas reales, margen de ruido, critical/shortest path](docs/2.28-digikey-nm-timing.md)
3. [Forbidden zone](docs/forbidden-zone.md)
4. [Timing + sumador de 1 bit y 2 bits](docs/timing-sumador.md)
5. [Glitch](docs/glitch.md)

## Resultados principales

| Punto | Resultado |
|---|---|
| 2.24 | Y = A'D + AB'C + AC'D + ABCD |
| 2.28 SOP y POS | Y = A(B + C + D') — misma expresión por ambos caminos |
| 2.28 margen de ruido (1.8 V) | NM_H = 30 mV, NM_L = 180 mV |
| 2.28 timing | shortest path 2.4 ns, critical path 25.9 ns |
| Forbidden zone | a Vin = VDD/2 la salida es inválida (1 V de 5 V) y la corriente sube de 50 nA a 10 mA |
| Sumador 1 bit | contamination 3.5 ns, propagation 25.9 ns |
| Sumador 2 bit (jerárquico) | contamination 3.5 ns, propagation 41.9 ns |
| Glitch | hueco de 100 unidades en Y cuando B cambia con A=0, C=1; se corrige balanceando el retardo del camino directo de B |

## Estructura del repositorio

```
docs/         explicación de cada punto, en Markdown
img/          figuras, mapas de Karnaugh, capturas de datasheet y de Logisim
circuitos/    archivos .circ de Logisim Evolution, verificados por línea de comandos
```

## Herramientas usadas

- **Logisim Evolution** (v4.1.0) para los circuitos digitales, verificados con su modo de consola (`--tty table`), que corre la tabla de verdad completa del `.circ` sin intervención manual.
- **Falstad Circuit Simulator** (falstad.com/circuit) para la zona prohibida (necesita un simulador analógico real, no uno puramente digital) y como referencia para el ejercicio del glitch.
- **Texas Instruments / Digikey**: datasheets reales de la familia SN74LVC1G para todos los cálculos de márgenes de ruido y tiempos de propagación a 1.8 V.
- Python (matplotlib, PyMuPDF) para las figuras propias (mapas de Karnaugh, diagramas de voltaje, diagramas de tiempo) y para extraer datos de los datasheets en PDF.

## Video

Pendiente — enlace privado de YouTube explicando la resolución de los ejercicios.
