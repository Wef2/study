# EditText

### Example Source Code

```xml
<EditText
  android:layout_width="wrap_content"
  android:layout_height="wrap_content"
  android:maxLength="10"
  android:inputType="number"
  android:imeOptions="actionDone"
  />

```

```java

EditText editText = (EditText) findViewById(R.id.edit_text);
editText.setImeOptions(EditorInfo.IME_ACTION_DONE);

```

### Attributes

- maxLength

- inputType

- imeOptions
