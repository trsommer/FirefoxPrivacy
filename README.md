# Firefox privacy guide

## Installation

#### 1. Install Firefox

https://www.mozilla.org/de/firefox/download/thanks/

#### 2. Install Addons

##### 1. Needed Addons

- uBlock Origin - https://addons.mozilla.org/en-US/firefox/addon/sponsorblock
- I don't care about Cookies - https://addons.mozilla.org/en-US/firefox/addon/i-dont-care-about-cookies
- SponsorBlock - https://addons.mozilla.org/en-US/firefox/addon/sponsorblock
- LocalCDN - https://addons.mozilla.org/en-US/firefox/addon/localcdn-fork-of-decentraleyes
- Privacy Badger - https://addons.mozilla.org/en-US/firefox/addon/privacy-badger17
- Bitwarden - https://addons.mozilla.org/en-US/firefox/addon/bitwarden-password-manager

##### 2. Optional Addons

- Cookie AutoDelete - https://addons.mozilla.org/en-US/firefox/addon/cookie-autodelete
- ClearURLs - https://addons.mozilla.org/en-US/firefox/addon/clearurls
- Chameleon - https://addons.mozilla.org/en-US/firefox/addon/chameleon-ext

## Configuration

### 1. Preferences

##### General / Startup

```bash
Restore previous session  - false
```

##### General / Firefox Updates

```bash
Allow Firefox to  - Check for updates but let you choose to install them
```

##### Search / Default Search Engine

Delete all other search engines

```bash
DuckDuckGo
```

##### Privacy & Security / Enhanced Tracking Protection

if you have Chameleon, you don't need this

```bash
Restore previous session  - false
```

```bash
Send websites a “Do Not Track” signal that you don’t want to be tracked - true
```

##### Privacy & Security / Cookies and Site Data

```bash
Delete cookies and site data when Firefox is closed  - true
```

##### Privacy & Security / Logins and Passwords

```bash
Ask to save logins and passwords for websites  - false
```

##### Privacy & Security / History

```bash
Clear history when Firefox closes  - true //optional
```

##### Privacy & Security / History

```
Browsing history - false
Bookmarks - false
Open tabs - false
Shortcuts - false
Search engines - false
```

##### Privacy & Security / Permissions

```
Block new requests asking to access your location - true
Block new requests asking to access your camera - true
Block new requests asking to access your microphone - true
Block new requests asking to allow notifications - true
Block new requests asking to access your virtual reality devices - true
```

```
Block pop-up windows - true
```

```
Warn you when websites try to install add-ons - true
```

##### Privacy & Security / Firefox Data Collection and Use

```
Allow Firefox to send technical and interaction data to Mozilla - false
```

```
Allow Firefox to send backlogged crash reports on your behalf - false
```

##### Privacy & Security / Security

```
Block dangerous and deceptive content - false
```

##### Privacy & Security / Certificates

```
Query OCSP responder servers to confirm the current validity of certificates - true
```

##### Privacy & Security / HTTPS-Only Mode

```
Enable HTTPS-Only Mode in all windows - true
```



### 2. Config

type **about:config** in the addess bar

search for the setting and change it to the provided value:

Forces every window into private browsing mode. No data will be saved

```
browser.privatebrowsing.autostart = true
```

This prevents Firefox from writing data to your local storage

```
browser.cache.disk.enable = false
browser.cache.offline.enable = false
```

Prevents Firefox from predicting your search

```
browser.urlbar.speculativeConnect.enabled = false
browser.search.suggest.enabled = false
```

Prevents Firefox from predicting what resources pages may need

```
network.predictor.enabled = false
network.prefetch-next = false
network.dns.disablePrefetch = true
```

Prevents Firefox from sending the "HTTP referer Header" - other websites wont know the website you came from: You can spoof this header with Cameleon (set to 1 for spoofing)

```
network.http.referer.XOriginPolicy = 0
```

Disables interfaces for things like public wifis

```
network.captive-portal-service.enabled = false
```

Prevent other websites from seeing other websites data and cookies

```
privacy.firstparty.isolate = true
```

Disables WebRTC. This can be used to track you even if you use a VPN

```
media.peerconnection.enabled = false
```

Prevents Geolocation tracking

```
geo.enabled = false
```

Prevents WebGL Hash fingerprinting

```
webgl.disabled = true
```

Prevents Canvas signature fingerprinting

```
privacy.resistFingerprinting = true
```

You dont need this. Use uBlock origin instead

```
privacy.trackingprotection = false
```

Prevents all types of internal Firefox telemetry

```
toolkit.telemetry.unified = false
```

Unnecessary Firefox features

```
extensions.pocket.enabled = false
extensions.screenshots.disabled = false
extensions.webcompat-reporter.enabled = false
identity.fxaccounts.enabled = false
media.gmp-- = false
```

Prevents Firefox from blocking websites google deems "unsafe"

```
browser.safebrowsing.malware.enabled = false
browser.safebrowsing.phishing.enabled = false
browser.safebrowsing.downloads.enabled = false
```

Optional

If you want to be sure that Firefox does not request security updates from google

```
browser.safebrowsing.provider.mozilla.gethashURL = ""
browser.safebrowsing.provider.mozilla.updateURL = ""
```



### 3. Addons

- #### Bitwarden

  - Turn on "Two-step Login in settings"
  - Turn on "Enable Auto-fill On Page Load" - its in settings/options at the bottom

  

- #### uBlock origin

  #####  Main settings

  ```
  Hide placeholders of blocked elements = true
  I am an advanced user = true
  ```

  ###### Privacy

  Improves privacy - look at "i" for more info

  ```
  Disable pre-fetching = true
  Disable hyperlink auditing = true 
  Prevent WebRTC from leaking local IP addresses = true
  Block CSP reports = true 
  Uncloak canonical names = true
  ```

  ###### Default behavior

  prevents remote font tracking by blocking fonts not stored on the websites server

  ```
  Block remote fonts = true
  ```

  ##### Filter Lists

  default is pretty good already. If you feel you need more, turn on the filter lists you deem necessary 

  

- #### Cookie AutoDelete

  ##### Automatic Cleaning Options

  ```
  Enable Automatic Cleaning = true
  Enable Cleanup on Domain Change = true
  Enable Greylist Cleanup on Browser Restart = true
  Clean Cookies and other Site Data from Open Tabs on Startup = true
  Clean All Expired Cookies = true
  ```

  ##### Other Browsing Data Cleanup Options

  ```
  Enable Cache Cleanup (Firefox 78+, Chrome 74+) = true
  Enable IndexedDB Cleanup (Firefox 77+, Chrome 74+) = true
  Enable LocalStorage Cleanup (Firefox 58+, Chrome 74+) = true
  Enable Plugin Data Cleanup (Firefox 78+, Chrome 74+) = true
  Enable Service Workers Cleanup (Firefox 77+, Chrome 74+) = true
  ```

  ##### Extension Options

  ```
  Enable Support for Container Tabs = true
  ```

- #### Chameleon

  ##### Profile

  ```
  Random Profile (Desktop) = true
  Change periodically = Every 10 minutes
  ```

  ##### Headers

  ```
  Prevent Etag tracking = true
  Spoof Accept Language = English
  Spoof X-Forwarded-For/Via IP = Random IP
  Disable referer = true
  ```

  ##### Options

  - ###### Injection

    ```
    Block media devices = true
    Block CSS Exfil = true
    Limit tab history = true
    Protect keyboard fingerprint = true
    Protect window name = true
    Spoof audio context = true
    Spoof client rects = true
    Spoof font fingerprint = true
    Screen Size = 1920x1080
    Timezone = select your timezone with a city not in your country 
    (e.g. (+01:00) Europe/Bratislava if you are in Germany)
    ```

  - ###### Standart

    ```
    Enable 1st party isolation = true
    Enable resist fingerprinting = true
    Disable WebRTC = true // this is not necessary bc. we already set it in the config
    Tracking protection mode = on
    Websockets = block all
    ```

  - ###### Cookie

    ```
    Policy = Allow all //we control cookies with Cookie autodelete 
    ```
