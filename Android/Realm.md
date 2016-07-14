# Realm

### Realm Gradle

##### build.gradle(Project)

```gradle
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:2.1.2'
        classpath "io.realm:realm-gradle-plugin:1.0.1"      
    }
}

```
##### build.gradle(Module: app)

```gradle
apply plugin: 'realm-android'
```

### MyApplication Class

##### AndroidManifest.xml
```xml
<application
    android:name=".MyApplication"
    ...>
    ...
</application>

```
```java
public class MyApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();
        RealmConfiguration config = new RealmConfiguration.Builder(this).build();
        Realm.deleteRealm(config);
        Realm.setDefaultConfiguration(config);
    }
}
```
