# Usage of Android Studio for Android module development

Сергей Волков at 2018-07-24 proposed a procedure for usage of Android Studio for Android Titanium module development.
   
*I use Android Studio for module development, all debugging tools work fine.*

You should build your module, then setup "Project Structure":

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