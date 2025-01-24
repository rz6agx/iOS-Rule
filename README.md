# iOS-Rule
This repository contains various rule sets for **ShadowRocket** and other proxy tools, designed to help bypass censorship and improve internet access on iOS devices. The rule sets are configured for services like **Google Gemini**, **YouTube**, and other commonly blocked resources.

## How to Use
To use the rules in ShadowRocket, you need to add the raw URL of the list files directly into the application settings. ShadowRocket requires raw URLs to correctly fetch and update rule sets from GitHub.

### Example of using the rules:
1. Open **ShadowRocket** on your iOS device.
2. Go to **Configuration** > **Rule Sets**.
3. Add the raw URL of the rule file you want to use (such as the Gemini.list or YouTube.list) in the following format:

  - **Gemini rule list**:
  ```https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/Gemini.list```

  - **YouTube rule list**:
  ```https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/YouTube.list```

4. Make sure the URL is in the **raw format** (it should start with https://raw.githubusercontent.com/ and end with .list).
5. **Important**: In your **ShadowRocket** configuration, make sure the last rule is ```DIRECT```. This rule ensures that all other domains that are **not listed in the rule sets** will bypass the proxy and go directly through your regular internet connection. Only domains included in the rule sets will be routed through the proxy.

### Example of Configuration:
Here’s an example configuration for ShadowRocket:
```
RULE-SET, https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/Gemini.list, PROXY
RULE-SET, https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/YouTube.list, PROXY
FINAL, DIRECT
```


### Why use the raw URL?
**ShadowRocket** requires raw URLs because they provide plain text files without the HTML formatting, which is necessary for the app to parse and use the rule lists properly. If you use the regular GitHub URL (e.g., https://github.com/rz6agx/iOS-Rule/blob/main/Gemini.list), ShadowRocket will not be able to correctly load the rules, as it will fetch an HTML page instead of the raw text file.

## Available Rule Lists
- Gemini.list: Rules for bypassing censorship for Google Gemini services.
- YouTube.list: Rules for bypassing restrictions on YouTube and related services.
- Other rule sets: Additional lists will be added over time.

## Example Configuration File
We have prepared a complete configuration file (`example.conf`) for ShadowRocket, which includes multiple rule sets and general settings. You can use this file as a template for your own configuration.

### Content of `example.conf`:
```conf
[General]
ipv6 = false
bypass-system = true
skip-proxy = 192.168.0.0/16, 10.0.0.0/8, 172.16.0.0/12, localhost, *.local
bypass-tun = 192.168.0.0/16, 10.0.0.0/8, 172.16.0.0/12, localhost, *.local
dns-server = 77.88.8.8, 77.88.8.1

[Rule]
RULE-SET,https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/domain_custom.list,PROXY
RULE-SET,https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/Copilot.list,PROXY
RULE-SET,https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/Instagram.list,PROXY
RULE-SET,https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/OpenAI.list,PROXY
RULE-SET,https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/Youtube.list,PROXY
RULE-SET,https://raw.githubusercontent.com/rz6agx/iOS-Rule/main/Gemini.list,PROXY

FINAL,DIRECT

[Host]
localhost = 127.0.0.1
```

### How to Use `example.conf`:
1. Download the [example.conf](https://raw.githubusercontent.com/rz6agx/iOS-Rule/refs/heads/main/example.conf) file from this repository.
2. Import it into ShadowRocket:
  - Open ShadowRocket.
  - Go to Configuration > Import.
  - Select the example.conf file.
3. Activate the configuration and ensure all rules are loaded correctly.

### Key Features of `example.conf`:
- General Settings:
  - Disables IPv6 (ipv6 = false).
  - Bypasses system proxy settings (bypass-system = true).
  - Skips proxy for local networks and Apple services (skip-proxy and bypass-tun).
  - Uses Yandex DNS servers (dns-server = 77.88.8.8, 77.88.8.1).

- Rule Sets:
  - Loads multiple rule sets from this repository (e.g., domain_custom.list, Copilot.list, Instagram.list, etc.).
  - Routes traffic for specified domains through the proxy (PROXY).
  - Ensures all other traffic goes directly (FINAL,DIRECT).

- Host Settings:
  - Maps localhost to 127.0.0.1.

## Special Thanks
We would like to extend our special thanks to GitHub user **[blackmatrix7](https://github.com/blackmatrix7)** for their incredible work on the rule lists available at [ios_rule_script](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule). Their contributions have been invaluable in creating and maintaining high-quality rule sets for tools like **ShadowRocket**.

### License
This repository is licensed under the MIT License. See the LICENSE file for details.
