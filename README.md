````markdown
# 🧰 YouTube Video Downloader (Dockerized)
````

A minimal YouTube video downloader wrapped in a Docker container.  
No need to install `yt-dlp` or any dependencies on your host machine — just Docker and you're ready.

---

## 📦 Features

- Runs in an isolated Ubuntu environment
- Uses `yt-dlp` to download videos
- Maps current directory for easy file access
- Zero dependencies on your local system

---

## 🚀 Getting Started

### 1. Build the Docker image

```bash
docker build . -t yt-d
````

### 2. Run the downloader

Use the command below to download any YouTube video:

```bash
docker run -v "$(pwd):/mydir" yt-d https://youtu.be/ZboZMIR3TtA?si=nSqYzi6MMYSL6aYZ
```

> ✅ Downloads will be saved to your current working directory.

---

## 🛠 How It Works

* The Dockerfile:

  * Starts from an Ubuntu base image
  * Installs `yt-dlp` and any required dependencies
  * Sets the working directory to `/mydir`
  * Defaults to using `yt-dlp` as the entrypoint

---

## 📁 Output

All downloaded videos will appear in the directory where you ran the command.

---

## 📝 Notes

* Make sure the video URL is properly quoted/escaped in shells like Zsh or Bash.
* You can pass any valid `yt-dlp` flags after the video URL.

Example:

```bash
docker run -v "$(pwd):/mydir" yt-d https://youtube.com/watch?v=XXXXXX
```
