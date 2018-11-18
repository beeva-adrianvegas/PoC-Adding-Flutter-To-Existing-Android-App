# PoC-Adding-Flutter-To-Existing-Android-App
In this poc we can see how add a Flutter module to an existing Android app

## Getting Started

Create a Flutter module project with some Dart code to get you started 

    cd some/path/
    flutter create -t module my_flutter

You can build that library using Gradle if you want 

    cd .android/
    ./gradlew flutter:assembleDebug

Include the Flutter module as a sub-project in the host app's settings.gradle :

    include ':app'                                    
      setBinding(new Binding([gradle: this]))           
      evaluate(new File(                                                     
      settingsDir.parentFile,                                             
      'my_flutter/.android/include_flutter.groovy'                         
    ))     

Add this dependencie to your MyApp/app/build.gradle 

    dependencies {
      implementation project(':flutter')
    }

Now you can use the Flutter module as you can see in **MainActivity** of this project.
