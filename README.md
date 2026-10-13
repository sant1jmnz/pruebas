# Macros del día

Calculadora interactiva de calorías, macronutrientes y comidas diarias. Es una sola página (`index.html`) sin dependencias ni proceso de compilación: ábrela en el navegador y funciona.

## Qué hace

1. **Tus datos.** Con sexo, edad, peso, altura y nivel de actividad calcula el metabolismo basal (ecuación de Mifflin-St Jeor) y el gasto energético total. El objetivo (perder grasa, mantener o ganar músculo) fija las calorías del día, que también puedes escribir a mano.
2. **Reparto de macros.** Elige un punto de partida (equilibrada, alta en proteína, baja en hidratos o rendimiento) o ajusta la proteína en g/kg y la grasa en % de las calorías. Los hidratos cubren el resto.
3. **Comidas y registro.** Reparte las calorías entre 3 y 6 comidas y apunta lo que comes buscando entre más de 80 alimentos (valores por 100 g con su ración habitual). Cada comida muestra lo que llevas frente a su objetivo.
4. **Mis alimentos.** Añade productos propios copiando la tabla nutricional del envase.
5. **Información nutricional.** Un resumen con forma de etiqueta muestra energía, proteínas, hidratos, grasas y fibra frente al objetivo, y el reparto calórico real frente al planificado. Puedes copiarlo como texto.

Los datos se guardan en el `localStorage` del navegador; no se envían a ningún sitio.

## Cálculos

| Concepto | Fórmula |
|---|---|
| Metabolismo basal (TMB) | `10 × peso (kg) + 6,25 × altura (cm) − 5 × edad + 5` (hombre) o `− 161` (mujer) |
| Gasto total (GET) | `TMB × factor de actividad` (1,2 · 1,375 · 1,55 · 1,725 · 1,9) |
| Calorías objetivo | `GET × (1 + ajuste)`, con ajustes de −20 %, −10 %, 0 %, +10 % o +15 %, redondeado a 10 kcal |
| Proteínas | `g/kg × peso`, a 4 kcal/g |
| Grasas | `% × calorías objetivo`, a 9 kcal/g |
| Hidratos | calorías restantes, a 4 kcal/g |
| Fibra | 14 g por cada 1.000 kcal |

Son estimaciones orientativas y no sustituyen el consejo de un dietista-nutricionista.
