### Fixing Issue of LocalWP
On Mac, by default self signed SSL is set to untrusted, thus if we want our local site to use https, we need to tweak our settings

- Steps:
```
1. Press Command + Space
2. Type `Keychain Acess` & Hit enter
3. Click on `Open Keychain Access` in the popup
4. Search the site name (e.g. ghtimeline.local) in search bar
5. Double click the SSL certificate
6. Click on `Trust` dropdown
7. Set the value of `When using this certificate` to `Always Trust`
```

### Acessing AdminerEvo
Similar to PHPMyAdmin, for accessing the database, follow these steps:

- Steps:
```
1. Open LocalWP
2. Click on database tab
3. Click on `Open AdminerEvo` button
```

### Fixing Curl Issue
1. Check log file using this command:
```cat logs/php/errors.log```
2. Identify the issue by searching on stackoverflow

### Curl Issue - 1: Getting `cacert` error
- Fixed it by downloading `cacert.pem` from curl website & mentionining the path in code
- Code Snippet
```
class GitHubMonitor {
    private $apiUrl = "https://github.com/timeline";
    // I've created a folder outside public folder containing cacert.pem
    private $cacertPath = __DIR__ . '/../../certificates/cacert.pem';

    public function getUpdates() {
        $ch = curl_init();
        curl_setopt($ch, CURLOPT_URL, $this->apiUrl);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_USERAGENT, 'Mozilla/5.0');
        curl_setopt($ch, CURLOPT_CAINFO, $this->cacertPath);

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

        if (curl_errno($ch) || $httpCode != 200) {
            error_log("Curl error: " . curl_error($ch) . " with HTTP Code: " . $httpCode);
            curl_close($ch);
            return [];
        }

        curl_close($ch);
        $xml = simplexml_load_string($response, "SimpleXMLElement", LIBXML_NOCDATA);
        if ($xml === false) {
            error_log("Failed to parse XML");
            return [];
        }

        return $this->parseXmlToArray($xml);
    }
}
```
- Directory Tree
```
├── app
│   ├── DEVELOPMENT.md
│   ├── README.md
│   ├── certificates
│   │   └── cacert.pem // cert placed at here
│   ├── phpcs.xml
│   ├── public
│   │   ├── app
│   │   │   ├── Email.php
│   │   │   └── GitHubMonitor.php // File which is using curl

```

For above tree output, install `tree` using `brew install tree`

## Curl Issue 2 - Gettting 406 Error
I've removed the `Accepted-Type` Header from the Curl setting, which might have unexpected return type

