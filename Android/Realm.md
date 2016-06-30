# Realm

## Realm Gradle 설정

### build.gradle(Project)

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
### build.gradle(Module: app)

```gradle
apply plugin: 'realm-android'
```

## MyApplication Class 추가

Application Class에서 Realm 설정

### AndroidManifest.xml 수정
```xml
<application
    android:name=".application.MyApplication"
    ...>
    ...
</application>

```
### Application Package 속 MyApplication Class 추가
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
애플리케이션 시작시 MyApplication.onCreate 실행

onCreate에서 기본 RealmConfiguration 설정
