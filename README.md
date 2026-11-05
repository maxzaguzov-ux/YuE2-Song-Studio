# 🎵 YuE2 Song Studio for Kaggle / Студия музыки YuE2 для Kaggle

**AI text-to-music generation with YuE2-3B (INT8) on free Kaggle GPUs.**
**Генерация музыки из текста с помощью YuE2-3B (INT8) на бесплатных GPU Kaggle.**

---

## 🚀 Launch in One Click / Запуск в один клик

### 1️⃣ Native Version (Jupyter widgets, no web server)
### Нативная версия (виджеты Jupyter, без веб-сервера)

[![Open in Kaggle](https://kaggle.com/static/images/open-in-kaggle.svg)](https://www.kaggle.com/kernels/welcome?src=https://github.com/maxzaguzov-ux/YuE2-Song-Studio/blob/main/yue2-3b-native.ipynb)

*Forms live inside the notebook cell. Most stable option.*
*Формы находятся прямо в ячейке ноутбука. Самый стабильный вариант.*

### 2️⃣ Gradio Web UI Version (public link studio)
### Версия с веб-интерфейсом Gradio (студия по публичной ссылке)

[![Open in Kaggle](https://kaggle.com/static/images/open-in-kaggle.svg)](https://www.kaggle.com/kernels/welcome?src=https://github.com/maxzaguzov-ux/YuE2-Song-Studio/blob/main/yue2-3b-gradio-web-ui.ipynb)

*After running the last cell, open the `*.gradio.live` link from the output.*
*После запуска последней ячейки открой ссылку `*.gradio.live` из вывода.*

---

## ✨ Features / Возможности

- 🎤 **Full songs with vocals** from lyrics + style prompt ([Verse]/[Chorus]/[Outro] structure)
- 🎤 **Полноценные песни с вокалом** из текста и описания стиля (структура [Verse]/[Chorus]/[Outro])
- 🔄 **Cover / Restyle mode** with source audio upload
- 🔄 **Режим кавера / рестайла** с загрузкой исходного аудио
- 🎼 **5 genre presets** + fully custom style descriptions
- 🎼 **5 пресетов жанров** + полностью произвольное описание стиля
- ⚙️ **Advanced controls**: sampler, scheduler, steps, ABC planning, format & quality
- ⚙️ **Расширенные настройки**: сэмплер, планировщик, шаги, ABC-планирование, формат и качество
- 📊 **Live progress bar** during diffusion sampling
- 📊 **Прогресс-бар в реальном времени** во время сэмплирования
- 📥 **Smart download block**: auto ZIP download + fallbacks
- 📥 **Умный блок скачивания**: авто-скачивание ZIP + запасные способы

---

## 🧠 Model / Модель

| | |
|---|---|
| **Model / Модель** | YuE2-3B INT8 (`yue2_3b_int8_convrot.safetensors`) |
| **Source / Источник** | [Comfy-Org/YuE2](https://huggingface.co/Comfy-Org/YuE2) (official repack / официальная перепаковка) |
| **Encoder / Энкодер** | SheetSage2 (`sheetsage2_bf16.safetensors`) |
| **Size / Размер** | ~4.5 GB + ~1.8 GB |
| **GPU target / Целевой GPU** | Tesla T4 / P100 (Kaggle free tier) |
| **Quality / Качество** | Frontier level, competitive with Suno v5/v6 / фронт-уровень, конкурирует с Suno v5/v6 |

*INT8 quantization is used because free Kaggle GPUs (T4) do not support BF16 natively.*
*Квантование INT8 используется, потому что бесплатные GPU Kaggle (T4) не поддерживают BF16 нативно.*

---

## 🛠 Requirements / Требования

- **Accelerator / Ускоритель**: GPU T4 x2 (or P100) — Settings → Accelerator
- **Internet / Интернет**: ON — Settings → Internet (needed for model download / нужно для скачивания модели)
- **Disk / Диск**: ~10 GB free in `/kaggle/working`
- **First run / Первый запуск**: 5–10 min for model download / 5–10 мин на скачивание модели

---

## 📖 How to Use / Как пользоваться

1. Click an "Open in Kaggle" button above. / Нажми кнопку "Open in Kaggle" выше.
2. Enable **GPU T4 x2** and **Internet** in Settings (right sidebar). / Включи **GPU T4 x2** и **Internet** в настройках (правая панель).
3. Run cells top to bottom (1 → 2 → 3 → 4 → 5). / Запускай ячейки сверху вниз (1 → 2 → 3 → 4 → 5).
4. In the studio: pick mode (New Song / Cover), fill style & lyrics, press Generate. / В студии: выбери режим (New Song / Cover), заполни стиль и текст, нажми Generate.
5. Run the last cell to pack & download all tracks as ZIP. / Запусти последнюю ячейку, чтобы упаковать и скачать все треки в ZIP.

### Gradio version note / Примечание для версии Gradio
After the last cell prints `Running on public URL: https://xxxx.gradio.live`, open that link in a new tab. The link lives 72 hours per session.
Когда последняя ячейка выведет `Running on public URL: https://xxxx.gradio.live`, открой эту ссылку в новой вкладке. Ссылка живёт 72 часа на сессию.

---

## 🆚 Which version to choose? / Какую версию выбрать?

| | Native / Нативная | Gradio Web UI |
|---|---|---|
| Interface / Интерфейс | Widgets in cell / виджеты в ячейке | Web app / веб-приложение |
| Stability / Стабильность | Max / максимальная | High / высокая |
| UX for long sessions / UX для долгих сессий | OK | Best / лучший |
| Extra deps / Доп. зависимости | None / нет | Gradio |

---

## 🐛 Troubleshooting / Решение проблем

- **"GPU Not Detected"** → Settings → Accelerator → GPU T4 x2.
- **Model download stuck / модель не качается** → check Internet = ON, re-run cell 3. / проверь Internet = ON, перезапусти ячейку 3.
- **Gradio link missing / нет ссылки Gradio** → wait 10–20 s after cell output, scroll the cell output up. / подожди 10–20 с после вывода ячейки, прокрути вывод вверх.
- **Download 404 in editor / 404 при скачивании в редакторе** → use right sidebar → **Output** tab → ⬇️ arrow on `YuE2_All_Tracks.zip`. / используй правую панель → вкладка **Output** → стрелка ⬇️ на `YuE2_All_Tracks.zip`.

---

## 🙏 Credits / Благодарности

- Original notebook concept / исходная концепция ноутбука: [AI With Chucky](https://github.com/AICHUCKY/Ai-with-Chucky-Colab-Notebooks)
- Model / модель: [m-a-p/YuE2-3B](https://huggingface.co/m-a-p/YuE2-3B)
- ComfyUI repack / перепаковка ComfyUI: [Comfy-Org/YuE2](https://huggingface.co/Comfy-Org/YuE2)
- Framework / фреймворк: [ComfyUI](https://github.com/comfyanonymous/ComfyUI)
- Web UI: [Gradio](https://gradio.app/)

---

## 📄 License / Лицензия

Notebook code: **MIT**. Underlying model weights: **CC BY-NC 4.0** (non-commercial).
Код ноутбука: **MIT**. Веса модели: **CC BY-NC 4.0** (некоммерческое использование).

**Happy music making! / Приятного творчества! 🎵**
