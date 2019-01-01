Debugging:

## Running Emulators from cmd line

If you only have one virtual device for your emulator to launch, you can launch the emulator with a single command like so:

```
emulator -avd $(emulator -list-avds)
```

## Dealing with KVM user permissions issue

If you run into the KVM permission issue for /dev/kvm run the command from [this answer](https://stackoverflow.com/a/50287739/2687479)

```
sudo chown username -R /dev/kvm
```
