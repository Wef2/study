### Layout border

Layout border bottom

#### res/drawable/layout_border.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<layer-list xmlns:android="http://schemas.android.com/apk/res/android">

    <item>
        <shape android:shape="rectangle">
            <solid android:color="#d7d7d7" />
        </shape>
    </item>
    <item android:bottom="1dp">
        <shape android:shape="rectangle">
            <solid android:color="#ffffff" />
        </shape>
    </item>

</layer-list>
```

#### res/layout/sample_layout.xml
```xml
<RelativeLayout
     android:layout_width="match_parent"
     android:layout_height="wrap_content"
     android:background="@drawable/layout_border"
     android:padding="16dp">

</RelativeLayout>
```
