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
