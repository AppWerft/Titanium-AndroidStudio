
# Use Android Studio to develop native Titanium Android Modules
 
This tutorial is based on the instructions from [drauggres](https://github.com/drauggres) via the [Titanium Slack Community](http://tislack.org), thank you!!

### Create a new Project

<img src="https://www.cloudcms.com/images/quickstarts/titanium/titanium.206f8815.png" width=100 />

Example:
```
ti create --type module --name test --platform android --id com.company.test --workspace-dir ./ 
```

Or simplified:
```
ti create -t module -n test -p android --id com.company.test -d ./
```

> Note: The same goes for the Appc-CLI and `appc new [args]`.

### Sample Output

```
[INFO]  Creating module project
[INFO]  Template directory: /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/templates/module/default
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/templates/module/default/template/LICENSE => /Users/fuerst/Desktop/AndroidStudioTitanium/test/LICENSE
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/templates/module/default/template/README.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/README
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/templates/module/default/template/assets/README.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/assets/README
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/templates/module/default/template/documentation/index.md.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/documentation/index.md
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/templates/module/default/template/example/app.js.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/example/app.js
[DEBUG] Detecting Android environment...
[INFO]  Copying android platform resources
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/.classpath.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/.classpath
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/.project.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/.project
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/.settings/org.eclipse.jdt.apt.core.prefs.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/.settings/org.eclipse.jdt.apt.core.prefs
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/.settings/org.eclipse.jdt.core.prefs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/.settings/org.eclipse.jdt.core.prefs
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/Resources/README.md => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/Resources/README.md
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/build.properties.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/build.properties
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/build.xml.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/build.xml
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/lib/README => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/lib/README
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/manifest.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/manifest
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/platform/README.md => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/platform/README.md
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/src/{{ModuleIdAsFolder}}/ExampleProxy.java.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/src/com/company/test/ExampleProxy.java
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/src/{{ModuleIdAsFolder}}/{{ModuleNameCamel}}Module.java.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/src/com/company/test/TestModule.java
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/7.0.1.GA/android/templates/module/default/template/android/timodule.xml => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/timodule.xml
[INFO]  Project created successfully in 1s 318ms
```

### Overview: `ti create`

```
user$ ti create -help
Titanium Command-Line Interface, CLI version 5.0.11, Titanium SDK version 7.0.1.GA
Copyright (c) 2012-2015, Appcelerator, Inc.  All Rights Reserved.

Please report bugs to http://jira.appcelerator.org/

Usage: titanium create --type <value> [--force] [--log-level <level>]

Creates a new Titanium application, native module, or Apple Watch™ app.

Apple, iPhone, and iPad are registered trademarks of Apple Inc. Apple Watch is a trademark of Apple
Inc.

Android is a trademark of Google Inc.

Create Flags:
   -f, --force   force project creation even if path already exists 
 
Create Options:
   --log-level <level>   minimum logging level  [trace, debug, info, warn, error]
   -t, --type <value>    the type of project to create  [app, applewatch, module]
 
Create --type=app Options:
   --id <value>                  the App ID in the format 'com.companyname.appname'
   --template <value>            the name of the project template, path to template dir, path to zip
                                 file, or url to zip file  [default: default]
   -d, --workspace-dir <value>   the directory to place the project in
   -n, --name <value>            the name of the project
   -p, --platforms <value>       one or more target platforms.  [all, android, mobileweb, iphone,
                                 ipad, windows]
   -u, --url <value>             your company/personal URL
 
Create --type=applewatch Options:
   --template <value>          the name of the project template, path to template dir, path to zip
                               file, or url to zip file  [default: watchos2-swift]
   -d, --project-dir <value>   the directory containing the project  [default: .]
   -n, --name <value>          the name of the watch app
 
Create --type=module Options:
   --id <value>                  the App ID in the format 'com.companyname.appname'
   --template <value>            the name of the project template, path to template dir, path to zip
                                 file, or url to zip file  [default: default]
   -d, --workspace-dir <value>   the directory to place the project in
   -n, --name <value>            the name of the project
   -p, --platforms <value>       one or more target platforms.  [all, android, mobileweb, ios,
                                 windows]
 
Global Flags:
   --no-banner          disable Titanium version banner 
   --no-colors          disable colors 
   --no-progress-bars   disable progress bars 
   --no-prompt          disable interactive prompting 
   -h, --help           displays help 
   -q, --quiet          suppress all output 
   -v, --version        displays the current version 
 
Global Options:
   --config <json>        serialized JSON string to mix into CLI config
   --config-file <file>   path to CLI config file  [default: /Users/fuerst/.titanium/config.json]
   -s, --sdk <version>    Titanium SDK version to use to bootstrap SDK-level commands and parse the
                          tiapp.xml; actual Titanium SDK used determined by <sdk-version> in the
                          tiapp.xml  [default: latest]
```

This command creates a folder `test` with it's subfolders.

## Installing Android Studio

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/34/Android_Studio_icon.svg/1200px-Android_Studio_icon.svg.png" width= 90 />

After [downloading](https://developer.android.com/studio/install) Android Studio you can install the dmg.

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/Install.png" width=500 />

And install the required SDK:

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/Components.png" width=500 />

## Starting Android Studio

### Add Project SDK

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/Studio.png" width=400 />

If you open an existing project and point to our `test` - folder, then there is nothing to show on the left side bar.  

Ok, next we add the SDK to project settings by calling this dialog:

Menu: **File/Projectstructure**

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/SDK.png" width=500 />

### Add Android Build Files

First you have to create some folders:

```
cd <module_path>
mkdir platform/android
mkdir platform/android/res
```
For accessing AndroidManifest you have to build an empty project:

```
ti build -p android -b
```
Now you can add the AndroidManifest.xml from folder `build/intermediates/manifests/aapt/AndroidManifest.xml`

After this preparations  you can add the facets to project:

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/FacetList.png" width=900 />

- Manifest: `<module_path>/android/build/intermediates/manifests/aapt/AndroidManifest.xml`
- Resources: `<module_path>/android/platform/android/res`
- Assets: `<module_path>/android/assets`
- Native libs: `<module_path>/android/libs`

**Important**: Also uncheck `Generate sources automatically`

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/NoSource.png" width=800 />

### Add Titanium libraries

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/Libraries.png" width=300 />

Add Titanium libraries (`titanium.jar`, `kroll-common.jar`, `kroll-apt.jar`) (edited)

In the end you will see:

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/Libraries2.png" width=600 />

And now you can edit the module:

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/Full.png" width=800 />

## Configuring Source root

Mark `src` directory (right click -> `Mark Directory As`)  as `Sources Root`.

<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/AsRoot.png" width=800 />

### Notes

See the `test/` directory for details!

### Potential pitfalls

```
Unregistered VCS root detected
The directory /Users/fuerst/Desktop/AndroidStudioTitanium is under Git, but is not registered in the Settings.
```
```
Can't start Git: /usr/local/bin/git
The path to Git executable is probably not valid. 
```
