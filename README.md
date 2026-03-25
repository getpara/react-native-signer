# React Native Signer

Pre-built native signer binary for the [Para React Native SDK](https://github.com/capsule-org/web-sdk/tree/main/packages/react-native-sdk). Distributed via [JitPack](https://jitpack.io/#getpara/react-native-signer).

## Usage

This package is consumed automatically by `@getpara/react-native-wallet`. No manual installation is needed.

The dependency is declared in the SDK's `build.gradle`:

```gradle
implementation 'com.github.getpara:react-native-signer:1.0.0@aar'
```

## Rebuilding

The `signer.aar` is compiled from the [Go SDK](https://github.com/capsule-org/go-sdk) signer package using `gomobile`. To rebuild, run the `compile-signer` script in the React Native SDK:

```bash
cd web-sdk/packages/react-native-sdk
yarn compile-signer
```

This compiles both iOS (`signer.xcframework`) and Android (`signer.aar`) binaries, and copies the aar into this repo if it is cloned alongside `web-sdk`.

## Releasing

1. Commit the updated `signer.aar`
2. Create a new GitHub release with an incremented tag (e.g., `1.1.0`)
3. Update the version in `web-sdk/packages/react-native-sdk/android/build.gradle`
