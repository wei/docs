* [Install and configure Amplify CLI](https://docs.amplify.aws/cli/start/install)
* A Flutter application targeting Flutter SDK >= 1.20 (stable version) with Amplify libraries integrated
    * An iOS configuration targeting at least iOS 13.0
    * An Android configuration targeting at least Android API level 21 (Android 5.0) or above
    * For a full example of please follow the [project setup walkthrough](~/lib/project-setup/create-application.md)

<amplify-callout warning>

If you are using Flutter v2 and encountering build errors involving minimum deployment targets, you may need to update your app's `Podfile` in the `ios` directory.

You should update the `post_install` hook to include the following:

</amplify-callout>

```diff
 post_install do |installer|
   installer.pods_project.targets.each do |target|
     flutter_additional_ios_build_settings(target)
+    target.build_configurations.each do |config|
+      config.build_settings.delete 'IPHONEOS_DEPLOYMENT_TARGET'
+    end
   end
 end
```
