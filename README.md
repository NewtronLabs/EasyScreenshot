# Easy Screenshot

The easy way to take screenshots of your application programmatically.

---

## How to Use 

### Step 1

Include the below dependency in your `build.gradle` project.

```gradle
buildscript {
    repositories {
        jcenter()
        maven { url "https://newtronlabs.jfrog.io/artifactory/libs-release-local"
            metadataSources {
                artifact()
            }
        }
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5.2'
        classpath 'com.newtronlabs.android:plugin:4.0.5'
    }
}

allprojects {
    repositories {
        jcenter()
        maven { url "https://newtronlabs.jfrog.io/artifactory/libs-release-local"
            metadataSources {
                artifact()
            }
        }
    }
}

subprojects {
    apply plugin: 'com.newtronlabs.android'
}
```

In the `build.gradle` for your app include:

```gradle
dependencies {
    compileOnly 'com.newtronlabs.easyscreenshot:easyscreenshot:2.0.0'
}
```

### Step 2

Sample on how to use it.

```java
public class MainActivity extends AppCompatActivity implements ICaptureListener
{
    private static final String TAG = "EasyScreenshot";

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        
        ScreenshotAdapter.getInstance().capture(this, this);
    }

    @Override
    public void onResult(@Result int result, Bitmap bitmap)
    {
        if(result == Result.FAILED)
        {
            Log.d(TAG, "Failed");
            return;
        }

        Log.d(TAG, "Succeeded");

        boolean res = ScreenshotAdapter.getInstance().saveToFolder(bitmap, "Screenshots", "MyScreenshot");   
    }
}
```

---

## License
https://gist.github.com/NewtronLabs/216f45db2339e0bc638e7c14a6af9cc8

## Contact

solutions@newtronlabs.com
