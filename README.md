# Xcode Notarization Action

This action invokes `xcrun notarytool` to send your app to Apple's notary service.

## Usage

```yaml
runs-on: macos-latest
steps:
  uses: cocoalibs/xcode-notarization-action@v1
  with:
    app-path: 'MyApp-*.dmg'
    apple-id: ${{ secrets.APPLE_ID }}
    password: ${{ secrets.PASSWORD }}
    team-id: ${{ secrets.TEAM_ID }}
    # Further Parameters:
    staple: 'false' # if you wish to skip running stapler
    keychain-profile: 'my-keychain-profile' # custom name for --keychain-profile
    xcode-path: '/Applications/Xcode_13.3.app' # defaults to /Applications/Xcode_13.2.app
```