# Usage of Android Studio for Android module development

Сергей Волков at 2018-07-24 proposed in our [slack channnel](https://ti-slack.slack.com/) a procedure for usage of Android Studio for Android Titanium module development. 

<details><summary>Screenshot of Slack dialog</summary>
<img src="https://raw.githubusercontent.com/AppWerft/Titanium-AndroidStudio/master/screens/%D0%A1%D0%B5%D1%80%D0%B3%D0%B5%D0%B9_%D0%92%D0%BE%D0%BB%D0%BA%D0%BE%D0%B2.png" width=700 />
</details>

This repo shows en detail how to.

## Creation of project
Example:
```
ti create --type module --name test --platform android --id com.company.test --workspace-dir ./ 
```

Or in short form:
```
ti create -t module -n test -p android --id com.company.test -d ./
```

<details><summary>Output sample</summary>

```
Please report bugs to http://jira.appcelerator.org/

[INFO]  Creating module project
[INFO]  Template directory: /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/templates/module/default
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/templates/module/default/template/LICENSE => /Users/fuerst/Desktop/AndroidStudioTitanium/test/LICENSE
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/templates/module/default/template/README.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/README
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/templates/module/default/template/assets/README.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/assets/README
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/templates/module/default/template/documentation/index.md.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/documentation/index.md
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/templates/module/default/template/example/app.js.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/example/app.js
[DEBUG] Detecting Android environment...
[INFO]  Copying android platform resources
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/.classpath.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/.classpath
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/.project.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/.project
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/.settings/org.eclipse.jdt.apt.core.prefs.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/.settings/org.eclipse.jdt.apt.core.prefs
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/.settings/org.eclipse.jdt.core.prefs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/.settings/org.eclipse.jdt.core.prefs
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/Resources/README.md => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/Resources/README.md
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/build.properties.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/build.properties
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/build.xml.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/build.xml
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/lib/README => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/lib/README
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/manifest.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/manifest
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/platform/README.md => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/platform/README.md
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/src/{{ModuleIdAsFolder}}/ExampleProxy.java.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/src/com/company/test/ExampleProxy.java
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/src/{{ModuleIdAsFolder}}/{{ModuleNameCamel}}Module.java.ejs => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/src/com/company/test/TestModule.java
[DEBUG] Copying /Library/Application Support/Titanium/mobilesdk/osx/5.5.1.GA/android/templates/module/default/template/android/timodule.xml => /Users/fuerst/Desktop/AndroidStudioTitanium/test/android/timodule.xml
[INFO]  Project created successfully in 1s 318ms
```
</details>

<details><summary>Full syntax of ti create</summary>

```
fuerst$ ti create -help
Titanium Command-Line Interface, CLI version 5.0.11, Titanium SDK version 5.5.1.GA
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

</details>

This command creates a folder `test` with some subfolders.

https://wiki.appcelerator.org/display/guides2/Android+Module+Development+Guide





1. Select proper `Project SDK`
2. Add `Android` facet:
-  Manifest: `<module_path>/android/build/intermediates/manifests/aapt/AndroidManifest.xml`
- Resources: `<module_path>/android/platform/android/res`
- Assets: `<module_path>/android/assets`
- Native libs: `<module_path>/android/libs`
Also uncheck `Generate sources automatically`
3. Add Titanium libraries (`titanium.jar`, `kroll-common.jar`, `kroll-apt.jar`) (edited)
 


Hans Knöchel [15 days ago]
we should update the guides for android studio as well!


Antonio [15 days ago]
thank you @Sergey Volkov! I will try to follow your instructions. Do you mean by "you should build your module" that I have to do that manually from the CLI with "appc run" anyway? So I use Android Studio to test the app WHERE I will include my native module? I was wondering if I could use Android Studio to edit the code of the module itself


Hans Knöchel [14 days ago]
ti build -p --build-only


Sergey Volkov [14 days ago]
>Do you mean by "you should build your module" that I have to do that manually from the CLI with "appc run" anyway?
Yes, `ti build -p android --build-only`
>So I use Android Studio to test the app WHERE I will include my native module?
Correct. You can't run module without app.
>I was wondering if I could use Android Studio to edit the code of the module itself
Why not? Don't forget (3) from comment above.


Jorge Macías [14 days ago]
@Sergey Volkov That deserves to have a post blog where you detail it. It could be super useful for Ti community :smile:

cc: @hans

Congrats (edited)