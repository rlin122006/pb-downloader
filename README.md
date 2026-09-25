# PB Downloader

Gathers video pages and stream links of select websites and downloads them in 1080p quality in MPEG-4 format. Supports both Windows 11 and NixOS.

## Getting Started

Download the project and enter the repository root directory.

### Windows 11

```powershell
python -m venv .venv # create venv
.\.venv\Scripts\Activate.ps1 # enter venv 
python -m pip install -r requirements.txt # install required packages
python -m patchright install chromium # install browser
```

### NixOS

```shell
nix shell nixpkgs#python # temporarily install python on system
python -m venv .venv # create venv
source .venv/bin/activate.fish # enter venv 
python -m pip install -r requirements.txt # install required packages
```

## Downloads

Enter and create `artist-list.txt` in project source directory and add one URL per line.

### Windows

```powershell
.\.venv\Scripts\Activate.ps1 # enter venv
python .\src\download.py # run script
```

### NixOS

```shell
set -x LD_LIBRARY_PATH $NIX_LD_LIBRARY_PATH # set FHS symlinks
nix shell nixpkgs#chromium # use nixpkgs chromium
source .venv/bin/activate.fish # enter venv 
python ./src/download.py # run script from anywhere
```

All downloaded videos are saved in the downloads directory under each artist's name (`./src/downloads/artist-name/video.mp4`).

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
