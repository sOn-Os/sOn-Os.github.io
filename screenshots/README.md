# Screenshots

The gallery on the page shows one screenshot per desktop. Put them here with these names:

| File | Desktop |
| :--- | :--- |
| `kde.webp` | KDE Plasma |
| `gnome.webp` | GNOME |
| `cosmic.webp` | COSMIC |
| `hyprland.webp` | Hyprland |

Take them at 1920×1080 (16:9; other sizes are cropped to fit) and save them as WebP, for example:

```bash
cwebp -q 82 screenshot.png -o kde.webp
```

Until a file exists, the page shows a "screenshot coming soon" placeholder in its place.
