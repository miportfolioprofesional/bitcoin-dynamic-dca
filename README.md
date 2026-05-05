# Bitcoin Dynamic DCA: Una Estrategia de Acumulación Basada en Datos

**Un proyecto real para un desafío académico de acumulación de Bitcoin.**  
Este repositorio contiene el análisis completo, el desarrollo del modelo, el backtesting y los informes finales de un proyecto para un cliente.

---

## 🧠 ¿Qué problema resuelve esto?

Muchos inversores de largo plazo en Bitcoin usan **Dólar Cost Averaging (DCA)** para reducir el riesgo de timing.  
Pero el DCA trata todos los días por igual — compra USD 100 el lunes y USD 100 el viernes, sin importar si Bitcoin está a USD 20.000 o USD 60.000.

**La pregunta real:**  
¿Podemos mejorar el DCA invirtiendo más en períodos de subvaluación y menos en períodos de sobrevaluación?

**El desafío:**  
- Las métricas on-chain tradicionales (hash rate, direcciones activas, cantidad de transacciones) **no predicen retornos de corto plazo** (R² < 0.2%).
- Existen señales predictivas, pero son **sutiles y dependientes del régimen**.
- Muchas "reglas simples" (ej: comprar cuando el precio < MA200) **tienen un rezago significativo** y no logran superar al DCA.

**Qué entrega este proyecto:**  
Un **framework riguroso y reproducible** para probar cualquier hipótesis de acumulación contra un benchmark real — DCA uniforme — con backtesting completo, análisis de tasa de acierto (win rate) y honestidad estadística (incluyendo resultados negativos).

---

## 📊 Qué vas a encontrar acá

| Archivo / Carpeta | Qué es |
|------------------|--------|
| `model_integration.ipynb` | Notebook principal: carga de datos, feature engineering, asignación secuencial, backtesting |
| `outputs/` | Archivos CSV con resultados de backtest, señales, asignaciones y distribución de regímenes |
| `Final Report.docx` | Informe final completo (formato paper, alineado con el blog) |
| `Presupuesto...docx` | Presupuesto original del proyecto (transparencia sobre alcance y costos) |

---

## 🔍 Principales hallazgos del proyecto

### 1. Las métricas on-chain son coincidentes, no predictivas
Hash rate, direcciones activas, cantidad de transacciones y volumen muestran **correlaciones por debajo de 0.04** con retornos forward a 30 días.  
Describen el *presente*, no el futuro.

### 2. La volatilidad es persistente y dependiente del régimen
El ACF de los retornos al cuadrado decae lentamente en 20–30 rezagos (efectos ARCH).  
La volatilidad móvil de 30 días se agrupa en ciclos importantes (2013, 2017, 2020, 2022).  
**Las señales predictivas se comportan diferente según el régimen de volatilidad (bajo/medio/alto).**

### 3. Las señales de Polymarket tienen poder predictivo (aunque modesto)
Las probabilidades políticas y macro causan en sentido de Granger los retornos de Bitcoin (p < 0.01 y p < 0.05).  
Las señales cripto específicas son marginales (p ≈ 0.09).  
**Las correlaciones se fortalecen en regímenes de volatilidad media** (político 0.136 vs -0.013 en volatilidad baja).

### 4. El Jump Model (precio < MA200) falla por retraso
Una regla contraria simple ("mercado bajista = comprar más") asignó 13% más de capital durante caídas, pero el **retraso en la detección del régimen** hizo que el modelo compre cerca del piso, perdiéndose los mejores descuentos.  
**Resultado:** -0.27% de diferencia vs DCA, 12% de win rate.

### 5. Los resultados negativos también tienen valor científico
No toda hipótesis funciona. Este análisis **documenta honestamente lo que no funcionó**, evitando sobreajustar narrativas falsas.  
Para el período 2019–2026, el DCA uniforme fue sorprendentemente difícil de superar con este conjunto de señales.

---

## 🛠️ Stack técnico

- **Python** (pandas, numpy, polars, matplotlib, seaborn, statsmodels)
- **Jupyter Notebook** (integración del modelo, EDA)
- **GitHub** (control de versiones, listo para portfolio)

---

## 📈 Qué significa esto para vos (como cliente)

Si necesitás a alguien que:

- Convierta un **problema de negocio difuso** en un **framework cuantitativo testeable**
- Trabaje con **datos reales y desordenados** (parquets de Polymarket, CSVs de CoinMetrics, merges manuales)
- Construya **motores de backtesting** que respeten restricciones de no look-ahead, presupuesto y ventanas móviles
- Documente **tanto aciertos como fracasos** con honestidad intelectual
- Comunique resultados a **audiencias técnicas y no técnicas** (resúmenes ejecutivos, diapositivas, informes finales)

…**este es el tipo de trabajo que entrego.**

---

## 📁 Estructura del repositorio
