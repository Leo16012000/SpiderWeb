Go to homepage, coupon
deadline 16/8
live 30/8
universal link
# Q & A
deeplink what for? **navigation**
deeplink types? **5 types: scheme, chrome intent, Universal, App, Defered**
universal link what is? **for ios, could redirect to install app**
what is currently problem? **only impl with custom scheme, which could not redirect if the app has not installed yet**
use where? **main, community, store, lounge pages**
what info need to create one? **country, language**
flow? **simple flow, install app if it has not installed yet, launch app, navigate on app to where user was on web**
condition when navigate? **keep login state(SSO)**
<mark style="background: #FF5582A6;">could we impl defered?</mark>
<mark style="background: #FF5582A6;">why it's hard? </mark>
function expose for schemes(wiki doc)? 
how value send? parameter or anyway else? need to clarify for each case!
defer what for? **after install app, it will navigate to exactly destination (but even when logon or not?)**
How to define Ipad as mobile devices? 
[[2024-07-22]]
**chrome intents**: use for android only
```
intent://example.com/view#Intent;scheme=https;package=com.example.app;S.browser_fallback_url=https://www.example.com/view;end
```
**universal link**: apple, `apple-app-site-association.json`, 
```json
{
  "applinks": {
    "apps": [],
    "details": [
      {
        "appID": "TEAMID.com.example.app",
        "paths": [ "/path/to/content/*" ]
      }
    ]
  }
}

```

trong AppDelegate
```swift
func application(_ application: UIApplication, continue userActivity: NSUserActivity, restorationHandler: @escaping ([UIUserActivityRestoring]?) -> Void) -> Bool {
    if userActivity.activityType == NSUserActivityTypeBrowsingWeb {
        if let url = userActivity.webpageURL {
            // Xử lý URL tại đây
            handleUniversalLink(url)
        }
    }
    return true
}
```
**android app** link: `assetlinks.json`
```json
[
  {
    "relation": ["delegate_permission/common.handle_all_urls"],
    "target": {
      "namespace": "android_app",
      "package_name": "com.example.app",
      "sha256_cert_fingerprints": [
        "AA:BB:CC:DD:EE:FF:00:11:22:33:44:55:66:77:88:99:AA:BB:CC:DD:EE:FF:00:11:22:33:44:55:66:77:88:99"
      ]
    }
  }
]

```
why use echo framework? compare with gin?
[[2024-07-31]]
schema problems? 
```
 scheme://host:port/path?query=xxxxxxx
 -> specified page you want to jump to
 -> query params need when reachi
```