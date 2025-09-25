# distributed-system-prediction
time series prediction algorithm

# ⚡ Sistemas Distribuidos – Prediciendo el Futuro  

El objetivo del proyecto es **implementar un algoritmo de predicción de series temporales** utilizando un método de **k vecinos más cercanos (k-NN)**, y estudiar la **escalabilidad** de la solución variando el número de procesos, hilos y tamaño de los datos.

---

## 📌 Descripción del proyecto

Una serie temporal es una sucesión de datos ordenados cronológicamente. El objetivo de este trabajo es, dado un histórico de datos diarios (ejemplo: 24 mediciones por día), **predecir el día siguiente** a partir de los días pasados más parecidos al actual.  

El algoritmo se basa en:
1. **Búsqueda de k vecinos más cercanos** al último día conocido.  
2. **Predicción**: tomar los valores del día siguiente de esos k vecinos y calcular la **media aritmética**.  
3. **Evaluación**: calcular el error usando **MAPE (Mean Absolute Percentage Error)**.  

Además, se analizan los tiempos de ejecución en función de:
- **Tamaño del dataset** (1x, 10x, 100x).  
- **Número de procesos MPI** (1–4).  
- **Número de hilos OpenMP** (1–4).  

---

## 🛠️ Tecnologías utilizadas
- **Lenguaje**: C  
- **Librerías**:
  - [MPI](https://www.mpi-forum.org/) → paralelismo distribuido (procesos).  
  - [OpenMP](https://www.openmp.org/) → paralelismo compartido (hilos).  
- **Entorno de compilación**:
  - `mpicc` para compilar código C con soporte MPI.  
  - `mpirun` para ejecutar con múltiples procesos.  

---

## 📂 Estructura del repositorio
```bash
sistemas-distribuidos/
│
├── exec.c              # Código fuente principal con MPI + OpenMP
├── enunciado.pdf       # Documento original de la práctica
├── README.md           # Este archivo
├── Predicciones.txt    # Ejemplo de salida con predicciones
├── MAPE.txt            # Ejemplo de salida con errores MAPE
└── Tiempo.txt          # Ejemplo de salida con tiempos de ejecución
