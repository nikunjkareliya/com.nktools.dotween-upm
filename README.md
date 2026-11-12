# DOTween (UPM Package)

A Unity Package Manager (UPM) distribution of **DOTween** (v1.3.045) by Daniele Giardini (Demigiant), structured for Git-based UPM dependency management across shared libraries and client games.

## Features

- **Standard UPM Layout**: Clean separation into `Runtime/` and `Editor/` assemblies.
- **Assembly Definitions**:
  - `DOTween.Modules` (Runtime, auto-referenced, DG.Tweening namespace)
  - `DOTween.Editor` (Editor-only utilities and inspector tools)
- **Ecosystem Compatibility**: Configured as `com.demigiant.dotween` so packages like **UniTask** (`UniTask.DOTween.asmdef`) automatically activate async tween extensions (`ToUniTask()`).
- **GUID Preservation**: Preserves official Demigiant GUIDs so existing project references remain unbroken.

## Installation

### Via Unity Package Manager (Git URL)

Add the Git URL directly in Unity's Package Manager window (**Add package from git URL...**):

```text
git@github.com:nikunjkareliya/com.nktools.dotween-upm.git#v1.3.45
```

Or add to your project's `Packages/manifest.json`:

```json
{
  "dependencies": {
    "com.demigiant.dotween": "https://github.com/nikunjkareliya/com.nktools.dotween-upm.git#v1.3.45"
  }
}
```

### In Shared Packages (`package.json`)

To declare DOTween as a dependency of another package (e.g. `com.nktools.shared-core`):

```json
"dependencies": {
  "com.demigiant.dotween": "https://github.com/nikunjkareliya/com.nktools.dotween-upm.git#v1.3.45"
}
```

Then in your `.asmdef` file, add `"DOTween.Modules"` to `"references"`:

```json
"references": [
  "DOTween.Modules"
]
```

## Setup & Settings

1. Open **Tools > Demigiant > DOTween Utility Panel** in the Unity Editor to inspect or update preferences.
2. DOTween settings are saved in your project's `Assets/Resources/DOTweenSettings.asset`.
3. In code, simply use:
   ```csharp
   using DG.Tweening;
   ```

## License

DOTween is copyright (c) Daniele Giardini - Demigiant.
See [readme.txt](readme.txt) and [http://dotween.demigiant.com/license.php](http://dotween.demigiant.com/license.php) for full licensing information.
