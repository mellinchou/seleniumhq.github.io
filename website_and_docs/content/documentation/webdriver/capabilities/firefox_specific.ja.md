---
title: "Firefoxー固有の機能"
linkTitle: "Firefoxー固有の機能"
weight: 3
---

## `FirefoxOptions` を使用してCapabilitiesを定義する

`FirefoxOptions` は、Firefoxブラウザの機能を定義する新しい方法であり、通常はDesiredCapabilitiesよりも優先して使用する必要があります。

{{< tabpane langEqualsHeader=true >}}
  {{< tab header="Java" >}}
FirefoxOptions options = new FirefoxOptions();
options.addPreference("network.proxy.type", 0);
driver = new RemoteWebDriver(options);
  {{< /tab >}}
  {{< tab header="Python" >}}
from selenium.webdriver.firefox.options import Options
options = Options()
options.headless = True
driver = webdriver.Firefox(options=options)
  {{< /tab >}}
  {{< tab header="CSharp" >}}
var options = new FirefoxOptions();
options.Proxy.Kind = ProxyKind.Direct;
var driver = new FirefoxDriver(options);
  {{< /tab >}}
  {{< tab header="Ruby" >}}
require 'selenium-webdriver'
opts = Selenium::WebDriver::Firefox::Options.new(args: ['-headless'])
driver = Selenium::WebDriver.for(:firefox, options: opts)
  {{< /tab >}}
  {{< tab header="JavaScript" >}}
const { Builder } = require("selenium-webdriver");
const firefox = require('selenium-webdriver/firefox');

const options = new firefox.Options();
options.headless();
const driver = new Builder()
    .forBrowser('firefox')
    .setFirefoxOptions(options)
    .build();
  {{< /tab >}}
  {{< tab header="Kotlin" >}}
val options = new FirefoxOptions()
options.addPreference("network.proxy.type", 0)
driver = RemoteWebDriver(options)
  {{< /tab >}}
{{< /tabpane >}}
