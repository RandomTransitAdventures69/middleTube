# MiddleTube™

A self-hosted video library and streaming server built with Node.js and Express.

MiddleTube lets you organize your own video collection into a simple web interface. Videos are scanned from a folder, given metadata and thumbnails, and displayed in a searchable library.

## Features

* 📺 Video library web interface
* 🎬 Supports multiple video formats
* 🔎 Automatic library scanning
* 🖼️ Automatic video thumbnails
* ⏱️ Video duration displayed on cards
* 📊 Video metadata including resolution, codec, FPS, and file size
* 📁 Recursive folder scanning
* ⬆️ Upload support
* ✏️ Video metadata editing
* 🔐 Admin API protected by an admin key
* 🌐 Simple Node.js + Express architecture
* 💾 Filesystem-based storage — no complicated database required

## Supported Video Formats

MiddleTube currently recognizes:

* `.mp4`
* `.m4v`
* `.mov`
* `.webm`
* `.mkv`
* `.avi`
* `.m2ts`
* `.ts`

## Requirements

You'll need:

* Node.js
* npm
* FFmpeg
* FFprobe

A Linux server, Mac, or other system capable of running Node.js should work.

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/MiddleTube.git
cd MiddleTube
```

Install dependencies:

```bash
npm install
```

Copy the example configuration:

```bash
cp .env.example .env
```

Edit `.env` and set your configuration:

```env
MIDDLETUBE_MEDIA_DIR=./media
MIDDLETUBE_ADMIN_KEY=change-this-to-a-random-key
PORT=3000
```

## Running MiddleTube

Start the server:

```bash
npm start
```

Then open:

```text
http://localhost:3000
```

If MiddleTube is running on another computer, replace `localhost` with that computer's IP address.

For example:

```text
http://192.168.1.180:3000
```

## Media Storage

By default, MiddleTube looks for videos in:

```text
./media
```

You can change this with:

```env
MIDDLETUBE_MEDIA_DIR=/path/to/your/videos
```

MiddleTube recursively scans the directory, so you can organize videos into folders.

For example:

```text
media/
├── Channel One/
│   ├── video1.mp4
│   └── video2.mp4
├── Channel Two/
│   └── video3.mkv
└── Uncategorized/
    └── random-video.mp4
```

## Admin Key

Administrative API actions require the `MIDDLETUBE_ADMIN_KEY`.

Generate a strong random key with:

```bash
openssl rand -hex 32
```

Then put it in your `.env` file:

```env
MIDDLETUBE_ADMIN_KEY=your-generated-key
```

**Never publish your real admin key to GitHub.**

## API

### Get videos

```http
GET /api/videos
```

Returns the videos currently in the library.

### Scan library

```http
POST /api/scan
x-admin-key: YOUR_ADMIN_KEY
```

Scans the configured media directory for new or changed videos.

### Health check

```http
GET /api/health
```

Returns basic server health information.

### Update video metadata

```http
PATCH /api/videos/:id
x-admin-key: YOUR_ADMIN_KEY
```

Updates metadata for a video.

### Generate a thumbnail

```http
POST /api/videos/:id/thumbnail
x-admin-key: YOUR_ADMIN_KEY
```

Generates a new thumbnail for a video.

## Project Structure

```text
MiddleTube/
├── server.js
├── package.json
├── package-lock.json
├── .env.example
├── .gitignore
├── public/
│   ├── index.html
│   ├── app.js
│   └── style.css
├── media/
├── thumbnails/
└── data/
```

`media/`, `thumbnails/`, and generated database data should not be committed to the repository.

## Security

MiddleTube is designed primarily for use on a trusted network.

Do not expose the MiddleTube server directly to the public internet without considering authentication, HTTPS, and other security requirements.

Never commit `.env` or other files containing your admin key to a public repository.

## License

MiddleTube is licensed under the MIT License.

See `LICENSE` for the full license text.

---

Made with Node.js, Express, FFmpeg, and an unreasonable amount of media files.

**MiddleTube™**
