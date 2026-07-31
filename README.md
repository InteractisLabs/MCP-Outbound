<!-- ══════════════════════════════════════════════════════════════
     IMAGEN (banner/logo): logotipo o wordmark de "Interactis" centrado.
     Súbelo a la RAÍZ del repo con nombre EXACTO: interactis-logo.png
     (sin carpeta, sin dos puntos, sin barra)
     ════════════════════════════════════════════════════════════════ -->
<p align="center">
  <img src="interactis-logo.png" alt="Interactis" width="420">
</p>

<h1 align="center">Interactis</h1>

<p align="center">
  <strong>Dale un teléfono a tu agente de IA.</strong><br>
  Llamadas de voz y SMS reales • Telefonía LATAM • Nativo de MCP • Sin pegamento.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/licencia-MIT-blue" alt="Licencia MIT">
  <img src="https://img.shields.io/badge/MCP--nativo-6E56CF" alt="Nativo de MCP">
  <img src="https://img.shields.io/badge/-Telefon%C3%ADa%20LATAM-green" alt="Telefonía LATAM">
  <img src="https://img.shields.io/badge/estado-beta%20temprana-orange" alt="Beta temprana">
</p>

---

> **Estado: beta temprana.** La conexión con Claude y las **llamadas de voz reales ya funcionan hoy** — pruébalo en [🚀 Pruébalo ahora](#-pruébalo-ahora-funciona-hoy). El resto de esta página es el rumbo del producto; lo que aún no está listo va marcado con 🔜.

**Interactis** le da a tu agente de IA la capacidad de hacer **llamadas de voz reales** y enviar **SMS** a teléfonos de verdad — directamente desde Claude, Cursor, ChatGPT o Gemini.

Sin conectar Twilio + TTS + webhooks tú mismo. Solo le dices qué quieres en lenguaje natural y tu agente lo ejecuta.

---

## Interactis, en 1 minuto

<!-- ══════════════════════════════════════════════════════════════
     VIDEO NORTH-STAR — arrastra tu demo.mp4 AQUÍ, en esta línea,
     dentro del editor del README en GitHub. GitHub lo sube solo y
     genera el enlace; se inserta como reproductor con controles.
     (No uses una ruta tipo assets/... ni con dos puntos — deja que
     el arrastre genere el enlace automáticamente.)
     ════════════════════════════════════════════════════════════════ -->


https://github.com/user-attachments/assets/1376e5b5-8707-4e11-9bbc-2f0205b22428



> Esto es hacia dónde va Interactis: le hablas a tu agente y una llamada real suena en un teléfono físico. Es un video de visión, no un producto terminado — lo que ya funciona hoy está justo abajo, en [🚀 Pruébalo ahora](#-pruébalo-ahora-funciona-hoy).

---

## 🚀 Prueba el demo ahora (Modo Sandbox)

Interactis se conecta a **Claude** como conector personalizado (MCP). En ~2 minutos puedes hacer que Claude te llame por teléfono de verdad.

1. En Claude, abre **Configuración → Conectores → Agregar conector personalizado**.
2. Pega esta URL:

   ```
   https://api.interact.is/mcp
   ```

3. Guarda y reconecta. Las herramientas de Interactis aparecen automáticamente.
4. **Verifica tu número.** Interactis te manda un código por SMS; dáselo a Claude para confirmar tu teléfono.
5. Pídele a Claude que te llame:

   ```
   "Llámame y dime el clima de hoy en Monterrey."
   ```

Puedes disparar **hasta 10 llamadas reales** con el prompt que tú quieras.

```text
Tú: "Llámame y recuérdame que tengo junta a las 4."

Claude: ✅ Llamada realizada. Estado: contestada. Duración: 12s.
```

<!-- Confirmar que el ejemplo de salida coincide con lo que devuelve el server. -->

---

## La visión

Todo lo que sigue es hacia dónde va Interactis. Lo que ya está vivo lleva ✅; lo que viene, 🔜.

### Por qué Interactis cambia las reglas

| Aspecto                    | Sin Interactis                          | Con Interactis                              |
|---------------------------|-----------------------------------------|---------------------------------------------|
| **Tiempo de puesta en marcha** | Días (Twilio + TTS + webhooks + lógica) | Minutos (conectas el MCP y listo)          |
| **Hacer una llamada**      | Escribir y depurar integración completa | Una instrucción en lenguaje natural        |
| **Cobertura y entrega**    | Configurar carriers y rutas por tu cuenta | Telefonía LATAM lista desde el primer día |
| **Control y seguridad**    | Riesgo de que el modelo improvise       | Tú defines el mensaje. El agente no improvisa |
| **Integración con IA**     | Código personalizado por cada agente    | Nativo de MCP (funciona en Claude, Cursor, etc.) |

### Características

- **📞 Llamadas de voz reales** ✅ — Tu agente marca y entrega el mensaje por voz.
- **🔐 Registro con OTP** ✅ — Verificación de teléfono desde el primer momento.
- **💬 SMS reales** 🔜 — Mensajes de texto con confirmación de entrega.
- **🇲🇽 Telefonía LATAM** — México disponible hoy; más países 🔜.
- **🧩 Nativo de MCP** ✅ — Funciona dentro de Claude; más clientes 🔜.
- **🛡️ Control total** ✅ — Tú defines exactamente qué se dice. El modelo no improvisa durante la llamada.
- **📊 Resultados estructurados** ✅ — Recibes estado limpio (contestada, entregado, etc.), no transcripciones crudas.

---

## Herramientas disponibles

<!-- Confirmar con Jacobo que estos nombres coinciden exactamente con el manifest del MCP server,
     y qué está realmente vivo hoy. Ajustar la columna Estado según eso. -->

| Herramienta            | Estado | Qué hace                                                       |
|------------------------|:------:|----------------------------------------------------------------|
| `register_with_otp`    |   ✅   | Crea cuenta y verifica el teléfono del usuario mediante código OTP |
| `make_voice_call`      |   ✅   | Realiza una llamada de voz real y entrega el mensaje           |
| `send_sms`             |   🔜   | Envía un SMS real con confirmación de entrega                  |

---

## Clientes compatibles

Interactis usa MCP estándar, así que en principio funciona con cualquier cliente que lo soporte. Estado real de pruebas:

- **Claude** (Desktop / Code) ✅ — probado
- **Cursor** 🔜
- **ChatGPT** (con soporte MCP) 🔜
- **Gemini** 🔜
- **VS Code** + extensiones compatibles 🔜
- **Codex CLI** y otros agentes 🔜

---

## Cómo usarlo

Una vez conectado y verificado, solo pídele a Claude lo que necesitas en lenguaje natural.

**Que te llame a ti**
```
"Llámame y dime el clima de hoy en Monterrey."
```

**Llamada a otro número** 🔜
```
"Llama al +52 81 1234 5678 y avísale que su cita de mañana quedó confirmada a las 16:00."
```

**SMS** 🔜
```
"Manda un SMS al +52 81 1234 5678 con el código de confirmación 4821."
```

Claude elige la herramienta correcta, Interactis ejecuta la acción y te devuelve el resultado de forma **estructurada**.

---

## Seguridad y control

Interactis está diseñado para **casos de uso reales de negocio**, donde la previsibilidad importa:

- **Tú defines el mensaje** — El modelo no improvisa durante la llamada.
- **Cuentas verificadas por OTP** — Evita uso anónimo y reduce abuso.
- **Resultados estructurados** — Recibes estado limpio y procesable.
- **Sin acceso sin control** — El agente solo puede usar las herramientas que tú has conectado.

---

## Roadmap

Lo que viene después:

- **Llamadas a cualquier número** — Que Claude marque a terceros, no solo a tu número verificado.
- **SMS reales** — Envío de texto con confirmación de entrega.
- **Guiones conversacionales acotados** — Describe el flujo completo y Interactis lo convierte en un guion con ramas limitadas (ideal para cobranza, recordatorios, encuestas).
- **Llamadas entrantes (inbound)** — Números propios que tu agente puede contestar.
- **Más canales** — WhatsApp, RCS y mayor cobertura en LATAM.
- **Plantillas de negocio** — Cobranza, recordatorios de citas, invitaciones, encuestas, etc.

---

## Solución de problemas

**El agente no ve las herramientas**
→ Revisa que la URL del conector sea `https://api.interact.is/mcp` y reconecta.

**No llega el código de verificación**
→ Verifica que tu número esté en formato E.164 (`+52...`) y sea alcanzable.

**La llamada no llega**
→ Confirma que completaste la verificación por OTP y que no superaste el límite de llamadas de la demo.

---

## Contribuir

¿Te interesa la idea? Abre un issue con tu caso de uso o feedback — en esta etapa, saber qué construir es lo más valioso. Los Pull Requests también son bienvenidos.

---

## Licencia

MIT © Interactis

---

<p align="center">
  <sub>Hecho para agentes que necesitan hablar por teléfono. 📞</sub>
</p>
