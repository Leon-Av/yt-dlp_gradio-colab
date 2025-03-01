
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

EN:
# YouTube Video Downloader

This project is a simple YouTube Video Downloader implemented using Python, the `yt-dlp` library to download videos and `gradio` to create a web interface. The project runs in Google Colab, which makes it easy to use without the need to install additional software on your local machine.

## Functionality

- Uploading videos from YouTube via a link.
- Automatically merge video and audio streams into a single MP4 file.
- Clean up downloaded files each time the application is restarted.
- Web interface for easy user interaction.

## How to use

1. Go to [Google Colab link](https://colab.research.google.com/github/Leon-Av/yt-dlp_gradio-colab/blob/main/yt_dlp_gradio.ipynb).
2. Start all the cells in notepad.
3. After running the last cell, a public link to the web interface will appear.
4. Paste the URL of the YouTube video into the text box and click the “Download/Download” button.
5. Once the download is complete, the file will be available for download through the interface.

## Installing dependencies

The following packages need to be installed for the project to work:

- `yt-dlp` - for downloading videos from YouTube.
- `gradio` - for creating a web interface.
- `ffmpeg` - for processing and combining video and audio streams.

All dependencies are installed automatically when you run the code in Google Colab.

```
