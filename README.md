# demucs-cxfreeze

## Freezing `demucs`

**With CUDA support (Windows & Linux)**
```
pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu116 demucs SoundFile cx-Freeze
```
**CPU only**
```
pip3 install torch torchvision torchaudio demucs SoundFile cx-Freeze
```
And then:
```
cxfreeze main.py --target-dir=dist --target-name=demucs-cxfreeze --packages=torch
```

Copy `venv/Lib/site-packages/_soundfile_data` to `dist/lib/_soundfile_data`

## Additional Dependenices (should be shipped with frozen Demucs; not included with this repository's releases)

### `ffmpeg` and `ffprobe`

The directory containing `ffmpeg` and `ffprobe` binaries should be added to the `PATH` environment variable in the environment in which `demucs` is run.

#### Windows

https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-essentials.zip

#### macOS

- https://evermeet.cx/ffmpeg/ffmpeg-107374-g046b05082d.zip
- https://evermeet.cx/ffmpeg/ffprobe-107374-g046b05082d.zip

### Models

Downloaded models and their corresponding YAML file should be placed in a directory, and that directory should be passed to Demucs via the `--repo` command line argument.

#### `mdx_extra_q`

- https://dl.fbaipublicfiles.com/demucs/mdx_final/83fc094f-4a16d450.th
- https://dl.fbaipublicfiles.com/demucs/mdx_final/7fd6ef75-a905dd85.th
- https://dl.fbaipublicfiles.com/demucs/mdx_final/14fc6a69-a89dd0ee.th
- https://dl.fbaipublicfiles.com/demucs/mdx_final/464b36d7-e5a9386e.th
- https://raw.githubusercontent.com/facebookresearch/demucs/main/demucs/remote/mdx_extra_q.yaml

### List of all filenames (in case you need a model other than `mdx_extra_q`)

https://raw.githubusercontent.com/facebookresearch/demucs/main/demucs/remote/files.txt
