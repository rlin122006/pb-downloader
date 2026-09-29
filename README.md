# PB Downloader

Gathers video pages and stream links of select websites and downloads them. 

## Description

PB Downloader is a tool written in Python with patchright and niquests that is able to mass download videos from a list of provided links. Windows 11 and NixOS are supported operating systems.

## Disclaimer

The functionality of PB Downloader may be illegal, unethical, and in violation of the terms of service of third parties. This software is intended for use only where legal. You confirm you are of legal age in your jurisdiction. You accept full responsibility for any consequences, legal or otherwise, that result from your use of this application.

I do not endorse, condone, or encourage any illegal, unethical, or terms-of-service-violating activity. This includes, but is not limited to, cheating, academic dishonesty, piracy, copyright infringement, unauthorized intrusions, cyberstalking, and child exploitation. 

Under no circumstances will I or the project's contributor(s) be liable for any damages, losses, or legal claims arising from your use of this software. Use at your own risk. By using this software, you acknowledge you have read and understood this disclaimer.

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
