# SearchableActivity

### Add the Search View to the App Bar
##### res/menu/search_menu.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">
    <item
        android:id="@+id/search"
        android:icon="@drawable/ic_search"
        android:title="@string/search_title"
        app:actionViewClass="android.support.v7.widget.SearchView"
        app:showAsAction="collapseActionView|ifRoom" />
</menu>
```

### Create a Searchable Configuration
##### res/xml/searchable.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<searchable xmlns:android="http://schemas.android.com/apk/res/android"
    android:label="@string/app_name"
    android:hint="@string/search_hint" >
</searchable>
```

### Creating a Searchable Activity

##### SearchResultsActivity.java
```java
public class SearchResultsActivity extends AppCompatActivity {

    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        MenuInflater inflater = getMenuInflater();
        inflater.inflate(R.menu.search_menu, menu);
        SearchManager searchManager = (SearchManager) getSystemService(Context.SEARCH_SERVICE);
        SearchView searchView = (SearchView) menu.findItem(R.id.search).getActionView();
        searchView.setSearchableInfo(searchManager.getSearchableInfo(getComponentName()));
        return true;
    }

}

```

### Declaring a searchable activity
##### AndroidManifest.xml
```xml
<application ... >
    <activity android:name=".SearchResultsActivity" >
        <intent-filter>
            <action android:name="android.intent.action.SEARCH" />
        </intent-filter>
        <meta-data android:name="android.app.searchable"
                   android:resource="@xml/searchable"/>
    </activity>
    ...
</application>
```

### For more information

https://developer.android.com/training/search/setup.html#create-sa
https://developer.android.com/guide/topics/search/search-dialog.html
https://www.youtube.com/watch?v=9OWmnYPX1uc
