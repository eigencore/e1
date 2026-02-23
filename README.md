<h1 align="center">
  e1 by EigenCore
</h1>

<p align="center">
  <a href="https://github.com/eigencore/e1"><img src="https://img.shields.io/badge/1B_parámetros-FF6B35?style=flat-square" /></a>
  <a href="https://github.com/eigencore/e1"><img src="https://img.shields.io/badge/PyTorch_puro-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" /></a>
  <a href="https://github.com/eigencore/e1"><img src="https://img.shields.io/badge/LLaMA--3_style-6C63FF?style=flat-square" /></a>
  <a href="https://github.com/eigencore/e1"><img src="https://img.shields.io/badge/100B_tokens-8B5CF6?style=flat-square" /></a>
  <a href="https://github.com/eigencore/e1"><img src="https://img.shields.io/badge/Español_primero-F59E0B?style=flat-square" /></a>
  <a href="https://github.com/eigencore/e1"><img src="https://img.shields.io/badge/Apache_2.0-22C55E?style=flat-square" /></a>
</p>

---

<h3 align="center">El primer LLM moderno construido desde cero en LATAM</h3>

<p align="center">
  <a href="#">Documentación</a> ·
  <a href="#">Paper técnico</a> ·
  <a href="https://x.com/MaxGalindo5">Sigue el build en X</a> ·
  <a href="#">EigenCore</a>
</p>

---

La mayoría de la gente usa modelos de lenguaje. Nosotros construimos uno.

**e1** es el primer modelo de lenguaje a gran escala de EigenCore — 1 billón de parámetros, arquitectura moderna, entrenado completamente en español, escrito línea por línea en PyTorch puro. Sin HuggingFace Trainer. Sin Lightning. Sin DeepSpeed. Cada forward pass, cada gradiente, cada operación que ves aquí fue escrita a mano y está disponible para que la leas, la entiendas y aprendas de ella.

> Esto no es un fine-tune. Esto no es un wrapper. Esto es el modelo real.

---

## ¿Qué hay adentro?

| Módulo | Descripción |
|---|---|
| 🔄 **RoPE** | Rotary Position Embeddings implementado desde cero |
| ⚡ **FlashAttention-2** | Atención eficiente vía `scaled_dot_product_attention` |
| 🎯 **GQA** | Grouped Query Attention — 16 Q heads, 8 KV heads |
| 🧱 **SwiGLU** | Activación moderna del FFN |
| 📐 **RMSNorm** | Normalización sin bias, más rápida que LayerNorm |
| 🔀 **FSDP2** | Multi-GPU nativo de PyTorch, sin DeepSpeed |
| 💾 **MMap Dataset** | Pipeline para 100B+ tokens sin explotar la RAM |
| 🎓 **SFT + DPO** | Post-training completo implementado desde cero |

---

## Arquitectura

```
e1-1B
├── Parámetros:      1,000,000,000
├── Capas:           22
├── d_model:         2048
├── Attention heads: 16Q / 8KV (GQA)
├── FFN hidden:      8192 (SwiGLU)
├── Context length:  4096 tokens
├── Vocabulario:     32,000 (español)
└── Entrenado en:    100B tokens
```

---

## Por qué construimos nuestro propio framework

Porque la mejor forma de entender algo es construirlo tú mismo.

Cada abstracción que HuggingFace te oculta, aquí la exponemos. Cada truco enterrado dentro de DeepSpeed, aquí lo implementamos y explicamos. Si alguna vez usaste un modelo de lenguaje y te preguntaste qué está pasando realmente por debajo — este repositorio es para ti.

El training loop completo son **~2,000 líneas de PyTorch puro**. Nada más.

---

## Inicio rápido

```bash
git clone https://github.com/eigencore/e1
cd e1
```

## Estado del proyecto

| Fase | Estado |
|---|---|
| Arquitectura base | 🔄 En progreso |
| Training loop | ⏳ Próximamente |
| Data pipeline | ⏳ Próximamente |
| Primer training run | ⏳ Próximamente |
| Post-training (SFT) | ⏳ Próximamente |
| Post-training (DPO) | ⏳ Próximamente |

---

<p align="center">
  Construido en público desde LATAM 🌎 por <a href="https://github.com/eigencore">EigenCore</a>
</p>
