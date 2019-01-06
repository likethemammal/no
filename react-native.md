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
