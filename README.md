```
                  ::::::::              ::::::::
                :+:    :+:            :+:    :+:
     +:++:++:+ +:+    +:+ +:++:++:+  +:+    +:+  +:++:++:+
   +#+        +#+    +:+ +#+    +#+ +#+    +:+ +#+
  +#++:++#++ +#+    +#+ +#+    +#+ +#+    +#+ +#++:++#++
        #+# #+#    #+# #+#    #+# #+#    #+#        #+#
#########   ########  ###    ###  ########  #########
```

The website of [sOnOs](https://github.com/aOnurTheDev/sOnOs), an Arch Linux-based operating system for developers and gamers.

The whole site is one file, `index.html`, with its CSS and JavaScript inline. There is no build step and nothing to install.

## Viewing it locally

Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8000
```

Then go to <http://localhost:8000>.

## What's on the page

| Section | Content |
| :--- | :--- |
| Hero | The sOnOs wordmark, the tagline and the download link |
| Console | The live ISO's ASCII logo and `/etc/os-release` |
| Nine questions | Every question soninstall asks, and the defaults it uses for the rest |
| Every installation | What each install includes, and its size with and without the development tools |
| Development tools | The languages installed when you answer yes to question 8 |
| Live ISO | The rescue and development packages on the ISO, by category |
| Installation | Download, write to USB, boot, answer the questions |
| Build & contribute | Building the ISO with `mkarchiso`, links to both repositories |

The content comes from the READMEs of [sOnOs](https://github.com/aOnurTheDev/sOnOs) and [sOnInstall](https://github.com/aOnurTheDev/sOnInstall). When either one changes (new desktops, new packages, new sizes), update the page to match.

## Languages

The page is written in Turkish and has an English translation, switched with the **TR / EN** buttons in the header.

- The Turkish text is the HTML itself.
- The English text is the `EN` object at the top of the `<script>` block.
- Every translated element has a `data-i18n="key"` attribute, and the same key in `EN`.

To change a sentence, edit it in the HTML for Turkish and under the same key in `EN` for English. To add one, give the element a new `data-i18n` key and add that key to `EN`.

The first visit uses English when the browser language is not Turkish. After that, the visitor's choice is remembered in `localStorage`.

## Design

| | |
| :--- | :--- |
| Colors | Black `#0B0909`, white `#FFFFFF` and the logo's red `#E53935` |
| Fonts | Anton for headings, Archivo for text, Martian Mono for commands and labels, from Google Fonts |
| Slant | Headings, buttons and dividers lean −12°, the same angle as the wordmark's letters |

All colors, fonts and the slant angle are CSS variables in the `:root` block at the top of the `<style>` tag.

The wordmark is inline SVG, drawn from `releng/sonos.svg` in the sOnOs repository. The red "On" flickers on once when the page loads.

## Motion

Three animations follow the scroll:

- The large wordmark drifts left as the page moves up.
- In the nine questions, each number fills in as it passes the middle of the screen, and the nine marks above them fill like a progress bar.
- The language wall fills in word by word, with a pacman-style counter below it, such as `(14/33) installing Haskell`.

All content is readable before any of it moves. Visitors who have reduced motion turned on in their system settings see a still page.

## Publishing on GitHub Pages

1. Put `index.html` at the root of a repository, or in a `docs/` folder.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, then the branch and the folder.

The site has no build step, so GitHub publishes the file as it is.

## Contributing

Bug reports and pull requests are welcome. Before you open a pull request, check the page at phone width (about 400 px) and in both languages.
