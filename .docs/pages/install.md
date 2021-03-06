# Installation

## Basic setup
<br>
#### 1. Install the plugin from NPM

```shell
npm i -S capacitor-stripe
```
<br>

#### 2. Import from @capacitor/core
```ts
import { Plugins } from '@capacitor/core';

const { Stripe } = Plugins;
```

<br><br>

## Android Setup

<br>

#### Requirements
To use this plugin with your Android application, you must have Android X enabled. At this time Android X is not used
by `@capacitor/android` (see [this PR](https://github.com/ionic-team/capacitor/issues/1937) for updates). Follow the 
steps in [this comment](https://github.com/zyra/capacitor-stripe/issues/1#issuecomment-555666767) for details on how to 
enable Android X in your app.

<br>

#### Basic setup
Include the plugin in your app's `MainActivity.java` file:
```java
//
// other imports
// ...

// 1. Import Stripe plugin
import ca.zyra.capacitor.stripe.Stripe;

public class MainActivity extends BridgeActivity {
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        // Initializes the Bridge
        this.init(savedInstanceState, new ArrayList<Class<? extends Plugin>>() {{
            //
            // other plugins
            // ...

            // 2. Add Stripe plugin here
            add(Stripe.class);
        }});
    }
}
```

<br>

#### Google Pay
To enable payments using Google Pay you must add the following `<meta-data>` tag to `AndroidManifest.xml` inside the  
main `<application />` tag:
```xml
<application
  ...
  <meta-data
    android:name="com.google.android.gms.wallet.api.enabled"
    android:value="true" />
</application>
```

There is no need to add any Gradle dependencies as they are already included with this plugin.

Please review the steps outlined here for more details on [Going live with Google Pay](https://stripe.com/docs/google-pay#going-live-with-google-pay).

<br><br>

## iOS Setup
To enable payments using Apple Pay you must follow the first 3 steps in [this guide](https://stripe.com/docs/apple-pay#native):

- 1. [Register for Apple Merchant ID](https://stripe.com/docs/apple-pay#merchantid)
- 2. [Create a new Apple Pay certificate](https://stripe.com/docs/apple-pay#csr)
- 3. [Integrate with Xcode](https://stripe.com/docs/apple-pay#setup)

 

