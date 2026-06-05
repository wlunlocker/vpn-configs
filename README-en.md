<p align="center">
  <img src="assets/logo.png" width="400">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active-blue?style=for-the-badge&logo=statuspage">
  <img src="https://img.shields.io/github/last-commit/wlunlocker/vpn-configs?style=for-the-badge&logo=git">
  <img src="https://img.shields.io/badge/Available_on-GitHub-orange?style=for-the-badge&logo=github">
  <img src="https://img.shields.io/badge/Keys_Count-1500+-purple?style=for-the-badge&logo=keybase">
  <img src="https://img.shields.io/badge/Update-Every_15_min-red?style=for-the-badge&logo=clockify">
</p>

## 📌 About the project

An automated generator of clean, verified, and stable subscriptions for bypassing network restrictions. The scripts aggregate over 1,500 keys, categorize them, and ensure moderation.

> 🛡️ **Key Feature:** All configurations undergo a **Proxy GET-Test**. No randomness, and a minimal number of servers with **"N/A" (No Data)**. Only nodes that successfully respond to an HTTP GET-request via a TLS-connection with a response speed of under 1000ms make it into the lists. There is an intuitive website: wlunlocker.github.io.

---

## 🗂️ Available Subscriptions

| Subscription Type | Description | RAW Link (Copy) |
| --- | --- | --- |
| 🌐🏳️ **WHITELIST ALL** | Full set of whitelists (CIDR + SNI) for selective bypassing in Russia | `[https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_all.txt](https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_all.txt)` |
| 🌐🏴 **BLACKLIST ALL** | Full set of blacklists to route all traffic through foreign servers | `[https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/blacklist_all.txt](https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/blacklist_all.txt)` |
| 🏳️ **WHITELIST CIDR 1 RU** | First part of configs filtered by IP address ranges for Russia | `[https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_cidr1_ru.txt](https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_cidr1_ru.txt)` |
| 🏳️ **WHITELIST CIDR 2 RU** | Second part of configs filtered by IP address ranges for Russia | `[https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_cidr2_ru.txt](https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_cidr2_ru.txt)` |
| 🏳️ **WHITELIST CIDR 3 EU** | European IP ranges for stable access to foreign services | `[https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_cidr3_eu.txt](https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_cidr3_eu.txt)` |
| 🏳️ **WHITE SNI RU** | Configs filtered by SNI domains for bypassing domain-based blocks | `[https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/white_sni_ru.txt](https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/white_sni_ru.txt)` |
| 🏴 **BLACKLIST VPN 1** | Blacklists for mobile networks, resistant to TSPU interference | `[https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/blacklist_vpn1.txt](https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/blacklist_vpn1.txt)` |
| 🏴 **BLACKLIST VPN 2** | Standard blacklists for PC and home routers | `[https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/blacklist_vpn2.txt](https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/blacklist_vpn2.txt)` |

---

## 🚀 Supported Protocols

The automation scripts process, deduplicate, and test the following proxy types:

* **VLESS** (including XTLS, Reality, gRPC) for HTTPS traffic masking.
* **VMess** for classic encrypted connections.
* **Trojan** for web-server mimicry.
* **Shadowsocks** for high-speed basic traffic handling.

---

## 📖 Setup Guide (Example: HAPP)

1. Copy the required link from the table above.
2. Open your client application (HAPP or similar) on your device.
3. Tap the **Three dots** icon in the top right corner.
4. Select **Import from clipboard**.
5. Done. To ensure stability, update your subscription regularly using the **Update** button.

---

## ⚙️ How Automation Works

Data sources are updated via the following algorithm:

1. **GitHub Actions** run on a schedule, fetching raw sources, sorting keys into separate files, and filtering out duplicates and invalid lines.
2. **A local checker** on a dedicated host runs `git pull` every 15 minutes, retrieves the updated files, and tests each node via a secure TLS connection. Servers that fail the GET-request or exceed the timeout are removed. Modified configurations are then automatically pushed back to the repository via `git push`.

---

## 📋 Configuration Sources

**VPN #1 (VLESS):**

* BLACK_VLESS_RUS_mobile.txt - [https://raw.githubusercontent.com/igareck/vpn-configs-for-russia/refs/heads/main/BLACK_VLESS_RUS_mobile.txt](https://www.google.com/search?q=https%3A%2F%2Fraw.githubusercontent.com%2Figareck%2Fvpn-configs-for-russia%2Frefs%2Fheads%2Fmain%2FBLACK_VLESS_RUS_mobile.txt)
* BLACK_VLESS_RUS.txt - [https://raw.githubusercontent.com/igareck/vpn-configs-for-russia/refs/heads/main/BLACK_VLESS_RUS.txt](https://www.google.com/search?q=https%3A%2F%2Fraw.githubusercontent.com%2Figareck%2Fvpn-configs-for-russia%2Frefs%2Fheads%2Fmain%2FBLACK_VLESS_RUS.txt)
* WangCai - [https://shz.al/~WangCai](https://www.google.com/search?q=https%3A%2F%2Fshz.al%2F%7EWangCai)

**VPN #2 (SS + Hysteria2):**

* BLACK_SS+All_RUS.txt - [https://raw.githubusercontent.com/igareck/vpn-configs-for-russia/refs/heads/main/BLACK_SS%2BAll_RUS.txt](https://www.google.com/search?q=https%3A%2F%2Fraw.githubusercontent.com%2Figareck%2Fvpn-configs-for-russia%2Frefs%2Fheads%2Fmain%2FBLACK_SS%252BAll_RUS.txt)
* FreeProxyList (mirror) - [https://raw.githubusercontent.com/nikita29a/FreeProxyList/refs/heads/main/mirror/1.txt](https://www.google.com/search?q=https%3A%2F%2Fraw.githubusercontent.com%2Fnikita29a%2FFreeProxyList%2Frefs%2Fheads%2Fmain%2Fmirror%2F1.txt)

**Whitelist (CIDR & SNI):**

* WHITE-SNI-RU-all.txt - [https://raw.githubusercontent.com/igareck/vpn-configs-for-russia/refs/heads/main/WHITE-SNI-RU-all.txt](https://www.google.com/search?q=https%3A%2F%2Fraw.githubusercontent.com%2Figareck%2Fvpn-configs-for-russia%2Frefs%2Fheads%2Fmain%2FWHITE-SNI-RU-all.txt)
* ByeWhiteLists2 - [https://raw.githubusercontent.com/ByeWhiteLists/ByeWhiteLists2/refs/heads/main/ByeWhiteLists2.txt](https://www.google.com/search?q=https%3A%2F%2Fraw.githubusercontent.com%2FByeWhiteLists%2FByeWhiteLists2%2Frefs%2Fheads%2Fmain%2FByeWhiteLists2.txt)

---

## ❗ Disclaimer:

The author of this repository acts solely as an aggregator of publicly available configurations and assumes no responsibility for the security, confidentiality, or privacy of your personal data. All servers listed belong to third parties; the use of these resources is at your own risk. Please exercise caution when transmitting sensitive information through third-party VPN nodes.
