
```markdown
# YouTube Video Downloader

Этот проект представляет собой простой YouTube Video Downloader, реализованный с использованием Python, библиотеки `yt-dlp` для загрузки видео и `gradio` для создания веб-интерфейса. Проект запускается в Google Colab, что позволяет легко использовать его без необходимости установки дополнительного ПО на локальную машину.

## Функциональность

- Загрузка видео с YouTube по ссылке.
- Автоматическое объединение видео и аудио потоков в один файл формата MP4.
- Очистка загруженных файлов при каждом новом запуске приложения.
- Веб-интерфейс для удобного взаимодействия с пользователем.

## Как использовать

1. Перейдите по [ссылке на Google Colab](https://colab.research.google.com/github/Leon-Av/yt-dlp_gradio-colab/blob/main/yt_dlp_gradio.ipynb).
2. Запустите все ячейки в блокноте.
3. После запуска последней ячейки появится публичная ссылка на веб-интерфейс.
4. Вставьте URL видео с YouTube в текстовое поле и нажмите кнопку "Скачать/Download".
5. После завершения загрузки файл будет доступен для скачивания через интерфейс.

## Установка зависимостей

Для работы проекта необходимо установить следующие пакеты:

- `yt-dlp` — для загрузки видео с YouTube.
- `gradio` — для создания веб-интерфейса.
- `ffmpeg` — для обработки и объединения видео и аудио потоков.

Все зависимости устанавливаются автоматически при запуске кода в Google Colab.

## Пример кода

```python
# Установка необходимых пакетов
!pip install yt-dlp gradio
!sudo apt update
!sudo apt install -y ffmpeg

import gradio as gr
import os
from yt_dlp import YoutubeDL

# Создаем папку для загрузок
download_folder = "/content/downloads"
os.makedirs(download_folder, exist_ok=True)

def download_video(url):
    ydl_opts = {
        'format': 'bestvideo[ext=mp4]+bestaudio[ext=m4a]/best[ext=mp4]/best',
        'outtmpl': f'{download_folder}/%(title)s.%(ext)s',
        'merge_output_format': 'mp4',
    }
    
    try:
        with YoutubeDL(ydl_opts) as ydl:
            info = ydl.extract_info(url, download=True)
            filename = ydl.prepare_filename(info)
            return filename
    except Exception as e:
        return str(e)

# Функция для очистки старых файлов
def cleanup():
    for file in os.listdir(download_folder):
        file_path = os.path.join(download_folder, file)
        try:
            if os.path.isfile(file_path):
                os.unlink(file_path)
        except Exception as e:
            print(f'Ошибка при удалении {file_path}: {e}')

# Создаем интерфейс Gradio
with gr.Blocks() as demo:
    gr.Markdown("## YouTube Video Downloader")
    with gr.Row():
        url_input = gr.Textbox(label="URL")
    with gr.Row():
        download_button = gr.Button("Скачать/Download")
    with gr.Row():
        file_output = gr.File(label="Downloaded File")

    download_button.click(
        fn=download_video,
        inputs=url_input,
        outputs=file_output
    )

    demo.load(fn=cleanup, inputs=None, outputs=None)

# Запускаем приложение с публичной ссылкой
demo.launch(share=True)
```
