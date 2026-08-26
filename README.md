[English](https://github.com/Anan-up/Windows-Blue-Screen-Update-Webpage/blob/main/README.md) | [简体中文](https://github.com/Anan-up/Windows-Blue-Screen-Update-Webpage/blob/main/README_Simplified_Chinese.md) | [繁体中文](https://github.com/Anan-up/Windows-Blue-Screen-Update-Webpage/blob/main/README_Classical_Chinese.md)


## File Overview

**`win-screens.html`** (~17KB, single file, zero external dependencies) is a **Windows Blue Screen / System Update screen simulator**. Built with pure HTML + CSS + vanilla JavaScript, it opens and runs instantly, delivering a full-screen immersive showcase of 6 highly faithful system screens.

## Feature Architecture: 3×2 Screen Matrix

| System Version | Blue Screen | Update Screen |
|---|---|---|
| **Windows 7** | Classic text-mode blue screen showing error `DRIVER_IRQL_NOT_LESS_OR_EQUAL`, STOP code `0x000000D1`, and `nvlddmkm.sys` driver crash info, complete with the full memory dump flow text | Black "Configuring Windows updates" screen with a blue gradient progress bar and a "Please do not turn off your computer" warning |
| **Windows 10** | Modern `:(` style blue screen with a hand-drawn SVG QR code, stop code `CRITICAL_PROCESS_DIED`, and a Bing search link | Dark theme with a circular progress ring (SVG stroke-dashoffset animation) |
| **Windows 11** | Cleaner `:(` blue screen (`#0067c0`, a deeper blue with more whitespace), QR code + support.microsoft.com link | Circular progress ring with a "Working on updates X%" counter |

## Interaction Design

- **HUD floating panel** (top-right, frosted glass effect): displays the current location in real time (e.g., "Windows 10 · Blue Screen") and contains a 3×2 grid of buttons (`1B/1U/2B/2U…`) for one-click navigation
- **Keyboard shortcuts**: `↑↓` switches the system version, `←→` switches the screen type, and `H` toggles the HUD
- **Animation simulation**: three independent progress animations (the Win7 progress bar, the blue screen's "collecting info" percentage, and the circular update progress ring), driven by `Math.random()` to mimic irregular progress changes for a "realistic" feel

## Technical Highlights

1. **Highly faithful details**: the Win7 blue screen uses monospace fonts + `white-space: pre-wrap` to reproduce the original text layout; the Win10/11 blue screen colors, emoticons, and bottom-right white QR codes (drawn with SVG paths) all mirror the real systems
2. **Responsive design**: full-screen font sizes scale with `clamp()`, and the layout uses vw/vh units so everything renders completely at any resolution
3. **Dependency-free, zero build**: a single file opens directly in any browser — ideal for demos, pranks, and front-end practice

## project screenshot

![project-screenshot](project_screenshot.png)

## License

[MIT](LICENSE)
