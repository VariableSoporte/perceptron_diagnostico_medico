# 🧠 Perceptrón para Clasificación de Riesgo en Pacientes

## 📌 Descripción del Proyecto

Este proyecto implementa un **Perceptrón desde cero en Python** para clasificar si un paciente está en **riesgo (1)** o **no está en riesgo (0)** basándose en los siguientes parámetros médicos:

- Edad  
- Presión arterial  
- Colesterol  
- Índice de Masa Corporal (IMC)  

El modelo es entrenado utilizando datos normalizados y posteriormente evaluado con un conjunto de prueba para calcular su precisión.

---

## 📊 Dataset

El dataset contiene **40 pacientes**, cada uno con:

| ID | Edad | Presión | Colesterol | IMC | Riesgo |
|----|------|----------|------------|------|--------|
| 1  | 72   | 160      | 280        | 32   | 1      |
| 2  | 24   | 110      | 170        | 22   | 0      |
| ... | ... | ... | ... | ... | ... |
| 40 | 73 | 162 | 285 | 33 | 1 |

- **Riesgo = 1** → Paciente en riesgo  
- **Riesgo = 0** → Paciente sin riesgo  

---

## 🔎 Normalización de Datos

Se utiliza la técnica **Min-Max Scaling**, que transforma los valores al rango **[0,1]**:

$$ X_{norm} = \frac{X - X_{min}}{X_{max} - X_{min}} $$


### 📌 ¿Por qué normalizar?

Si no normalizamos, valores grandes como el colesterol (ej: 210) tendrían más peso que valores menores como la edad (ej: 45).

La normalización:
- Evita sesgos por magnitudes grandes
- Mejora la estabilidad del entrenamiento
- Permite que todas las variables tengan la misma relevancia

---

## ✂ División del Dataset

- **Entrenamiento:** 30 pacientes  
- **Testeo:** 10 pacientes  

```python
x_entrenamiento = datos_normalizados[:30,:]
y_entrenamiento = etiquetas[:30]

x_testeo = datos_normalizados[30:,:]
y_testeo = etiquetas[30:]
```
## 🧪 Evaluación del Modelo

### Función para calcular la precisión

```python
def test_precision(data, result_real, pesos, bias):
```

### 📈 Resultados

```
Total aciertos: 9/10
Precisión: 90.0%
```

El modelo logró una **precisión del 90%** en el conjunto de prueba.

---

## 📌 Interpretación del Resultado

De 10 pacientes evaluados:

- ✅ 9 fueron clasificados correctamente  
- ❌ 1 fue clasificado incorrectamente  

Esto demuestra que el perceptrón logró aprender un patrón adecuado para separar pacientes en riesgo y no riesgo.

---

## 🛠 Requisitos

- Python 3.x  
- NumPy  

### Instalación

```bash
pip install numpy
```

---

## 📁 Estructura del Proyecto

```
📂 perceptron-riesgo-pacientes
 ├── perceptron.py
 └── README.md
```

---

## 🚀 Posibles Mejoras

- Implementar validación cruzada  
- Graficar la evolución del error  
- Agregar matriz de confusión  
- Probar con diferentes tasas de aprendizaje  
- Implementar versión con activación sigmoide (Regresión Logística)  

---

## 🎯 Conclusión

Este proyecto demuestra cómo implementar un **Perceptrón desde cero**, incluyendo:

✔ Normalización  
✔ División de datos  
✔ Entrenamiento  
✔ Evaluación  
✔ Cálculo de precisión  

Es una excelente base para comprender modelos de clasificación binaria y el funcionamiento interno de redes neuronales simples.
