# MiddleTube™

A self-hosted local video archive and media management platform built with HTML, CSS, JavaScript, and Node.js.

MiddleTube™ turns a directory of locally stored videos into a clean, searchable web-based media library.

## Features

* Local video library
* Automatic library scanning
* Video metadata detection
* Automatic thumbnails
* Video duration detection
* Channel/category organization
* Video search and filtering
* Recently added videos
* Storage and library statistics
* Dedicated video playback pages
* Light and dark themes
* Simple web-based settings
* Self-hosted and fully local
* No accounts or user system required

## Technology

MiddleTube™ is intentionally built using relatively simple technologies:

* HTML
* CSS
* JavaScript
* Node.js
* Express
* FFmpeg / FFprobe

There is no giant frontend framework required. No React. No Next.js. No 400-package JavaScript ecosystem™.

Just a web server, some HTML, some CSS, and enough JavaScript to make everything work.

## Requirements

* Node.js
* npm
* FFmpeg
* FFprobe

MiddleTube™ is primarily designed for Linux, but should work on other platforms supported by Node.js and FFmpeg.

## Installation

Clone the repository:

```bash
git clone https://github.com/randomtransitadventures/MiddleTube.git
cd MiddleTube
```

Install dependencies:

```bash
npm install
```

Start the server:

```bash
npm start
```

MiddleTube™ will start on port `3000` by default.

Open:

```text
http://localhost:3000
```

## Media Library

Place your videos inside the configured media directory.

The default directory is:

```text
media/
```

Then open the Settings page and select **Scan Library**.

MiddleTube™ will scan the directory and build its local library database.

## Supported Media

MiddleTube™ relies on FFmpeg/FFprobe for media inspection and playback.

Common formats such as:

* MP4
* MKV
* WebM
* MOV
* AVI

may be supported depending on the codecs available on the system and browser.

## Project Structure

```text
MiddleTube/
├── index.html
├── library.html
├── video.html
├── settings.html
├── style.css
├── app.js
├── server.js
├── media/
├── thumbnails/
├── data/
└── package.json
```

### Frontend

The HTML files provide the individual MiddleTube™ pages.

`style.css` contains the global visual design and themes.

`app.js` handles frontend interactions, library loading, filtering, video pages, scanning, and theme preferences.

### Backend

`server.js` runs the Express web server and handles:

* Video library scanning
* Video metadata
* Thumbnail generation
* Video uploads
* Library APIs
* Static media delivery

## Configuration

MiddleTube™ can be configured through the Settings page.

Available settings include:

* Media directory
* Server port
* Light/dark theme
* Library scanning

Server environment variables may also be used where supported.

## Design Philosophy

MiddleTube™ is designed around a simple idea:

> Your media library should not require a complicated media platform to use.

The project intentionally avoids unnecessary account systems, complicated permissions, cloud dependencies, and excessive frontend frameworks.

It is meant to be understandable, modifiable, and easy to self-host.

## Why?

Because sometimes you have a folder full of videos and decide:

> “You know what this needs? A fucking media platform.”

So MiddleTube™ exists.

## Status

MiddleTube™ is an actively developed personal project.

Expect bugs, questionable architectural decisions, and occasional instances of accidentally deleting one character and causing 200 JavaScript errors.

## License

See the `LICENSE` file for licensing information.

## Disclaimer

MiddleTube™ is provided as-is.

You are responsible for the media you store, serve, and access through your own installation.

nah fuh that if buying isnt owning piracy isnt stealing
---

# cant you tell i used cheatGPT on this?

**MiddleTube™ — Local video. No corporate cloud bullshit.**
