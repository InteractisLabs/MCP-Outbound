<!-- ══════════════════════════════════════════════════════════════
     IMAGEN (banner/logo): logotipo o wordmark de "Interactis" centrado.
     Colócalo en assets/interactis-logo.svg — ancho ~420px.
     ════════════════════════════════════════════════════════════════ -->
<p align="center">
  <img src="assets/interactis-logo.png" alt="Interactis" width="420">
</p>

<h1 align="center">Interactis</h1>

<p align="center">
  <strong>Dale un teléfono a tu agente de IA.</strong><br>
  Llamadas de voz y SMS reales • Telefonía LATAM • Nativo de MCP • Sin pegamento.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/licencia-MIT-blue" alt="Licencia MIT">
  <img src="https://img.shields.io/badge/MCP--nativo-6E56CF" alt="Nativo de MCP">
  <img src="https://img.shields.io/badge/Telefonia_LATAM-green" alt="Telefonía LATAM">
</p>

---

**Interactis** le da a tu agente de IA la capacidad de hacer **llamadas de voz reales** y enviar **SMS** a teléfonos de verdad — directamente desde Claude Code, Cursor, ChatGPT o Gemini.

Sin dashboards complicados. Sin conectar Twilio + TTS + webhooks tú mismo. Solo le dices qué quieres en lenguaje natural y tu agente lo ejecuta.

---

## ¿Qué es Interactis?

Interactis es un **servidor MCP** (Model Context Protocol) que convierte a tu agente de IA en un comunicador real.

Tu agente puede:
- Hacer llamadas de voz a cualquier número
- Enviar SMS con confirmación de entrega
- Registrar usuarios con verificación por OTP

Todo desde tu chat de IA favorito con control total sobre lo que se dice.


```text
Tú: "Llama al +52 81 1234 5678 y dile que su pedido ya está listo para recoger."

Agente: ✅ Llamada realizada. Estado: contestada. Duración: 28s.
```

<!-- Confirmar que el ejemplo de salida coincide con lo que devuelve el server:
     ¿realmente regresa estado + duración? Ajustar a la respuesta real. -->

---

## Por qué Interactis cambia las reglas

| Aspecto                    | Sin Interactis                          | Con Interactis                              |
|---------------------------|-----------------------------------------|---------------------------------------------|
| **Tiempo de puesta en marcha** | Días (Twilio + TTS + webhooks + lógica) | Minutos (conectas el MCP y listo)          |
| **Hacer una llamada**      | Escribir y depurar integración completa | Una instrucción en lenguaje natural        |
| **Cobertura y entrega**    | Configurar carriers y rutas por tu cuenta | Telefonía LATAM lista desde el primer día |
| **Control y seguridad**    | Riesgo de que el modelo improvise       | Tú defines el mensaje. El agente no improvisa |
| **Integración con IA**     | Código personalizado por cada agente    | Nativo de MCP (funciona en Claude, Cursor, etc.) |

---

## Características principales

- **📞 Llamadas de voz reales** — Tu agente marca y entrega el mensaje por voz.
- **💬 SMS reales** — Mensajes de texto con confirmación de entrega.
- **🔐 Registro con OTP** — Verificación de teléfono desde el primer momento.
- **🇲🇽 Telefonía LATAM** — Entrega real a números de México y LATAM, con cobertura de carrier.
- **🧩 Nativo de MCP** — Funciona dentro de Claude Code, Cursor, ChatGPT, Gemini y más.
- **🛡️ Control total** — Tú defines exactamente qué se dice. El modelo no improvisa durante la llamada.
- **📊 Resultados estructurados** — Recibes estado limpio (contestada, entregado, etc.), no transcripciones crudas.

---

## Demo

<p align="center">
  <img src="assets/demo.gif" alt="Demo: Agente haciendo una llamada real con Interactis" width="560">
</p>

> Un agente recibe una instrucción y realiza una llamada real que suena en un teléfono físico.

<!-- ══════════════════════════════════════════════════════════════
     ALTERNATIVA (recomendada en GitHub): video en vez de GIF.
     El MP4 pesa ~2 MB (vs ~7 MB del GIF), el texto se ve nítido y
     trae controles de reproducción. GitHub lo renderiza como player
     si subes el archivo al repo. Para usarlo, comenta el <img> de
     arriba y descomenta esto:

  https://github.com/USUARIO/REPO/raw/main/assets/demo.mp4

     (Sustituye USUARIO/REPO. En GitHub basta con arrastrar el .mp4
     al editor del README para que genere la URL automáticamente.)
     ════════════════════════════════════════════════════════════════ -->

---

## Instalación (MCP)

<!-- ══════════════════════════════════════════════════════════════
     BLOQUE DE INSTALACIÓN — PENDIENTE
     Se completa cuando la API esté desplegada en su URL pública.
     Definir con Jacobo: ¿remoto/hosted (type: http + url) o local (npx)?
     No poner una URL inventada — un bloque roto mata la adopción.
     ════════════════════════════════════════════════════════════════ -->

> El bloque de configuración se publicará aquí en cuanto la API esté desplegada.

```jsonc
// Próximamente
{
  "mcpServers": {
    "interactis": {
      // ...
    }
  }
}
```

Después de pegar la configuración, reinicia tu cliente MCP. Las herramientas de Interactis aparecerán automáticamente para tu agente.

---

## Cómo usarlo

Una vez conectado, solo pídele a tu agente lo que necesitas en lenguaje natural.

### Ejemplos:

**Llamada de voz**
```
"Llama al +52 81 1234 5678 y avísale que su cita de mañana quedó confirmada a las 16:00."
```

**SMS**
```
"Manda un SMS al +52 81 1234 5678 con el código de confirmación 4821."
```

Tu agente elige la herramienta correcta, Interactis ejecuta la acción y te devuelve el resultado de forma **estructurada**.

---

## Herramientas disponibles

<!-- Confirmar con Jacobo que estos nombres coinciden exactamente con el manifest del MCP server. -->

El servidor expone un conjunto enfocado y confiable de herramientas:

| Herramienta            | Qué hace                                                          |
|------------------------|------------------------------------------------------------------|
| `register_with_otp`    | Crea cuenta y verifica el teléfono del usuario mediante código OTP |
| `make_voice_call`      | Realiza una llamada de voz real y entrega el mensaje             |
| `send_sms`             | Envía un SMS real con confirmación de entrega                    |

---

## Clientes compatibles

Funciona con cualquier cliente que soporte MCP:

- **Claude Code** & **Claude Desktop**
- **Cursor**
- **ChatGPT** (con soporte MCP)
- **Gemini**
- **VS Code** + extensiones compatibles
- **Codex CLI** y otros agentes

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

- **Guiones conversacionales acotados** — Describe el flujo completo y Interactis lo convierte en un guion con ramas limitadas (ideal para cobranza, recordatorios, encuestas).
- **Llamadas entrantes (inbound)** — Números propios que tu agente puede contestar.
- **Más canales** — WhatsApp, RCS y mayor cobertura en LATAM.
- **Plantillas de negocio** — Cobranza, recordatorios de citas, invitaciones, encuestas, etc.

---

## Solución de problemas

**El agente no ve las herramientas**
→ Revisa el bloque de configuración MCP y reinicia tu cliente.

**La llamada o SMS no llega**
→ Verifica que el número esté en formato E.164 (`+52...`) y sea alcanzable.

**Problemas al registrarte**
→ Asegúrate de haber completado la verificación por OTP.

---

## Contribuir

Las contribuciones son bienvenidas.
Abre un issue para reportar problemas o proponer mejoras, o envía un Pull Request.

---

## Licencia

MIT © Interactis

---

<p align="center">
  <sub>Hecho para agentes que necesitan hablar por teléfono. 📞</sub>
</p>
