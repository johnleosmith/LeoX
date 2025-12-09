# Modified Whatsapp-API
<p align='center'>
  <img src="https://files.catbox.moe/wafkql.jpg" width="172">
</p>

--- 

## Usage
```json
"depencies": {
  "@whiskeysockets/baileys": "github:johnleosmith/LeoX"
}
```
## Import
```javascript
const {
  default:makeWASocket,
  // Other Options 
} = require('@whiskeysockets/baileys');
```

---
# How To Connect To Whatsapp
## With QR Code
```javascript
const {
  default: makeWASocket
} = require('@whiskeysockets/baileys');

const client = makeWASocket({
  browser: ['Ubuntu', 'Chrome', '20.00.1'],
  printQRInTerminal: true
})
```

## Connect With Number
```javascript
const {
  default: makeWASocket,
  fetchLatestWAWebVersion
} = require('@whiskeysockets/baileys');

const client = makeWASocket({
  browser: ['Ubuntu', 'Chrome', '20.00.1'],
  printQRInTerminal: false,
  version: fetchLatestWAWebVersion()
  // Other options
});

const number = "234XXXXX";
const code = await client.requestPairingCode(number.trim) /* Use : (number, "YYYYYYYY") for custom-pairing */

console.log("Ur pairing code : " + code)
```

# Sending messages

## send orderMessage
```javascript
const fs = require('fs');
const LeoImg = fs.readFileSync('./LeoImage');

await client.sendMessage(m.chat, {
  thumbnail: LeoImg,
  message: "Gotta get a grip",
  orderTitle: "JohnleoSmith",
  totalAmount1000: 100000,
  totalCurrencyCode: "NGN"
}, { quoted:m })
```

## send pollResultSnapshotMessage
```javascript
await client.sendMessage(m.chat, {
  pollResultMessage: {
    name: "JohnleoSmith",
    options: [
      {
        optionName: "poll 1"
      },
      {
        optionName: "poll 2"
      }
    ],
    newsletter: {
      newsletterName: "JohnleoSmith",
      newsletterJid: "1@newsletter"
    }
  }
})
```

## send productMessage
```javascript
await client.relayMessage(m.chat, {
  productMessage {
    title: "JohnleoSmith.js",
    description: "XinvasionX...",
    thumbnail: { url: "./LeoImg" },
    productId: "EXAMPLE_TOKEN",
    retailerId: "EXAMPLE_RETAILER_ID",
    url: "https://t.me/johnleosm1th",
    body: "XinvasionX",
    footer: "JohnleoSmith",
    buttons: [
      {
        name: "cta_url",
        buttonParamsJson: "{\"display_text\":\"JohnleoSmith.js\",\"url\":\"https://t.me/johnleosm1th\"}"
      }
    ],
    priceAmount1000: 100000,
    currencyCode: "NGN"
  }
})
```
Follow https://t.me/johnleosmithch to get updates
