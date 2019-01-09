Debugging:

## Running Emulators from cmd line

If you only have one virtual device for your emulator to launch, you can launch the emulator with a single command like so:

```
emulator -avd $(emulator -list-avds)
```

## Dealing with KVM user permissions issue

```

emulator: ERROR: x86 emulation currently requires hardware acceleration!
Please ensure KVM is properly installed and usable.
CPU acceleration status: This user doesn't have permissions to use KVM (/dev/kvm)

```

If you run into the KVM permission issue for /dev/kvm run the command from [this answer](https://stackoverflow.com/a/50287739/2687479)

```
sudo chown username -R /dev/kvm
```

##### Complete command with emulator startup:

```
sudo chown username -R /dev/kvm; emulator -avd $(emulator -list-avds)
```

## react-native run-android issues


### gradle download issue (bintray / maven issue)

Add `google()` and new maven url to `android/build.gradle`

```
buildscript {
    repositories {
        jcenter()
        google()
        maven {   url "https://maven.google.com"  }
     }
    dependencies {
        classpath 'com.android.tools.build:gradle:2.2.3'

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

```

### gradle download issue

```
...
Downloading https://services.gradle.org/distributions/gradle-3.3-bin.zip     

Exception in thread "main" javax.net.ssl.SSLException: java.lang.RuntimeException: Unexpected error: java.security.InvalidAlgorithmParameterException: the trustAnchors parameter must be non-empty
        at java.base/sun.security.ssl.Alerts.getSSLException(Alerts.java:214)                                                                             
        at java.base/sun.security.ssl.SSLSocketImpl.fatal(SSLSocketImpl.java:1969)                                                                        
...
```

If you get this issue, follow the answers in this thread:

https://github.com/mesosphere/hdfs-deprecated/issues/141

Basically by removing the `s` from `https` in the `distributionUrl` value in gradle/wrapper/gradle-wrapper.properties.

### Could not determine java version from x.x.x

```
Building and installing the app on the device (cd android && ./gradlew installDebug)...

FAILURE: Build failed with an exception.

* What went wrong:
Could not determine java version from '10.0.1'.
...
```

Follow this answer in stackoverflow by updating the `distributionUrl` to an updated version of gradle: https://stackoverflow.com/a/46867575/2687479

Make sure to keep it `http` not `https` if the previous SSL issue occured.

# Styling:

## Full Width Image

```
<View 
  style={{
    flex:1,
    flexDirection: 'row'
  }}
>
  <Image
    resizeMode='contain'
    style={{
      flex:1,
      width:null,
      height:null
    }}
    source={...}
  />
</View>
```

Use `contain` or `cover` to stretch Image component to full width.

https://github.com/facebook/react-native/issues/950#issuecomment-315845328

## display: inline/inline-block equivalent

```
const styles = StyleSheet.create({
   item: {
     flexDirection: 'row', 
     alignSelf: 'flex-start'
   }
})
```

https://stackoverflow.com/a/49263706/2687479

## Vertical Align child

```
const styles = StyleSheet.create({
   container: {
      justifyContent: 'center',
   }
})

```

https://stackoverflow.com/a/44338089/2687479
