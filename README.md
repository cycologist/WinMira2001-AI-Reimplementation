# AI-Mira — Unofficial AI-Assisted WINMIRA 2001 Reimplementation

**AI-Mira** is an independent, AI-assisted reimplementation of **WINMIRA 2001**, the latent-class / latent-class-analysis statistics program that was originally commercial software sold for approximately US$200. The original WINMIRA 2001 was designed and developed by the author of this reimplementation.

AI-Mira is built with Free Pascal / Lazarus and with substantial AI coding assistance. It is **not** the commercial release and is **not associated with the official distributors** of WINMIRA 2001.

The program has no registration, no serial-number generator and no demo mode. It always runs with the full-version limits (100000 persons, 256 items, 30 categories, 199 latent classes) and does not access the Windows registry. Defaults are stored in a plain `winmira.ini` file.

## Download

Go to the [latest release](https://github.com/cycologist/WinMira2001-AI-Reimplementation/releases/latest) and download the file for your platform:

| Platform | File |
| --- | --- |
| Linux x86-64 | `AI-Mira-linux-x86_64` |
| Windows x86-64 | `AI-Mira-windows-x86_64.exe` |
| macOS Intel | `AI-Mira-macos-x86_64.zip` or `AI-Mira-macos-x86_64` |
| macOS Apple Silicon | `AI-Mira-macos-arm64.zip` or `AI-Mira-macos-arm64` |
| Documentation | `AI-Mira-help.zip` |
| Example data | `AI-Mira-examples.zip` |

`SHA256SUMS` contains the SHA-256 checksums for every asset.

The macOS `.zip` files contain a ready-to-run **AI-Mira.app** bundle. The raw Mach-O executables are provided for advanced users.

## Data formats

The application can read and write several statistical data containers directly; no SPSS, R, Stata or SAS installation is required.

| Format | Import | Export |
| --- | --- | --- |
| SPSS `.sav` | yes | yes |
| R `.rds` (gzip or uncompressed) | yes | yes |
| R `.rda` / `.RData` (single data.frame) | yes | — |
| Stata `.dta` (formats 113–119) | yes | format 114 |
| SAS XPORT `.xpt` | version 5 and 8 | version 5 |

Use **File → Open Data File...** for import and **File → Save → Save data as ...** for export.

## HTML help / user manual

`AI-Mira-help.zip` contains the original HTML WINMIRA user manual plus the printable PDF version (`winmiramanual.pdf`). Extract it and open `help/index.html` in any web browser. The HTML pages are self-contained; no web server is needed.

On Windows and Linux, place the extracted `help` folder next to the AI-Mira executable. On macOS, place it next to **AI-Mira.app**.

The in-app **Help → Contents** menu entry in the current binaries still shows the port's placeholder message; use `help/index.html` directly.

## Example data

`AI-Mira-examples.zip` contains example data sets from the original WINMIRA package, prepared for the current importer:

| File | Cases | Items | Categories |
| --- | ---: | ---: | --- |
| `examples/ascii/Kft.dat` | 300 | 15 | 0–1 |
| `examples/ascii/Esu.dat` | 800 | 5 | 0–3 |
| `examples/ascii/Neoffi.dat` | 1000 | 10 | 0–3 |
| `examples/ascii/Simula9x_items.dat` | 2001 | 10 | 0–3 |
| `examples/ascii/Simula9z_items.dat` | 999 | 10 | 0–1 |

The archive also includes `with_class` variants of the Simula files, SPSS versions (`Kft.sav`, `Simula9x.sav`), original fixed-width files, and the original definition/fixation files. Open the ASCII files with **File → Open** using the freefield format and separator `Space`; open the `.sav` files with **File → Open Data File...**.

## macOS notes

The macOS bundles are ad-hoc signed but **not notarized**, so Gatekeeper warns on first launch. Right-click **AI-Mira.app** and choose **Open**, or remove the quarantine flag from a terminal:

```sh
xattr -dr com.apple.quarantine "AI-Mira.app"
```

The Apple Silicon build is native arm64; it does not need Rosetta. The Intel build is native x86-64.

## Verification

The source build includes a `make tabtest` round-trip test for R, Stata and SAS XPORT. It passes on Linux, Windows, Intel macOS and Apple Silicon macOS. All release checksums are verified after upload.

## Version

1.45 — free to use, unofficial AI-assisted reimplementation.
