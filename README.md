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
RULE-SET, DIRECT
```

### Why use the raw URL?
**ShadowRocket** requires raw URLs because they provide plain text files without the HTML formatting, which is necessary for the app to parse and use the rule lists properly. If you use the regular GitHub URL (e.g., https://github.com/rz6agx/iOS-Rule/blob/main/Gemini.list), ShadowRocket will not be able to correctly load the rules, as it will fetch an HTML page instead of the raw text file.

## Available Rule Lists
Gemini.list: Rules for bypassing censorship for Google Gemini services.
YouTube.list: Rules for bypassing restrictions on YouTube and related services.
Other rule sets: Additional lists will be added over time.

### License
This repository is licensed under the MIT License. See the LICENSE file for details.