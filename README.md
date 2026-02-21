# CounterApp: On-Chain Next.js Starter

A modern Web3 application showcasing a clean, responsive interface to interact with an on-chain Counter smart contract. This project demonstrates seamlessly integrating blockchain interactions within a modern Next.js ecosystem.

## 🌟 Overview

CounterApp allows users to connect their Web3 wallets and interact with a deployed smart contract on the **Sepolia Testnet**. Users can view the current counter value, increment it, and decrement it. The contract owner has exclusive rights to reset the counter to zero.

This project serves as an excellent starting point for developers looking to build on-chain React native apps, demonstrating best practices in Web3 frontend architecture.

## 🚀 Features

- **Wallet Connection:** Seamless and secure wallet connection using Thirdweb's robust `ConnectButton`.
- **Live On-Chain Data:** Reads the counter state directly from the smart contract in real-time using `useReadContract`.
- **State Mutating Transactions:** Securely executes `increment` and `decrement` functions using `TransactionButton`.
- **Role-Based Access Control (RBAC):** Conditionally renders the `reset` functionality exclusively for the smart contract owner.
- **Modern Tech Stack:** Built with Next.js 15 (App Router), React 19, Tailwind CSS, and Thirdweb SDK v5.

## 🧠 Developer Expertise Demonstrated

This repository highlights expertise in several modern web and blockchain development areas:

- **Web3 Integration:** Mastery of Thirdweb SDK v5 for creating robust client-side blockchain interactions without the complexity of managing raw ABIs and Web3 providers manually.
- **React & Next.js Pattern Mastery:** Effective use of React Hooks (`useActiveAccount`, `useReadContract`), Next.js App Router, and Client Components (`"use client"`).
- **Graceful UI/UX:** Implementing loading states, transaction confirmation alerts, and error handling for a smooth decentralized application (dApp) user experience.
- **Environment Management:** Secure handling of Thirdweb API keys and client IDs using environment variables.

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/en/) (v18 or higher)
- [pnpm](https://pnpm.io/) (used in this project based on `pnpm-lock.yaml`)
- A Thirdweb Client ID. You can get one from the [Thirdweb Dashboard](https://thirdweb.com/dashboard/settings/api-keys).

## 🛠 Installation & Local Setup

1. **Clone the repository:**

   ```bash
   git clone <your-repo-url>
   cd counterapp
   ```

2. **Install dependencies:**

   ```bash
   pnpm install
   ```

3. **Configure Environment Variables:**
   - Copy `.env.example` to `.env.local`:
     ```bash
     cp .env.example .env.local
     ```
   - Open `.env.local` and add your Thirdweb Client ID:
     ```env
     NEXT_PUBLIC_TEMPLATE_CLIENT_ID=your_actual_client_id_here
     ```

4. **Run the Development Server (with Turbopack):**

   ```bash
   pnpm run dev
   ```

5. **Open the app:**
   Visit [http://localhost:3000](http://localhost:3000) in your browser.

## 🧪 Testing the Application

### Manual Verification Guide

To fully test the application locally, follow these steps:

1. **Start the App:** Ensure your local development server is running (`pnpm run dev`).
2. **Connect Wallet:** Click the "Connect Wallet" button and connect a wallet (e.g., MetaMask) that is switched to the **Sepolia Testnet**. You will need some Sepolia ETH to perform transactions.
3. **Read Data:** Once connected, the application should automatically fetch and display the current counter value.
4. **Interact (Increment/Decrement):**
   - Click the **`+`** button to increment the counter. Approve the transaction in your wallet.
   - Click the **`-`** button to decrement the counter. Approve the transaction in your wallet.
   - You should see alert popups confirming when transactions are sent and confirmed, followed by the counter value updating on the UI.
5. **Test Owner Role (Reset):**
   - Disconnect and connect with a different wallet address. The "Reset" button should _not_ be visible, and instead, you should see "You are not the owner".
   - Connect with the deployer/owner wallet. The "Reset" button should appear. Click it, confirm the transaction, and the counter will reset to 0.

## 🏗 Smart Contract Details

- **Network:** Sepolia Testnet
- **Contract Address:** `0x6e38356f796a4b023607f17e8ec7954241be284c`

## 🤝 Need Help?

For Thirdweb SDK specific help or feedback, please [visit the Thirdweb support site](https://thirdweb.com/support) or read their [Documentation](https://portal.thirdweb.com/typescript/v5).
