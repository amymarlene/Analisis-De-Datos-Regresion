# 🏥 Análisis de Costos de Seguro Médico

## Descripción del Proyecto

Este proyecto analiza un dataset de **1,338 personas** en Estados Unidos con información sobre costos de seguros médicos y variables demográficas y de salud:

- `edad`, `sexo`, `imc`, `hijos`, `fumador`, `region`, `cargos` (variable objetivo).

El objetivo es **preparar los datos para regresión**, identificar variables que más afectan los costos y generar datasets listos para modelado.

---

## Objetivos del Proyecto

1. Explorar y limpiar el dataset (valores faltantes, tipos de datos, outliers).  
2. Análisis univariante y bivariante para entender las variables.  
3. Transformar variables categóricas en dummies para regresión.  
4. Analizar la correlación y destacar las variables más importantes.  
5. Dividir el dataset en `train` (80%) y `test` (20%) para modelos predictivos.

---

## Resultados del Análisis

### 1️⃣ Distribución de Variables Numéricas

#### Edad, IMC, Hijos y Costos

#### Edad
![Histograma de Edad](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/histedad.png?raw=true)

#### IMC
![Histograma de IMC](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/histdebmi.png?raw=true)

#### Hijos
![Histograma de Hijos](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/histchildr.png?raw=true)

#### Costos
![Histograma de Costos](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/histdecharge.png?raw=true)

> Observación: Los costos muestran alta dispersión y algunos valores extremos (outliers), filtrados antes de la regresión.

---

### 2️⃣ Distribución de Variables Categóricas

#### Sexo, Fumador y Región

#### Sexo
![Conteo por Sexo](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/conteoporsex.png?raw=true)

#### Estado de Fumador
![Conteo de Fumadores](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/contfumad.png?raw=true)

#### Región
![Conteo por Región](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/contregi.png?raw=true)

> Observación: La mayoría de los datos son no fumadores; algunas regiones tienen más registros que otras.

---

### 3️⃣ Análisis Bivariante

- **Scatterplots**: edad, IMC e hijos vs `cargos`  

#### Relación entre Edad y Costo del Seguro
![Edad vs Costo del Seguro](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/edadvscost.png?raw=true)

#### Relación entre IMC y Costo del Seguro
![IMC vs Costo del Seguro](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/bmivscarg.png?raw=true)

- **Boxplots**: variables categóricas vs `cargos`  

#### Relación entre Fumador y Costo del Seguro
![Fumador vs Costo del Seguro](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/fumvscos.png?raw=true)

> Observación: Ser fumador aumenta drásticamente los costos; edad e IMC muestran correlación positiva; hijos y sexo tienen menor impacto.

---

### 4️⃣ Correlación de Variables

### Matriz de Correlación
![Matriz de Correlación](https://github.com/amymarlene/Analisis-De-Datos-Regresion/blob/main/correlacionmatriz.png?raw=true)

**Correlación con `cargos`:**

| Variable       | Correlación |
|----------------|------------|
| fumador_si     | 0.79       |
| edad           | 0.30       |
| imc            | 0.21       |
| hijos          | 0.07       |
| sexo_masculino | 0.06       |

> Observación: Fumador, edad e IMC son las variables más influyentes en los costos.

---


### 5️⃣ División Train / Test

- **Train**: 80% (~1008 filas)  
- **Test**: 20% (~252 filas)  
- La media de `cargos` se mantiene similar en ambos datasets.  
