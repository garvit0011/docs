To initialize the Amplify Auth and API categories you call `Amplify.addPlugin()` method for each category. To complete initialization call `Amplify.configure()`.

Add the following code to your `onCreate()` method in your application class:

<amplify-block-switcher>
<amplify-block name="Java">

```java
Amplify.addPlugin(new AWSApiPlugin());
```

Your class will look like this:

```java
public class MyAmplifyApp extends Application {
    @Override
    public void onCreate() {
        super.onCreate();

        try {
            // Add this line to add the AWSApiPlugin plugin
            Amplify.addPlugin(new AWSApiPlugin());
            Amplify.configure(getApplicationContext());

            Log.i("MyAmplifyApp", "Initialized Amplify");
        } catch (AmplifyException error) {
            Log.e("MyAmplifyApp", "Could not initialize Amplify", error);
        }
    }
}
```

</amplify-block>
<amplify-block name="Kotlin">

```kotlin
Amplify.addPlugin(AWSApiPlugin())
```

Your class will look like this:

```kotlin
class MyAmplifyApp : Application() {
    override fun onCreate() {
        super.onCreate()

        try {
            // Add this line to add the AWSApiPlugin plugin
            Amplify.addPlugin(AWSApiPlugin())
            Amplify.configure(applicationContext)

            Log.i("MyAmplifyApp", "Initialized Amplify")
        } catch (error: AmplifyException) {
            Log.e("MyAmplifyApp", "Could not initialize Amplify", error)
        }
    }
}
```

</amplify-block>
</amplify-block-switcher>