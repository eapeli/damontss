# Damon TTS — Voice Cloning Notebook

> Notebook Colab pronto para usar **OmniVoice** (k2-fsa/OmniVoice) — voice cloning zero-shot + voice design em 600+ idiomas, incluindo português.

---

## O que faz

| Modo | Descrição |
|------|-----------|
| 🎤 **Voice Clone** | Upload de áudio de referência (5–30s) → clona a voz para falar qualquer texto |
| 🎨 **Voice Design** | Cria voz do zero via atributos: gender, age, pitch, accent, dialect, whisper |
| 🌍 **600+ idiomas** | PT-BR, EN, ES, FR, DE, JA, KO, ZH, RU, AR, HI, e muitos outros |

---

## Como usar (grátis, Colab Free)

### 1. Abra no Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/eapeli/damontss/blob/main/text_to_speak_Rota_Clonador.ipynb)

> Ou: `File → Open notebook → GitHub` → cole `eapeli/damontss`

### 2. Configure GPU
`Runtime → Change runtime type → T4 GPU` → **Save**

### 3. Rode a primeira célula (setup)
- Baixa modelo (~2GB) na primeira vez
- **Dica**: Monte seu Google Drive para cache persistente (evita baixar de novo):
  ```python
  from google.colab import drive
  drive.mount('/content/drive')
  import os
  os.environ['HF_HOME'] = '/content/drive/MyDrive/hf_cache'
  ```

### 4. Use a interface Gradio
- Link público `gradio.live` aparece ao final
- Aba **Voice Clone**: cole texto + áudio de referência → **GERAR AUDIO**
- Aba **Voice Design**: escolha atributos + texto → **Generate**

### 5. Feche a aba quando terminar
Colab desliga sozinho (90 min idle / 12h hard limit). **Custo: $0**

---

## Requisitos locais (se tiver GPU)

```bash
pip install omnivoice pydub gradio==6.11.0 torch transformers>=5.3
python -c "from omnivoice import OmniVoice; OmniVoice.from_pretrained('k2-fsa/OmniVoice')"
# CLI nativo:
omnivoice-demo --ip 0.0.0.0 --port 8001
```

---

## Modelo

- **OmniVoice** — `k2-fsa/OmniVoice` (Hugging Face)
- Paper / Repo: [k2-fsa/OmniVoice](https://github.com/k2-fsa/OmniVoice)
- Licença: verificar no repositório original

---

## Estrutura

```
damontss/
├── text_to_speak_Rota_Clonador.ipynb   # Notebook principal (Colab-ready)
└── README.md                           # Este arquivo
```

---

## Créditos

- **OmniVoice** by [k2-fsa](https://github.com/k2-fsa)
- Notebook adaptado de **ROTA PROMPT AI** / Canal W. Freitas
- Integração Damon / Hermes Agent by [Anne (Bettynha)](https://github.com/eapeli)

---

## ⚖️ Uso responsável

Voice cloning é poderoso. Use apenas com **consentimento** da pessoa cuja voz está clonando. Não use para deepfakes, fraude, ou qualquer fim malicioso.