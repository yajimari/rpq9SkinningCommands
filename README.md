# rpq9SkinningCommands

**rpq9SkinningCommands** is a custom commands for Autodesk Maya.  
This repository uses a multi-license structure.

## ⬇️ Installation

1. Download the files in this repository from the Releases page.
2. Copy the appropriate version of `rpq9SkinningCommands.mll` or `rpq9SkinningCommands.so` from under the `plug-ins` folder to the directory set in `MAYA_PLUG_IN_PATH`.(You can check the destination directory by running the code below.)
```python
import os
from pathlib import Path
import maya.cmds as cmds

version = cmds.about(majorVersion=True)
if int(version) < 2025:
    raise RuntimeError('Unsupported Maya version.')

appDir = Path(os.environ.get("MAYA_APP_DIR"))
currentVerPluginDir = appDir.joinpath(version, 'plug-ins')
print('Installation directory: ', currentVerPluginDir.as_posix())
```
3. Load `rpq9SkinningCommands.mll` or `rpq9SkinningCommands.so` from the Plug-in Manager.

##  📖 Documentation

See `command-reference.md` for command documentation.

## ⚠️ Limitations

- Supported in Maya 2025 and later versions. Not available in earlier versions.


## 📄 License

Unless otherwise stated, files in this repository are licensed under the **MIT License**.

Files under `plug-ins/**` are not licensed under the MIT License.
They are licensed under the separate custom license
`LicenseRef-rpq9RestrictedBinary`.

Please refer to the following files for the full license texts:

- `LICENSES/MIT.txt`
- `LICENSES/LicenseRef-rpq9RestrictedBinary.txt`

The applicable license for each file is determined by the license notice for that file,
any adjacent `.license` file, and `REUSE.toml`.