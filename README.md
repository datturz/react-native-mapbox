1. Install Mapbox 
    ```bash 
         $ npm i @mapbox/react-native-mapbox-gl
    ```
2. go to __*yourProject/android/build.gradle*__
    ```java
    allprojects {
        repositories {
            jcenter()
            maven { url "$rootDir/../node_modules/react-native/android" }
            maven { url "https://jitpack.io" }
            maven { url "https://maven.google.com" }
        }
    }
    ```

3. go to __*yourProject/android/app/build.gradle*__
    ```java
    dependencies {
        compile project(':mapbox-react-native-mapbox-gl')
    }
    ```

4. go to __*yourProject/android/settings.gradle*__
    ```java
    include ':mapbox-react-native-mapbox-gl'
    project(':mapbox-react-native-mapbox-gl').projectDir = new File(rootProject.projectDir, '../node_modules/@mapbox/react-native-mapbox-gl/android/rctmgl')
    ```

5. go to __*yourProject/android/app/src/main/java/com/yourProject/MainApplication.java*__

    insert after ```import com.facebook.soloader.SoLoader```:
    ```java
    import com.mapbox.rctmgl.RCTMGLPackage;
    ```

    insert inside ```getPackages()``` after ```new MainReactPackage(),```
    ```java
    new RCTMGLPackage()
    ```
6. signup to mapbox.com & get your acces token !