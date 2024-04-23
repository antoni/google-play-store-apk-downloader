## Build

```console
   pushd internal/play
   go build -o ../../build/google-play-apk-downloader
   popd
```

## tool examples

[sign in](//accounts.google.com/embedded/setup/v2/android) with your Google
Account. then get authorization code (`oauth_token`) cookie from
[browser&nbsp;storage][1]. should be valid for 10 minutes. then exchange
authorization code for refresh token (`aas_et`):

```
play -o oauth2_4/0Adeu5B...
```

[1]: //firefox-source-docs.mozilla.org/devtools-user/storage_inspector

create a file containing `X-DFE-Device-ID` (GSF ID) for future requests:

```
play -d
```

get app details:

```
> play -i com.google.android.youtube
details[6] = Google LLC
details[8] = 0 USD
details[13][1][4] = 19.13.36
details[13][1][16] = Apr 3, 2024
details[13][1][17] = APK APK APK APK
details[13][1][82][1][1] = 8.0 and up
downloads = 16.09 billion
name = YouTube
size = 112.04 megabyte
version code = 1545332160
```

acquire app. only needs to be done once per Google account:

```
play -i com.google.android.youtube -a
```

download APK. you need to specify any valid version code. the latest code is
provided by the previous details command. if APK is split, all pieces will be
downloaded:

```
play -i com.google.android.youtube -v 1540222400
```

## goals

1. [Pixel 6](//wikipedia.org/wiki/Pixel_6) (2021)
2. [Android 12](//wikipedia.org/wiki/Android_12) (2021)
3. [Google Play](//wikipedia.org/wiki/Google_Play) 29 (2022)

non goals:

email/password login. up to Android 4.4 (2013), the login is protected with TLS
fingerprinting, which is difficult but possible to bypass. since Android 5
(2014), Google uses bot-guard via JavaScript to protect the login. I do not
know how to reverse that, and I did not find any implementations online.

## support

because of repeated abuse, as of november 5 2023, I no longer offer free
discussion of this software. so unless you have paid up front, do not:

1. post an issue
2. post a pull request
3. message me on Discord
4. email me

software is not licensed for commercial use. if you wish to purchase a
commercial license, contact me.

<dl>
   <dt>email</dt>
      <dd>srpen6@gmail.com</dd>
   <dt>Discord</dt>
      <dd>srpen6</dd>
      <dd>https://discord.com/invite/WWq6rFb8Rf</dd>
   <dt>PayPal</dt>
      <dd>https://paypal.com/donate?hosted_button_id=UEJBQQTU3VYDY</dd>
   <dt>Ethereum</dt>
      <dd>0xB614Ff822c8Df557dd4714f80Cd280Bc3887390F</dd>
   <dt>Tether</dt>
      <dd>0xfcF0b126A22f08881ccD7473439762A42201b77F</dd>
</dl>
