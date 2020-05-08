SoftMaskForUGUI
===

UI Soft Mask is a smooth masking component for Unity UI (uGUI) elements.

![](https://user-images.githubusercontent.com/12690315/50282438-18408d80-0496-11e9-8f86-81e804edadd4.png)

[![](https://img.shields.io/npm/v/com.coffee.softmask-for-ugui?label=openupm&registry_uri=https://package.openupm.com)](https://openupm.com/packages/com.coffee.softmask-for-ugui/)
[![](https://img.shields.io/github/v/release/mob-sakai/SoftMaskForUGUI?include_prereleases)](https://github.com/mob-sakai/SoftMaskForUGUI/releases)
[![](https://img.shields.io/github/release-date/mob-sakai/SoftMaskForUGUI.svg)](https://github.com/mob-sakai/SoftMaskForUGUI/releases)  
![](https://img.shields.io/badge/unity-2017.1%20or%20later-green.svg)
[![](https://img.shields.io/github/license/mob-sakai/SoftMaskForUGUI.svg)](https://github.com/mob-sakai/SoftMaskForUGUI/blob/upm/LICENSE.txt)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-orange.svg)](http://makeapullrequest.com)
[![](https://img.shields.io/github/watchers/mob-sakai/SoftMaskForUGUI.svg?style=social&label=Watch)](https://github.com/mob-sakai/SoftMaskForUGUI/subscription)
[![](https://img.shields.io/twitter/follow/mob_sakai.svg?label=Follow&style=social)](https://twitter.com/intent/follow?screen_name=mob_sakai)

<< [Description](#Description) | [WebGL Demo](#demo) | [Installation](#installation) | [Usage](#usage) | [For Your Custom Shader](#support-soft-masks-with-your-custom-shaders) >>



<br><br><br><br>
## Description

By using SoftMask instead of the default Mask component, you can beautifully represent the rounded edges of UI elements.

![](https://user-images.githubusercontent.com/12690315/50282806-4b375100-0497-11e9-891c-35309d332c7b.png)

#### Features

* SoftMask is compatible with Mask.
* You can adjust the visible part.  
![](https://user-images.githubusercontent.com/12690315/48661087-01ca9f00-eab0-11e8-8878-772a1ed1fb7b.gif)
* Text, Image, RawImage can be used as a masking.
* Support multiple-sprites and SpriteAtlas.
* Support up to 4 nested soft masks.  
![](https://user-images.githubusercontent.com/12690315/48708326-a0d4cf80-ec45-11e8-83b8-f55d29138db7.png)
* Support scroll view.  
![](https://user-images.githubusercontent.com/12690315/48708527-2b1d3380-ec46-11e8-9adf-9d33498f0353.png)
* Support inversed soft mask.  
![](https://user-images.githubusercontent.com/12690315/48708328-a0d4cf80-ec45-11e8-9945-e877faabc968.png)
* Support overlay, camera space and world space.  
![](https://user-images.githubusercontent.com/12690315/48708329-a0d4cf80-ec45-11e8-8328-16b697f981ec.png)
* (Option) Raycast is filtered only for the visible part.  
![](https://user-images.githubusercontent.com/12690315/48708330-a16d6600-ec45-11e8-94bf-afecd1bd9a39.png)
* Contain soft maskable UI shader.
* Support soft masks in your custom shaders by adding just 3 lines. For details, please see [Development Note](#support-soft-masks-in-your-custom-shaders). 
* Adjust soft mask buffer size to improve performance.
* Convert existing Mask to SoftMask from context menu.  
![](https://user-images.githubusercontent.com/12690315/48659018-902e2900-ea8e-11e8-9b6e-224365cdde7f.png)
* Render the soft mask buffer only when needed to improve performance.
* Add a SoftMaskable component to the child UI elements of SoftMask from the inspector.  
![](https://user-images.githubusercontent.com/12690315/50284153-76bc3a80-049b-11e9-8c55-719af897960a.png)
* Preview soft mask buffer in inspector.  
![](https://user-images.githubusercontent.com/12690315/50284151-7459e080-049b-11e9-9cd3-24fb476766dc.png)
* Make multiple holes on one background by 'Parts of parent' option.  
![](https://user-images.githubusercontent.com/12690315/54102470-f5c26e80-440b-11e9-89d1-899aa4dca00d.png)



#### Components

|Component|Description|Screenshot|
|-|-|-|
|SoftMask|Use instead of Mask for smooth masking.<br><br>**Show Mask Graphic:** Show the graphic that is associated with the Mask render area.<br>**Desampling Rate:** The desampling rate for soft mask buffer. The larger the value, the better the performance but the lower the quality.<br>**Softness:** The value used by the soft mask to select the area of influence defined over the soft mask's graphic.<br>**Ignore Parent:** Should the soft mask ignore parent soft masks?<br>**Part Of Parent:** Is the soft mask a part of parent soft mask?|<img src="https://user-images.githubusercontent.com/12690315/50319746-377a0200-050c-11e9-96ae-a3a0ec81765f.png" width="600px">|
|SoftMaskable|Add this component to Graphic under SoftMask for smooth masking.<br><br>**Inverse:** The graphic will be visible only in areas where no mask is present.|<img src="https://user-images.githubusercontent.com/12690315/50319747-39dc5c00-050c-11e9-85fa-dd6ea9065daf.png" width="600px">|



<br><br><br><br>
## Demo

[WebGL Demo](http://mob-sakai.github.io/SoftMaskForUGUI)



<br><br><br><br>
## Installation

#### Requirement

* Unity 2017.1 or later
* No other SDK are required

#### Using OpenUPM (for Unity 2018.3 or later)

This package is available on [OpenUPM](https://openupm.com). 
You can install it via [openupm-cli](https://github.com/openupm/openupm-cli).
```
openupm add com.coffee.softmask-for-ugui
```

#### Using Git (for Unity 2018.3 or later)

Find the manifest.json file in the Packages folder of your project and edit it to look like this:
```js
{
  "dependencies": {
    "com.coffee.softmask-for-ugui": "https://github.com/stalker1hunt/SoftMaskForUGUI.git",
    ...
  },
}
```

To update the package, change suffix `#{version}` to the target version.

* e.g. `"com.coffee.softmask-for-ugui": "https://github.com/mob-sakai/SoftMaskForUGUI.git#1.0.0",`

Or, use [UpmGitExtension](https://github.com/mob-sakai/UpmGitExtension) to install and update the package.

#### For Unity 2018.2 or earlier

1. Download a source code zip file from [Releases](https://github.com/mob-sakai/SoftMaskForUGUI/releases) page
2. Extract it
3. Import it into the following directory in your Unity project
   - `Packages` (It works as an embedded package. For Unity 2018.1 or later)
   - `Assets` (Legacy way. For Unity 2017.1 or later)



<br><br><br><br>
## How to play demo

#### For Unity 2019.1 or later

1. Open `Package Manager` window and select `UI Soft Mask` package in package list
2. Click `Import in project` button  
![](https://user-images.githubusercontent.com/12690315/79000480-a8bd4880-7b87-11ea-89c7-a17033a486ba.png)
3. The demo will be imported into `Assets/Samples/UI Soft Mask/{version}/Demo`｡  
Open `UISoftMask_Demo` scene and play it

#### For Unity 2018.4 or earlier

1. Select `Assets/Samples/UI Soft Mask Demo` from menu  
![Assets_と_Menubar](https://user-images.githubusercontent.com/12690315/79001101-dd7dcf80-7b88-11ea-9cf2-b44c6c5c9b17.png)
2. The demo will be imported into `Assets/Samples/UI Soft Mask/{version}/Demo`.  
Open `UISoftMask_Demo` scene and play it


<br><br><br><br>
## Usage

1. Add a SoftMask component instead of Mask component.  
Or, convert an existing Mask component to SoftMask component from the context menu.  
![](https://user-images.githubusercontent.com/12690315/48659018-902e2900-ea8e-11e8-9b6e-224365cdde7f.png)
2. Add a SoftMaskable components to the child UI elements of the SoftMask component.  
![](https://user-images.githubusercontent.com/12690315/48704424-d4a9f800-ec39-11e8-8d65-8b7d1975750c.png)  
Or, add a SoftMaskable components from the inspector of the SoftMask component.  
![](https://user-images.githubusercontent.com/12690315/50284153-76bc3a80-049b-11e9-8c55-719af897960a.png)
3. Adjust softness setting of SoftMask.  
![](https://user-images.githubusercontent.com/12690315/48661087-01ca9f00-eab0-11e8-8878-772a1ed1fb7b.gif)
4. Enjoy!



<br><br><br><br>
## Support soft masks with your custom shaders

<b>With just three additional lines,</b> you can now support softmasks in your custom shaders!

1. Add `#pragma` and `#include` directives, where `SOFTMASK_EDITOR` is an editor-only keyword and is not included in the build.
If you didn't use package manager to install, include `SoftMask.cginc` in the appropriate path instead.
```
#include "Packages/com.coffee.softmask-for-ugui/Shaders/SoftMask.cginc"
#pragma shader_feature __ SOFTMASK_EDITOR
```
2. Apply a soft mask in the fragment shader.  
This operation determines the final alpha according to the soft mask buffer.  
  - `IN.vertex`: the clip position
  - `IN.worldPosition`: the world position
```
color.a *= SoftMask(IN.vertex, IN.worldPosition);
```

As an example of implementation, please see [UI-Default-SoftMask.shader](https://raw.githubusercontent.com/mob-sakai/SoftMaskForUGUI/upm/Shaders/Resources/UI-Default-SoftMask.shader).



<br><br><br><br>
## License

* MIT
* © UTJ/UCL



<br><br><br><br>
## Support

This is an open-source project that I am developing in my free time. 
If you like it, you can support me. 
By supporting, you let me spend more time working on better tools that you can use for free. :)

[![become_a_patron_on_patreon](https://user-images.githubusercontent.com/12690315/50731629-3b18b480-11ad-11e9-8fad-4b13f27969c1.png)](https://www.patreon.com/join/2343451?)  
[![become_a_sponsor_on_github](https://user-images.githubusercontent.com/12690315/66942881-03686280-f085-11e9-9586-fc0b6011029f.png)](https://github.com/users/mob-sakai/sponsorship)



## Author

[mob-sakai](https://github.com/mob-sakai)
[![](https://img.shields.io/twitter/follow/mob_sakai.svg?label=Follow&style=social)](https://twitter.com/intent/follow?screen_name=mob_sakai) 



## See Also

* GitHub page : https://github.com/mob-sakai/SoftMaskForUGUI
* Releases : https://github.com/mob-sakai/SoftMaskForUGUI/releases
* Issue tracker : https://github.com/mob-sakai/SoftMaskForUGUI/issues
* Change log : https://github.com/mob-sakai/SoftMaskForUGUI/blob/upm/CHANGELOG.md
