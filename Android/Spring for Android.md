# Spring for Android

### RestTemplate, MappingJackson2HttpMessageConverter

#### build.gradle(Module: app)
```
android {

    ...

    packagingOptions {
        exclude 'META-INF/DEPENDENCIES'
        exclude 'META-INF/NOTICE'
        exclude 'META-INF/NOTICE.txt'
        exclude 'META-INF/notice.txt'
        exclude 'META-INF/LICENSE'
        exclude 'META-INF/LICENSE.txt'
        exclude 'META-INF/license.txt'
        exclude 'META-INF/ASL2.0'
    }
}

dependencies {
    ...    
    compile 'org.springframework.android:spring-android-rest-template:2.0.0.M3'
    compile 'com.fasterxml.jackson.core:jackson-databind:2.3.2'
}
```

#### JSON
```json
[{"id":"1","name":"test1"},{"id":"2","name":"test2"},{"id":"3","name":"test3"}]

```

#### Model
```java
class Person{
  private Long id;
  private String name;

  public Long getId(){
    return id;
  }

  public setId(Long id){
    this.id = id;
  }

  public String getName(){
    return name;
  }

  public String setName(){
    this.name = name;
  }
}
```

#### AsyncTask
```java
class Task extends AsyncTask<Void, Void, List<Person>> {

        @Override
        protected List<Person> doInBackground(Void... params) {
            try {
                RestTemplate restTemplate = new RestTemplate();
                restTemplate.getMessageConverters().add(new MappingJackson2HttpMessageConverter());
                Person[] people = restTemplate.getForObject(REQUEST_URL, Person[].class);
                return Arrays.asList(people);

            } catch (Exception e) {
            }
            return null;
        }

        @Override
        protected void onPostExecute(List<Person> people)
//            Do something                
        }
    }
```
