# Cadence v2 — Speak English with Confidence

Tu entrenador personal de speaking. Un solo `index.html`, sin build step, deploy directo en Vercel.

## Qué cambió respecto a v1

- **Día 1 desde cero** — streak 0, XP 0, vocab 0, pronunciation pendiente. El usuario empieza limpio.
- **Onboarding con nivel inicial** configurable (beginner / intermediate / upper / advanced).
- **Diseño editorial dark premium** — Instrument Serif italic + Geist + acento lime `#B4FF39`, grain overlay, hairlines, tipografía magazine.
- **10 módulos completos** (antes 8): Today, Speak, Shadow, Conversations, Video, Lab, Idioms, Reading, Grammar, Progress.
- **AI híbrida** — local por defecto (respuestas pre-generadas por escenario), o pegas tu Anthropic API key en Settings y se conecta a `claude-sonnet-4-20250514`.

## Funcionalidades reales (no mockup)

- **Web Speech API** para transcripción en vivo (Chrome/Edge/Safari)
- **SpeechSynthesis** para audio nativo en cada frase, idiom, línea
- **Canvas waveform** real desde `getUserMedia` durante el speaking
- **Análisis en vivo**: WPM, fluency, clarity, detección de fillers (uh, um, like, you know…) y calques de español (people is, since a long time, I have hungry…)
- **Shadowing scoring** por overlap de palabras objetivo vs. dichas
- **YouTube embed** con control de velocidad (0.75x / 1x / 1.25x) vía postMessage al iframe API
- **Heatmap de 52 semanas** estilo GitHub
- **Achievements** que se desbloquean por XP, streak y conteo de reps
- **LocalStorage persistence** completo (estado, conversaciones, settings)

## Métodologías pedagógicas implementadas

Shadowing · Active Recall · Comprehensible Input · Chunking · Pronunciation Drilling · Sentence Mining · Listening Before Speaking · Pattern Recognition.

## Atajos de teclado

- `1-9, 0` → cambiar de módulo
- `Space` → toggle mic en Speak
- `Esc` → cerrar modales / parar grabación

## Estructura del archivo

Un solo `index.html` (~116 KB) con CSS y JS inline. No requiere build, npm, ni dependencias. Solo Google Fonts.

## Deploy

```
vercel --prod
```

El `vercel.json` ya tiene el header `Permissions-Policy: microphone=(self)` para que la Web Speech API funcione.

## Limitaciones honestas

- Firefox tiene TTS pero no STT live (la app avisa).
- El "scoring" de pronunciación es heurístico (overlap de palabras + fillers + calques), no análisis fonético real. Para análisis fonético real necesitarías un modelo como wav2vec o un endpoint dedicado.
- AI híbrida: si no hay API key, las respuestas de Conversations son árboles guionados por escenario (8 escenarios x ~6 turnos cada uno). Con API key, son generativas reales.
