# Linux Instructions:

## Ubuntu/Debian

I recommend installing MyST through pipx:
```
sudo apt install pipx
pipx ensurepath
# Restart your terminal after this
pipx install mystmd
```

Install LaTeX utilities:
```
sudo apt install texlive-full
```

Or if you need are short on storage space:
```
sudo apt install texlive-latex-extra texlive-fonts-recommended, latexmk, texlive-core, texlive-xetex texlive-plain-generic
```

Install Fonts:
```
sudo apt install ttf-mscorefonts-installer
```
## Arch

Install mystmd with pipx:
```
sudo pacman -S python-pipx
pipx ensurepath
# Restart your terminal after this
pipx install mystmd
```

Install LaTeX utilities:
```
sudo pacman -S texlive-meta
```

Or if you need are short on storage space:
```
sudo pacman -S texlive-basic texlive-latexextra texlive-fontsrecommended texlive-xetex texlive-plaingeneric latexmk
```

Install fonts:
```
yay -S ttf-ms-fonts
```
