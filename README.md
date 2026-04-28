# 🚀 GenLayer Delegator Node — Complete Beginner Guide

> 🇬🇧 **English** | 🇧🇩 **বাংলা** | 🇮🇳 **हिंदी**  
> **Author / লেখক / लेखक:** Mritunjoy  
> **Network / নেটওয়ার্ক / नेटवर्क:** Testnet Asimov    
> **Join Our Telegram Get more Update:** https://t.me/vaivaicrypto        
> **Official Guide:** https://github.com/genlayerlabs/genlayer-cli/blob/main/docs/delegator-guide.md

---

## 📋 Table of Contents / বিষয়সূচি / विषय सूची

1. [Prerequisites](#1-prerequisites)
2. [Install GenLayer CLI](#2-install-genlayer-cli)
3. [Create Account](#3-create-account)
4. [Download Keystore File](#4-download-keystore-file)
5. [Get Wallet Address](#5-get-wallet-address)
6. [Set Network](#6-set-network)
7. [Get 50 GEN Tokens](#7-get-50-gen-tokens)
8. [Find Active Validators](#8-find-active-validators)
9. [Join as Delegator](#9-join-as-delegator)
10. [Verify Delegation](#10-verify-delegation)
11. [Common Errors & Fixes](#11-common-errors--fixes)
12. [Important Notes](#12-important-notes)

---

## 1. Prerequisites

🇬🇧 **English:** What you need before starting:
- GitHub Codespaces account (free)
- Minimum **50 GEN** testnet tokens
- A little patience 😄

🇧🇩 **বাংলা:** শুরু করার আগে যা যা লাগবে:
- GitHub Codespaces অ্যাকাউন্ট (ফ্রি)
- ন্যূনতম **50 GEN** টেস্টনেট টোকেন
- একটু ধৈর্য 😄

🇮🇳 **हिंदी:** शुरू करने से पहले आपको क्या चाहिए:
- GitHub Codespaces अकाउंट (फ्री)
- कम से कम **50 GEN** टेस्टनेट टोकन
- थोड़ा धैर्य 😄
---

## 2. Install GenLayer CLI

🇬🇧 Run this command in your GitHub Codespaces terminal.  
🇧🇩 GitHub Codespaces terminal-এ এই command চালাও।  
🇮🇳 GitHub Codespaces terminal में यह command चलाएं।

```sudo apt update
sudo apt install nodejs npm
```

```bash
npm install -g genlayer
```

✅ **Success output:**
```
added X packages in Xs
```

> ⚠️ 🇬🇧 If npm update notice appears, run: `npm install -g npm@latest`  
> ⚠️ 🇧🇩 npm update notice আসলে চালাও: `npm install -g npm@latest`  
> ⚠️ 🇮🇳 npm update notice आए तो चलाएं: `npm install -g npm@latest`

---

## 3. Create Account

🇬🇧 Create your wallet account with a name and password.  
🇧🇩 নাম ও পাসওয়ার্ড দিয়ে তোমার ওয়ালেট অ্যাকাউন্ট তৈরি করো।  
🇮🇳 नाम और पासवर्ड के साथ अपना वॉलेट अकाउंट बनाएं।

```bash
genlayer account create --name <your-name>
```

```bash
# Example / উদাহরণ / उदाहरण:
genlayer account create --name mywallet
```

✅ **Success output:**
```
Account 'mywallet' created at: /home/codespace/.genlayer/keystores/mywallet.json
```

> 🔑 🇬🇧 Remember the password you set — you will need it later!  
> 🔑 🇧🇩 যে password দিলে সেটা মনে রেখো — পরে দরকার হবে!  
> 🔑 🇮🇳 जो password सेट किया है उसे याद रखें — बाद में जरूरत पड़ेगी!

---

## 4. Download Keystore File

🇬🇧 This file is your wallet backup. Keeping it safe is **very important.**  
🇧🇩 এই file-টা তোমার wallet-এর backup। এটা safe রাখা **অত্যন্ত জরুরি।**  
🇮🇳 यह file आपके wallet का backup है। इसे safe रखना **बहुत जरूरी है।**

**Step 4a — Copy to workspace:**
```bash
cp /home/codespace/.genlayer/keystores/mywallet.json /workspaces/Genlayer-Deligator-node/
```

**Step 4b — Verify:**
```bash
ls mywallet.json
```

**Step 4c — Download from VS Code Explorer:**

🇬🇧 Click the Files icon (📄) in the left sidebar → Right-click `mywallet.json` → Click **"Download..."** → File saves to your Mac Downloads folder ✅

🇧🇩 বাম দিকের Files icon (📄) তে click করো → `mywallet.json` এ Right-click করো → **"Download..."** তে click করো → Mac-এর Downloads folder-এ save হবে ✅

🇮🇳 बाईं तरफ Files icon (📄) पर click करें → `mywallet.json` पर Right-click करें → **"Download..."** पर click करें → Mac के Downloads folder में save होगा ✅

**Step 4d — Cleanup after download:**
```bash
rm /workspaces/Genlayer-Deligator-node/mywallet.json
```

> 🚫 🇬🇧 Never push this file to GitHub!  
> 🚫 🇧🇩 এই file কখনো GitHub-এ push করো না!  
> 🚫 🇮🇳 इस file को कभी GitHub पर push मत करें!

---

## 5. Get Wallet Address

🇬🇧 Run this to see your wallet address.  
🇧🇩 তোমার wallet address দেখতে এটা চালাও।  
🇮🇳 अपना wallet address देखने के लिए यह चलाएं।

```bash
cat /home/codespace/.genlayer/keystores/mritunjoy.json | grep -i address
```

✅ **Output:**
```json
"address": "134a796047a4828f8e6d1fa5e2b0d566a8e88***"
```

> 🇬🇧 Your full wallet address = add `0x` at the front → `0x134a796047a4828f8e6d1fa5e2b0d566a8e88***`  
> 🇧🇩 তোমার full wallet address = সামনে `0x` যোগ করো → `0x134a796047a4828f8e6d1fa5e2b0d566a8e88***`  
> 🇮🇳 आपका full wallet address = आगे `0x` जोड़ें → `0x134a796047a4828f8e6d1fa5e2b0d566a8e88***`

---

## 6. Set Network

🇬🇧 Set the network to testnet-asimov before doing anything else.  
🇧🇩 যেকোনো কিছু করার আগে network testnet-asimov-এ set করো।  
🇮🇳 कुछ भी करने से पहले network को testnet-asimov पर set करें।

```bash
genlayer network set testnet-asimov
```

✅ **Success output:**
```
Network set to testnet-asimov
```

---

## 7. Get 50 GEN Tokens

🇬🇧 Send at least **50 GEN** testnet tokens to your wallet address from Step 5. You can get tokens from the GenLayer Discord/Telegram faucet or request from the GenLayer team.

🇧🇩 Step 5-এর wallet address-এ ন্যূনতম **50 GEN** testnet token পাঠাও। GenLayer Discord/Telegram faucet থেকে নিতে পারো অথবা GenLayer team-এর কাছে request করো।

🇮🇳 Step 5 के wallet address पर कम से कम **50 GEN** testnet token भेजें। GenLayer Discord/Telegram faucet से प्राप्त करें या GenLayer team से request करें।

> ⏳ 🇬🇧 Tokens may take a few minutes to arrive.  
> ⏳ 🇧🇩 Token আসতে কয়েক মিনিট লাগতে পারে।  
> ⏳ 🇮🇳 Token आने में कुछ मिनट लग सकते हैं।

---

## 8. Find Active Validators

🇬🇧 Get the list of active validators to delegate to.  
🇧🇩 যে validator-এর কাছে delegate করবে তার list দেখো।  
🇮🇳 उन active validators की list देखें जिन्हें delegate करना है।

```bash
genlayer staking active-validators --network testnet-asimov
```

✅ **Output example:**
```
{
  validators: [
    '0x9781a9dD53665cB949A4bF330CD9f081eEb6b72D',
    '0xabCe9710bF2a3d5f1237587bA5f4894798ad7bc5',
    '0xcef2b0Fc479b61f855274A3eeb45afA6041b3eAC',
    ...
  ]
}
✔ Active validators retrieved
```

> 🇬🇧 Copy any one validator address from this list.  
> 🇧🇩 এখান থেকে যেকোনো একটা validator address copy করো।  
> 🇮🇳 इस list से कोई भी एक validator address copy करें।

---

## 9. Join as Delegator

🇬🇧 Now stake your 50 GEN with a validator.  
🇧🇩 এখন তোমার 50 GEN একটা validator-এর সাথে stake করো।  
🇮🇳 अब अपने 50 GEN को एक validator के साथ stake करें।

```bash
genlayer staking delegator-join --account mywallet --amount 50gen <VALIDATOR_ADDRESS>
```

```bash
# Example / উদাহরণ / उदाहरण:
genlayer staking delegator-join --account mywallet --amount 50gen 0x9781a9dD53665cB949A4bF330CD9f081eEb6b72D
```

> 🔑 🇬🇧 Enter the password you set in Step 3 when asked.  
> 🔑 🇧🇩 Password চাইলে Step 3-এ দেওয়া password দাও।  
> 🔑 🇮🇳 Password मांगे तो Step 3 में दिया गया password डालें।

✅ 🇬🇧 You will see a transaction hash if successful.  
✅ 🇧🇩 সফল হলে একটা transaction hash দেখাবে।  
✅ 🇮🇳 सफल होने पर एक transaction hash दिखेगा।

---

## 10. Verify Delegation

🇬🇧 Check your delegation status.  
🇧🇩 তোমার delegation status চেক করো।  
🇮🇳 अपनी delegation status check करें।

```bash
genlayer staking delegation-info <VALIDATOR_ADDRESS>
```

```bash
# Example / উদাহরণ / उदाहरण:
genlayer staking delegation-info 0x9781a9dD53665cB949A4bF330CD9f081eEb6b72D
```

✅ **Output example:**
```json
{
  "delegator": "0x134a796047a4828f8e6d1fa5e2b0d566a8e8884d",
  "validator": "0x9781a9dD53665cB949A4bF330CD9f081eEb6b72D",
  "shares": "0",
  "stake": "0 GEN",
  "projectedReward": "N/A",
  "pendingDeposits": [
    {
      "epoch": "62",
      "stake": "50 GEN",
      "activatesAtEpoch": "64",
      "epochsRemaining": "2"
    }
  ]
}
✔ Your delegation info
```

> ⏳ 🇬🇧 Stake activates after ~2 epochs (~2 days). Check again after that to see rewards.  
> ⏳ 🇧🇩 ~2 epoch (~2 দিন) পর stake active হবে। তারপর আবার check করলে reward দেখবে।  
> ⏳ 🇮🇳 ~2 epoch (~2 दिन) बाद stake active होगा। उसके बाद check करें तो reward दिखेगा।

**Check after 2 days / ২ দিন পর / 2 दिन बाद:**
```bash
genlayer staking delegation-info 0x9781a9dD53665cB949A4bF330CD9f081eEb6b72D
```

---

## 11. Common Errors & Fixes

---

### ❌ `required option '--name <name>' not specified`

🇬🇧 You forgot to add `--name` flag.  
🇧🇩 `--name` flag যোগ করতে ভুলে গেছ।  
🇮🇳 `--name` flag लगाना भूल गए।

```bash
# ❌ Wrong / ভুল / गलत:
genlayer account create

# ✅ Correct / ঠিক / सही:
genlayer account create --name mritunjoy
```

---

### ❌ `fetch failed` / RPC error

🇬🇧 Network is not set. Set it first.  
🇧🇩 Network set করা নেই। আগে set করো।  
🇮🇳 Network set नहीं है। पहले set करें।

```bash
genlayer network set testnet-asimov
```

---

### ❌ `unknown option '--network'`

🇬🇧 `account show` does not support `--network`. Use `--rpc` instead.  
🇧🇩 `account show`-এ `--network` কাজ করে না। `--rpc` ব্যবহার করো।  
🇮🇳 `account show` में `--network` काम नहीं करता। `--rpc` use करें।

```bash
genlayer account show --account mywallet --rpc https://rpc.asimov.genlayer.com
```

---

### ❌ `validator address is required`

🇬🇧 You must provide a validator address with `delegation-info`.  
🇧🇩 `delegation-info`-এর সাথে validator address দিতে হবে।  
🇮🇳 `delegation-info` के साथ validator address देना होगा।

```bash
# ✅ Correct / ঠিক / सही:
genlayer staking delegation-info 0x9781a9dD53665cB949A4bF330CD9f081eEb6b72D
```

---

### ❌ Running Codespaces command in Mac terminal

🇬🇧 Make sure you are in the browser Codespaces terminal, NOT your System terminal.  
🇧🇩 নিশ্চিত করো তুমি browser-এর Codespaces terminal-এ আছ, System terminal-এ নয়।  
🇮🇳 सुनिश्चित करें कि आप browser के Codespaces terminal में हैं, System terminal में नहीं।

```
# ❌ System terminal (Wrong / ভুল / गलत):
mritunjoy@Mritunjoys-MacBook-Air ~ %

# ✅ Codespaces terminal (Correct / ঠিক / सही):
@Mritun55 ➜ /workspaces/Genlayer-Deligator-node (main) $
```

---

## 12. Important Notes

### 🔐 Security / নিরাপত্তা / सुरक्षा

🇬🇧 Never push `mywallet.json` to GitHub. Add it to `.gitignore`:  
🇧🇩 `mywallet.json` কখনো GitHub-এ push করো না। `.gitignore`-এ add করো:  
🇮🇳 `mywallet.json` को कभी GitHub पर push मत करें। `.gitignore` में add करें:

```bash
echo "*.json" >> .gitignore
```

🇬🇧 GenLayer CLI does **not** create a mnemonic phrase. Your backup = **keystore file + password**.  
🇧🇩 GenLayer CLI **mnemonic phrase তৈরি করে না**। তোমার backup = **keystore file + password**।  
🇮🇳 GenLayer CLI **mnemonic phrase नहीं बनाता**। आपका backup = **keystore file + password**।

---

### ⏰ Timing / সময় / समय

| | 🇬🇧 English | 🇧🇩 বাংলা | 🇮🇳 हिंदी |
|---|---|---|---|
| 1 Epoch | ~1 day | ~১ দিন | ~1 दिन |
| Activation time | ~2 days | ~২ দিন | ~2 दिन |
| Codespaces off? | Delegation stays safe ✅ | Blockchain-এ safe থাকে ✅ | Blockchain पर safe रहता है ✅ |

---

### 💰 Delegator vs Validator

| | Delegator | Validator |
|---|---|---|
| 🇬🇧 Min Stake | 50 GEN | 42,000 GEN |
| 🇬🇧 Server needed? | ❌ No | ✅ Yes |
| 🇬🇧 Difficulty | ⭐ Easy | ⭐⭐⭐ Hard |
| 🇧🇩 সর্বনিম্ন stake | 50 GEN | 42,000 GEN |
| 🇧🇩 Server লাগে? | ❌ না | ✅ হ্যাঁ |
| 🇧🇩 কঠিনতা | ⭐ সহজ | ⭐⭐⭐ কঠিন |
| 🇮🇳 न्यूनतम stake | 50 GEN | 42,000 GEN |
| 🇮🇳 Server चाहिए? | ❌ नहीं | ✅ हाँ |
| 🇮🇳 कठिनाई | ⭐ आसान | ⭐⭐⭐ कठिन |

---

## 🎉 Congratulations! / অভিনন্দন! / बधाई हो!

🇬🇧 You have successfully set up your GenLayer Delegator Node! Now just wait and earn rewards. 🏆

🇧🇩 তুমি সফলভাবে GenLayer Delegator Node setup করে ফেলেছ! এখন শুধু অপেক্ষা করো এবং reward earn করো। 🏆

🇮🇳 आपने सफलतापूर्वक GenLayer Delegator Node setup कर लिया है! अब बस इंतजार करें और reward कमाएं। 🏆

---

*Made with ❤️ by Mritunjoy*
