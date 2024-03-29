# FFMPEG UI

Project goals: Desktop UI for ffmpeg tool

## Current Version - 0.1

1. Based on:

    - Vue 3
    - Quasar https://quasar.dev/vue-components/
    - Electron
    - Material Icons https://fonts.google.com/icons?selected=Material+Icons&icon.query=info

2. Dev Build:

    - `npm install` / `yarn install`
    - `quasar dev -m electron`

3. Screen

![Screen 1](docs/screen-1.jpg)

## Previous versions and attempts

Looking at https://brainhub.eu/library/electron-alternatives-javascript-frameworks-for-desktop-apps/

1. [x] Electron + Vue.js (FAIL)

    1. Проблема с отображением стандартной системной модалки выбора файла
    2. Проблема с запуском: после старта иногда отображается белое окно

2. [X] NW.js + Nuxt (FAIL)

    1. https://github.com/elegantweb/nwjs-vue ошибка npm install: `PostCSS plugin postcss-discard-comments requires PostCSS 8.`
    2. Nuxt + clean NW.js + https://github.com/zcbenz/nw-sample-apps + https://github.com/nwutils/nw-local-server-example/
    3. Проблема с остановкой локального сервера
    4. Не удалось запаковать приложение в exe

3. [x] NW.js + Vuetify (FAIL)

    1. проблема с поддержкой fluent-ffmpeg внутри браузера

4. [X] NW.js + port spinner + Vuetify (FAIL)
    
    1. https://www.npmjs.com/package/spawn-for-ip
    2. child_process not initialized in browser

5. [x] Electron clean setup + Vuetify + electron-packager

    1. Almost done, but problems with installer

6. [ ] Vue 3 + Pinia + Quasar + Electron
    1. https://mokkapps.de/blog/building-a-vue-3-desktop-app-with-pinia-electron-and-quasar/



## FYI: best way to add FFmpeg to project

1. `npm i fluent-ffmpeg` - gives all neccessary methods
2. `npm i @ffmpeg-installer/ffmpeg` - add binary of ffmpeg to project
3. `const ffmpegPath = require('@ffmpeg-installer/ffmpeg').path;` - get path of binary
4. `Ffmpeg.setFfmpegPath(ffmpegPath);` - set binary path value for fluent-ffmpeg
5. `npm i @ffprobe-installer/ffprobe` - add ffprobe binary to project
6. `npm install nw --nwjs_build_type=sdk` - open console dev tools in app