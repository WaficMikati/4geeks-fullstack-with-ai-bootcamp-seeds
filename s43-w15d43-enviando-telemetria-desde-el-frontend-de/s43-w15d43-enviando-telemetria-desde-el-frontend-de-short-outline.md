# Short Outline: Sending Telemetry from the Frontend

**Skill:** 43 — Collecting telemetry and context-related info from the user and your application
**Block:** Enviando telemetría desde el frontend de mi aplicación
**File:** s43-w15d43-enviando-telemetria-desde-el-frontend-de
**Total Lessons:** 10

**💻 Declaration:** YES — Students implement a telemetry sender: a JavaScript function that batches events and transmits them via `fetch` (POST /telemetry/events with debounce) and `navigator.sendBeacon` (for page unload flush). The function produces observable output — HTTP requests sent to an endpoint — and can be verified in the browser's network tab.

---

## Lesson List

- 00.0 Welcome 📖
- 01.0 The Event Contract 📖
- 01.1 Designing the Event Schema 📖
- 02.0 Sending Telemetry to the Backend 📖
- 02.1 The Batch Sender 📖
- 02.2 Reliability Patterns 📖
- 02.3 Build the Telemetry Sender 💻
- 03.0 The Implementation Mental Model 📖
- 03.1 Telemetry in Transit 🧠
- 04.0 Outro
