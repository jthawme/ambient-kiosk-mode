# Ambient Kiosk Mode

A 'kiosk mode' plugin for [Ambient](https://github.com/jthawme/ambient). Designed initially for a raspberry pi as the ambient machine, upon building and running the site, it will open chromium fullscreen in kiosk mode with the app

## Usage

```
// ambient.config.js

import * as KioskMode from "ambient-kiosk-mode";

/** @type {import('./server/types/options.js').Config} */
export default {
  ...,
  plugins: [KioskMode],
  pluginOptions: {
    kiosk: {
      ...
    }
  }
};
```

## Config

| Key         | Type     | Description                            | Default                                                                                      |
| ----------- | -------- | -------------------------------------- | -------------------------------------------------------------------------------------------- | --------------------------- | ------ |
| platform    | `'pi'    | 'mac'                                  | 'auto'`                                                                                      | Explicitly set the platform | `auto` |
| pi          | object   |                                        |                                                                                              |
| pi.command  | string   | The spawned command to run the browser | `/usr/bin/chromium-browser`                                                                  |
| pi.args     | string[] | The arguments to pass to the browser   | `["--start-maximized", "--kiosk", "--noerrdialogs", "--disable-infobars", "--no-first-run"]` |
| mac.command | string   | The spawned command to run the browser | `/Applications/Google Chrome.app/Contents/MacOS/Google Chrome`                               |
| mac.args    | string[] | The arguments to pass to the browser   | `[]`                                                                                         |
