# Build Guide
## Clone repository
```bash
# Clone repository
git clone git@github.com:digitamizers/techforce-ide-extension.git

# Checkout development branch
git checkout development
```

## Install Dependencies
:::caution Use **`yarn`**
Building extension may throw errors when using `npm` or `pnpm`
:::

```bash
yarn install
```

## Build Extension
Extension will be built in `development` or `production` mode depending on **`NODE_ENV`** environment variable value.
```bash
# ENVs configurable when building extension
NODE_ENV=   # "development" | "production"
SUPER_API=
SSO_URL=
CMS_URL=
```
After configuring above envs, run
```bash
yarn compile
```

This outputs extension in **`dist`** directory.

## Load extension in browser

### Chrome
1. Open [chrome://extensions](chrome://extensions). *You will have to open it by pasting it in URL bar.*
2. Enable `Developer mode`
3. Click `Load unpacked`
4. In opened file dialog, select **`dist`** directory.


## Build Native Messaging Host
Running
```bash
yarn compile-nmh
```
will output `messaging_host.exe` under `build/src/messaging_host` directory.

For loading it, give absolute location of `build/src/messaging_host/manifest.json` file in Windows Registry as suggested [here](https://developer.chrome.com/docs/apps/nativeMessaging/#native-messaging-host-location).


```powershell
REG ADD "HKCU\Software\Google\Chrome\NativeMessagingHosts\com.techforce.chrome_extension" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
```

