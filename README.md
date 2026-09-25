# PB Downloader

Download the project and enter the repository root directory.

Create `artist-list.txt` in project source directory and add one URL per line.

Then set up on NixOS with:

```fish
nix shell nixpkgs#python3 # temporarily install python on system
python3 -m venv .venv # create venv
source .venv/bin/activate.fish # enter venv 
python -m pip install -r requirements.txt # install required packages
```

After that, download with:
```fish
set -x LD_LIBRARY_PATH $NIX_LD_LIBRARY_PATH # set FHS symlinks
nix shell nixpkgs#chromium # use nixpkgs chromium
source .venv/bin/activate.fish # enter venv 
python ./src/download.py # run script from anywhere
```

All downloaded videos are saved in the downloads directory under each artist's name (`./src/downloads/model-name/video.mp4`).

## License

This project is licensed under the MIT License.
