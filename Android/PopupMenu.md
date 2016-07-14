### Android

#### res/menu/popup_menu.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:id="@+id/menu1" android:title="Menu 1" />
    <item android:id="@+id/menu2" android:title="Menu 2" />
    <item android:id="@+id/menu3" android:title="Menu 3" />
    <item android:id="@+id/menu4" android:title="Menu 4" />
</menu>
```

#### Android source code
```java
selectButton.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        PopupMenu popup = new PopupMenu(getActivity(), selectButton);
        popup.getMenuInflater().inflate(R.menu.popup_menu, popup.getMenu());
        popup.show();
    }
});
```
