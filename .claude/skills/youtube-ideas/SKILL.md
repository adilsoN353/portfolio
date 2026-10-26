---
name: youtube-ideas
description: Generador de ideas de canales de YouTube (animados o hiperrealistas con IA) para monetizar con AdSense. Úsala cuando el usuario quiera buscar nichos, tendencias, outliers o adaptar canales de habla inglesa al mercado español/francés.
---

# Generador de ideas de canales YouTube

Objetivo: encontrar nichos emergentes (outliers) que todavía no estén clonados en el idioma objetivo, y cerrar un concepto de canal accionable.

## Contexto del equipo (actualizar si cambia)
- 2 personas: una hace vídeo (Flow/Kling), otra guion + investigación + imágenes + voces (Claude, ElevenLabs).
- ~10 h/semana. Objetivo: AdSense rápido. Vídeos largos (+10 min) y shorts derivados.
- Mercado actual: español. Futuro: francés e inglés.
- Problema: sus canales anteriores se clonan en masa → buscar nichos con barrera (investigación) o innovación de formato.
- Ideas ya guardadas en `ideas/` — leerlas antes para no repetir.

## Flujo
1. **Preguntas rápidas** (solo lo que falte): formato (animado/hiperrealista), idioma, objetivo, duración, temas que gustan/no.
2. **Datos de outliers** (en paralelo):
   - `nexlev latest_discovered_faceless_niches` (outlierScore >= 2). Salida enorme: procesar con jq/python, campos `title, subscribers, outlierScore, rpm, avgViewPerVideo, daysSinceStart, categories, lastUploadedVideos[].video_title/video_view_count`.
   - `vidiq_outliers` con keyword en inglés (language en) y en el idioma objetivo (es).
   - `nexlev search_niche_finder_channels` con `channelLanguage` del idioma objetivo para medir competencia.
3. **Proponer 4-5 nichos** con: canal referencia, subs, vistas, outlier, RPM, hueco en español, riesgo. Dar recomendación.
4. **Profundizar** en el elegido: tabla de vídeos top en inglés, fórmula repetible, competencia en español, ángulo diferencial local.
5. **Concepto final**: nombre provisional, promesa, formato, ventaja local, shorts, y preguntas de cierre (época/tono/voz/frecuencia).
6. **Guardar** en `ideas/AAAA-MM-DD-<slug>.md` y hacer commit.

## Criterios de un buen nicho
- Canales referencia < 6 meses y < 20K subs con vídeos de 100K+ (outlier alto).
- RPM >= $3 (ideal >$5); evitar nichos de RPM ~$1 salvo volumen enorme.
- Fórmula de título repetible.
- Poca competencia fuerte en el idioma objetivo.
- Barrera anti-clon: investigación, ángulo local, calidad visual.
- Riesgo copyright bajo (cuidado con IPs: anime, marcas).

## Formato de respuesta
Español, conciso, móvil: tablas cortas, viñetas, recomendación clara, 3-4 preguntas al final.
