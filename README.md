# ⚡ Simulador de Circuito RLC en serie

Simulador interactivo de la **ecuación diferencial lineal de segundo orden** que gobierna un circuito RLC en serie. Recurso educativo abierto desarrollado para el curso de **Ecuaciones Diferenciales** de la **Universidad Nacional Abierta y a Distancia (UNAD)**.

$$L\frac{d^2q}{dt^2} + R\frac{dq}{dt} + \frac{1}{C}q = E(t), \qquad i = \frac{dq}{dt}$$

---

## ✨ Características

- **Tres tipos de fuente** `E(t)`: respuesta libre (sin fuente), escalón DC y sinusoidal AC.
- **Clasificación automática del régimen** de amortiguamiento a partir de la ecuación característica `Ls² + Rs + 1/C = 0`:
  - Subamortiguado (`ζ < 1`) — oscila y decae.
  - Sobreamortiguado (`ζ > 1`) — decae sin oscilar.
  - Amortiguamiento crítico (`ζ = 1`).
  - Sin amortiguamiento (`R = 0`).
- **Cuatro vistas**:
  - **Dominio del tiempo** — carga `q(t)` y corriente `i(t)`.
  - **Plano de fase** — trayectoria `(q, i)` con espirales y nodos.
  - **Energía** — en el capacitor `q²/2C`, en el inductor `½Li²` y total.
  - **Resonancia** — curva de amplitud de corriente `|I(ω)|` con pico en `ω₀`.
- **Animación de reproducción**: un cabezal de tiempo recorre la solución mientras el esquema del circuito muestra el flujo de corriente y el punto se mueve por el plano de fase.
- **Parámetros característicos** en vivo: `ω₀`, `f₀`, `α`, `ζ`, `ω_d`, factor de calidad `Q` y ancho de banda.
- Siete escenarios predefinidos y todas las expresiones en **LaTeX**.
- Diseño responsive (computador, tableta y móvil) con el logo institucional UNAD incrustado.

## 🔬 Física implementada

El sistema de segundo orden se reduce a uno de primer orden y se integra con **Runge–Kutta de 4.º orden**:

```
q' = i
i' = (E(t) − R·i − q/C) / L
```

Validado contra la solución analítica de la respuesta libre subamortiguada (error ≈ 10⁻¹⁴).

## 🚀 Publicar en GitHub Pages

1. Sube `index.html` y `.nojekyll` a la raíz del repositorio.
2. Ve a **Settings → Pages**.
3. En **Source**, elige la rama `main` y la carpeta `/ (root)`. Guarda.
4. En pocos minutos el simulador estará en:
   `https://<tu-usuario>.github.io/<nombre-del-repo>/`

> El archivo `.nojekyll` (vacío) evita que GitHub procese el sitio con Jekyll. Si no aparece al subir, créalo en GitHub con **Add file → Create new file**, nombre `.nojekyll`, sin contenido, y **Commit**.

## 🧪 Uso local

No requiere instalación ni servidor: abre `index.html` en cualquier navegador moderno con conexión a internet (carga KaTeX desde CDN).

## 🛠️ Tecnología

[KaTeX](https://katex.org/) para LaTeX · Canvas 2D para los gráficos · RK4 para la integración numérica. Todo en un único archivo autónomo, sin dependencias locales.

## 📄 Licencia

Recurso educativo abierto. Libre uso, adaptación y redistribución con fines académicos.

---

<p align="center"><sub>Universidad Nacional Abierta y a Distancia — UNAD · Ecuaciones Diferenciales</sub></p>
