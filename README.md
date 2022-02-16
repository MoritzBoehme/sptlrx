<div align="center">

<h1><a href="https://github.com/raitonoberu/sptlrx">sptlrx</a></h1>
<h4>Spotify lyrics in your terminal.</h4>

![Crystal Castles - Not In Love](./demo.svg "Crystal Castles - Not In Love")

</div>

## Features

- Timesynced lyrics in your terminal.
- Fully compatible with [spotifyd](https://github.com/Spotifyd/spotifyd).
- Works well with long lines & Unicode characters.
- Easy to use customization.
- Single binary & cross-plaftorm.

## Installation

**Linux**

- Arch Linux ([@BachoSeven](https://github.com/BachoSeven))
```
yay -S sptlrx-bin
```
- Other
```
curl -sSL instl.sh/raitonoberu/sptlrx/linux | sudo bash  
````

**Windows**
````
iwr instl.sh/raitonoberu/sptlrx/windows | iex  
````

**macOS**
````
curl -sSL instl.sh/raitonoberu/sptlrx/macos | sudo bash   
````

You can also download the binary from the [Releases](https://github.com/raitonoberu/sptlrx/releases/latest) page or [build it yourself](./building.md).

## Configuration

Since Spotify requires a special web token to display song lyrics, you need to specify your cookie when you first launch.

1. Open your browser.
2. Press F12, open the `Network` tab and go to [open.spotify.com](https://open.spotify.com/).
3. Click on the first request to `open.spotify.com`.
4. Scroll down to the `Request Headers`, right click the `cookie` field and select `Copy value`.
5. Paste it when you are asked.

You can also set the `SPOTIFY_COOKIE` enviroment variable or pass the `--cookie` flag, and your cookie will be saved on the next run. You can always clear cookie by running `sptlrx clear`.

## Information

### Styling

There are three special flags for applying custom colors and styles to lines: `--current`, `--before` and `--after`. The syntax for all flags is the same - pass styles and colors separated by commas. Example:
```sh
sptlrx --current "bold,#FFDFD3,#957DAD" --before "104,faint,italic" --after "104,faint"
```
List of allowed styles: `bold`, `italic`, `underline`, `strikethrough`, `blink`, `faint`. The colors can be either in HEX format, or ANSI 0-255. The first color represents the foreground, the second represents the background. **Note that styles will not work if your terminal does not support them.**

### Delay

For some reason unknown to me, there is a delay in the lyrics on some devices. You can manually adjust the delay by using the "**+**" and "**-**" symbols on the keyboard (adds or subtracts 100 ms).

## License

**MIT License**, see [LICENSE](./LICENSE) for additional information.
