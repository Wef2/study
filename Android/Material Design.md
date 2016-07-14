# Android Material Design

### Floating Hint EditText

##### Dependency in gradle

```gradle
compile 'com.android.support:design:22.2.0'
```

##### XML

```xml
<android.support.design.widget.TextInputLayout
    android:id="@+id/input_layout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <EditText
        android:id="@+id/edit_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="@string/edit_text_hint" />

</android.support.design.widget.TextInputLayout>
```
