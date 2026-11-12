# DOTween (UPM Package)

A Unity Package Manager (UPM) distribution of **DOTween** (v1.3.46) by Daniele Giardini (Demigiant), optimized for Git-based UPM dependency management across shared libraries and client games.

## Features

- **Clean Runtime Engine**: Stripped of legacy precompiled Editor DLLs (`DOTweenEditor.dll`, `DOTweenUpgradeManager.dll`) to eliminate UPM path resolution errors (`Couldn't find DOTween's Modules directory`) and recurring modal setup popups in read-only package caches.
- **Fast Domain Reloads**: Zero reflection scanning on script reload, resulting in faster iteration times.
- **Full Module Support**: Includes all standard DOTween modules (UI, Audio, Physics, Physics2D, Sprites, UI Toolkit) pre-wired with `DOTween.Modules.asmdef`.
- **Ecosystem Compatibility**: Configured as `com.demigiant.dotween` so packages like **UniTask** (`UniTask.DOTween.asmdef`) automatically activate async tween extensions (`ToUniTask()`).
- **GUID Preservation**: Preserves official Demigiant GUIDs so existing project references remain unbroken.

## Installation

### Via Unity Package Manager (Git URL)

Add the Git URL directly in Unity's Package Manager window (**Add package from git URL...**):

```text
git@github.com:nikunjkareliya/com.nktools.dotween-upm.git#v1.3.46
```

Or add to your project's `Packages/manifest.json`:

```json
{
  "dependencies": {
    "com.demigiant.dotween": "https://github.com/nikunjkareliya/com.nktools.dotween-upm.git#v1.3.46"
  }
}
```

### In Shared Packages (`package.json`)

To declare DOTween as a dependency of another package (e.g. `com.nktools.shared-core`):

```json
"dependencies": {
  "com.demigiant.dotween": "https://github.com/nikunjkareliya/com.nktools.dotween-upm.git#v1.3.46"
}
```

Then in your `.asmdef` file, add `"DOTween.Modules"` to `"references"`:

```json
"references": [
  "DOTween.Modules"
]
```

## Usage

In your C# scripts, simply use:

```csharp
using DG.Tweening;

// Example
transform.DOMove(Vector3.one, 1f).SetEase(Ease.OutQuad);
```

## License

DOTween is copyright (c) Daniele Giardini - Demigiant.  
See [readme.txt](readme.txt) and [http://dotween.demigiant.com/license.php](http://dotween.demigiant.com/license.php) for full licensing information.
