# Easy Screenshot

The easy way to take screenshots of your application programmatically.

---

## How to Use 

### Step 1

Include the below dependency in your `build.gradle` project.

```gradle
allprojects {
    repositories {
        jcenter()
        maven { url "http://code.newtronlabs.com:8081/artifactory/libs-release-local" }
    }
}
```

In the `build.gradle` for your app include:

```gradle
compile 'com.newtronlabs.easyscreenshot:easyscreenshot:0.0.1'
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

Easy Screenshot binaries and source code can only be used in accordance with Freeware license. That is, freeware may be used without payment, but may not be modified. The developer of Easy Screenshot retains all rights to change, alter, adapt, and/or distribute the software. Easy Screenshot is not liable for any damages and/or losses incurred during the use of Easy Screenshot.

You may not decompile, reverse engineer, pull apart, or otherwise attempt to dissect the source code, algorithm, technique or other information from the binary code of Easy Screenshot unless it is authorized by existing applicable law and only to the extent authorized by such law. In the event that such a law applies, user may only attempt the foregoing if: (1) user has contacted Newtron Labs to request such information and Newtron Labs has failed to respond in a reasonable time, or (2) reverse engineering is strictly necessary to obtain such information and Newtron Labs has failed to reply. Any information obtained by user from Newtron Labs may be used only in accordance to the terms agreed upon by Newtron Labs and in adherence to Newtron Labs confidentiality policy. Such information supplied by Newtron Labs and received by user shall not be disclosed to a third party or used to create a software substantially similar to the technique or expression of the Newtron Labs Easy Screenshot software.

You are solely responsible for determining the appropriateness of using Easy Screenshot and assume any risks associated with Your use of Easy Screenshot. In no event and under no legal theory, whether in tort (including negligence), contract, or otherwise, unless required by applicable law (such as deliberate and grossly negligent acts) or agreed to in writing, shall Newtron Labs be liable to You for damages, including any direct, indirect, special, incidental, or consequential damages of any character arising as a result of this License or out of the use or inability to use the Easy Screenshot (including but not limited to damages for loss of goodwill, work stoppage, computer failure or malfunction, or any and all other commercial damages or losses), even if Newtron Labs has been advised of the possibility of such damages. 

## Contact

contact@newtronlabs.com
