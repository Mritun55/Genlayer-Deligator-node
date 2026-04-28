# 🚀 GenLayer Delegator Node — Complete Beginner Guide

> 🇬🇧 English | 🇧🇩 বাংলা | 🇮🇳 हिंदी
> Author: Mritunjoy | Network: Testnet Asimov

## 1. Install GenLayer CLI

🇬🇧 Run in GitHub Codespaces terminal.
🇧🇩 GitHub Codespaces terminal এ চালাও।
🇮🇳 GitHub Codespaces terminal में चलाएं।

\`\`\`bash
npm install -g genlayer
\`\`\`

## 2. Create Account

\`\`\`bash
genlayer account create --name mritunjoy
\`\`\`

## 3. Get Wallet Address

\`\`\`bash
cat /home/codespace/.genlayer/keystores/mritunjoy.json | grep -i address
\`\`\`

## 4. Set Network

\`\`\`bash
genlayer network set testnet-asimov
\`\`\`

## 5. Find Active Validators

\`\`\`bash
genlayer staking active-validators --network testnet-asimov
\`\`\`

## 6. Join as Delegator

\`\`\`bash
genlayer staking delegator-join --account mritunjoy --amount 50gen <VALIDATOR_ADDRESS>
\`\`\`

## 7. Verify Delegation

\`\`\`bash
genlayer staking delegation-info <VALIDATOR_ADDRESS>
\`\`\`
