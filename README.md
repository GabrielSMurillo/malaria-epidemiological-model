# Modelo Matemático para la Epidemiología de la Malaria en Zonas de Bajamar - Colombia

Este repositorio presenta el desarrollo e implementación de un modelo matemático tipo Ross-Macdonald con enfoque metapoblacional para estudiar la transmisión de malaria en zonas rurales y urbanas del Pacífico colombiano, particularmente afectadas por la minería ilegal.

---

## 🌍 Contexto

La malaria es una enfermedad infecciosa de alta carga epidemiológica en Colombia, especialmente en zonas tropicales como el Chocó. El aumento de la minería ilegal ha generado condiciones propicias para la proliferación del vector (mosquito Anopheles), lo cual ha incidido en el incremento de casos. Este proyecto busca modelar cuantitativamente estas interacciones.

---

## 🧬 Objetivo del Proyecto

Modelar la influencia de las migraciones entre zonas urbanas y zonas de minería ilegal (rurales) en la propagación de la malaria, usando una estructura compartimentada con interacción mosquito-humano, mediante simulaciones en Python.

---

## 🔄 Enfoque Metodológico

Se implementa un modelo Ross-Macdonald extendido en dos parches:

* **Parche urbano** (zona con baja exposición)
* **Parche rural** (zona minera con alta exposición)

Incluye:

* Estados para humanos: Susceptibles (S), Expuestos (E), Infectados (I)
* Estados para mosquitos: Susceptibles (Sm), Infectados (Im)
* Interacción entre poblaciones y tasas migratorias τ (urbano ➔ rural) y η (rural ➔ urbano)

Las ecuaciones diferenciales están descritas completamente en el código y el documento PDF anexo.

---

## 📈 Resultados Clave

* A mayor tasa de migración urbana ➔ rural (τ), mayor infección en humanos y mosquitos.
* La infección se propaga más rápidamente cuando η (migración rural ➔ urbana) es menor.
* Se evidencian puntos críticos de estabilidad e inestabilidad de poblaciones infectadas.

<p align="center">
  <img src="./images/resultados_simulacion.png" width="600" alt="Gráfica de simulación">
</p>

---

## 🧰 Dataset y Parámetros

No se utilizó un dataset clásico, sino valores asumidos o extraídos de literatura para los parámetros del modelo:

| Símbolo | Descripción                                          | Valor   | Unidad | Fuente  |
| ------- | ---------------------------------------------------- | ------- | ------ | ------- |
| β       | Tasa de recuperación humana                          | 0.00017 | d⁻¹    | OMS     |
| σ       | Tasa de infección expuestos ➔ infectados             | 0.05    | d⁻¹    | \[4]    |
| c₁      | Tasa de picadura urbana                              | 0.46    | d⁻¹    | \[10]   |
| α₁      | Probabilidad de infección mosquito ➔ humano (urbano) | 0.022   | -      | \[11]   |
| b₂      | Probabilidad de infección humano ➔ mosquito (mina)   | 0.883   | -      | \[11]   |
| τ       | Migración ciudad ➔ mina                              | 0.15    | d⁻¹    | asumida |
| η       | Migración mina ➔ ciudad                              | 0.95    | d⁻¹    | asumida |
| ...     | ...                                                  | ...     | ...    | ...     |

Ver todos los parámetros y referencias en el documento `Malaria_Bajamar.pdf`

---

## 📁 Estructura del Repositorio

```
├── Modelo_malaria.ipynb     # Notebook con simulación y visualización
├── Malaria_Bajamar.pdf      # Documento con modelo matemático y análisis
├── images/
│   └── resultados_simulacion.png
└── README.md                # Este archivo
```

---

## 🎓 Autores

* Gabriel Murillo Barragán - [gs.murillo@uniandes.edu.co](mailto:gs.murillo@uniandes.edu.co)
* Hector J. Malpica Salcedo - [hj.malpica@uniandes.edu.co](mailto:hj.malpica@uniandes.edu.co)
* José F. Gómez Bonilla - [jf.gomezb1@uniandes.edu.co](mailto:jf.gomezb1@uniandes.edu.co)

---

## 💡 Trabajo Futuro

* Incorporar estacionalidad climática con funciones trigonométricas
* Considerar poblaciones heterogéneas (niños, adultos mayores)
* Incluir mortalidad y natalidad humana
* Evaluar estrategias de vacunación o tratamiento antimalárico

---

## ⚖️ Licencia

Este proyecto es de uso académico bajo licencia MIT.

---

## 🌐 Referencias

Ver sección final del PDF `Malaria_Bajamar.pdf` para citas completas.

> "La modelación matemática puede ser la clave para anticipar y controlar epidemias en zonas olvidadas."
