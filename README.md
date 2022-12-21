# demucs-cxfreeze

## Freezing `demucs`

**With CUDA support (Windows & Linux)**
```
pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu116 demucs SoundFile cx-Freeze
```
**CPU only (Any OS)**
```
pip3 install torch torchvision torchaudio demucs SoundFile cx-Freeze
```
And then:
```
cxfreeze main.py --target-dir=dist --target-name=demucs-cxfreeze --packages=torch --includes=demucs.htdemucs
```

Copy `venv/Lib/site-packages/_soundfile_data` to `dist/lib/_soundfile_data`

## Additional Dependenices (should be shipped with frozen Demucs; not included with this repository's releases)

### `ffmpeg` and `ffprobe`

The directory containing `ffmpeg` and `ffprobe` binaries should be added to the `PATH` environment variable in the environment in which `demucs` is run.

#### Windows

https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-essentials.zip

#### macOS

- https://evermeet.cx/ffmpeg/ffmpeg-109428-g10a56363a7.zip
- https://evermeet.cx/ffmpeg/ffprobe-109428-g10a56363a7.zip

### Models

Downloaded models and their corresponding YAML file should be placed in a directory, and that directory should be passed to Demucs via the `--repo` command line argument.

#### `htdemucs_ft`

- https://dl.fbaipublicfiles.com/demucs/hybrid_transformer/f7e0c4bc-ba3fe64a.th
- https://dl.fbaipublicfiles.com/demucs/hybrid_transformer/d12395a8-e57c48e6.th
- https://dl.fbaipublicfiles.com/demucs/hybrid_transformer/92cfc3b6-ef3bcb9c.th
- https://dl.fbaipublicfiles.com/demucs/hybrid_transformer/04573f0d-f3cf25b2.th
- https://raw.githubusercontent.com/facebookresearch/demucs/main/demucs/remote/htdemucs_ft.yaml

### List of all filenames (in case you need a model other than `htdemucs_ft`)

https://raw.githubusercontent.com/facebookresearch/demucs/main/demucs/remote/files.txt
