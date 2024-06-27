# Arduino-Cloudflare-DDNS-Client
A Cloudflare DDNS client on an Arduino (ESP8266)

This does DDNS (Dynamic DNS) updates on the Cloudflare API endpoint, on an Arduino (ESP8266)

* Step 1: Create the file Secrets.h and paste the following
```cpp
/* Secrets.h file should contain data as below: */
#ifndef WIFI_SSID
  #define WIFI_SSID "xxxxxxxxxx"
  #define WIFI_PASSWORD "xxxxxxxxxx"
  #define TOKEN "cloudflare-api-token" // API token from https://dash.cloudflare.com/profile/api-tokens [All zones - Zone:Read, DNS:Edit]
  #define DOMAIN "example.com" // domain name (without subdomain)
  #define SUBDOMAIN "hello" // subdomain in: hello.example.com
  #define NOTIFY_URL "https://hooks.slack.com/services/TMVF27R8B/BN0K5BWAD/xxxxxxxxxxxxx" // Slack webhook notify url
#endif
``` 
* Step 2: Fill in `EMAIL`, `TOKEN`, `DOMAIN` and `SUBDOMAIN`. Your API token is here: `https://dash.cloudflare.com/profile/api-tokens`.
  * Make sure the token is the Global token, or has these permissions: #zone:read, #dns_record:read, #dns_records:edit
* Step 3: Create an A record on Cloudflare with the subdomain you choose.
* Step 4: Compile and flash to your choice of ESP8266 board.
