
# 📘 Understanding Aave V3: Supplying and Borrowing

Aave V3 is a **decentralized liquidity protocol** where users can act as either **suppliers (lenders)** or **borrowers**.  
This lesson covers how supplying and borrowing works, including step-by-step guides and important financial mechanics.

---

## 🔑 Core Concepts

- **Supplying (Lending)**  
  Users deposit assets into Aave V3 liquidity pools. These assets earn interest over time.

- **Borrowing**  
  Users borrow assets from liquidity pools, but only if they supply enough collateral. Borrowers pay interest.

- **Collateral**  
  Assets supplied that secure a loan. Example: Supplying DAI and enabling it as collateral allows borrowing ETH.

- **Interest Dynamics**  
  Suppliers earn interest, which comes from the interest borrowers pay.

---

## 🟢 Supplying Assets (Example: DAI)

Steps to supply assets:

1. **Navigate to “Assets to Supply”**: Find the list of assets you can supply.  
2. **Select Asset & Amount**: Choose **DAI** and enter an amount. Example: wallet balance = `1.63 DAI`, choose `MAX`.  
3. **Check Initial State**:  
   - Existing supply = `3.52 DAI`.  
   - Health Factor = `1.49`.  
4. **Review Supply Details** (Pop-up: “Supply DAI”):  
   - Amount: `1.63 DAI`.  
   - Supply APY: e.g., `2.57%`.  
   - Collateralization: “Enabled.”  
   - Health Factor Impact: increases (e.g., `1.49 → 2.19`).  
5. **Execute Transaction**: Click **“Supply DAI.”**  
6. **Confirm in Wallet** (MetaMask, gas fees apply).  
7. **Wait for On-Chain Confirmation** → “All done. You Supplied 1.63 DAI.”  
8. **Verify Updated Balances**:  
   - Supplies = `5.15 DAI` (3.52 + 1.63).  
   - Health Factor = `2.19`.  

✅ Supplying collateral usually **increases Health Factor**.

---

## 🔴 Withdrawing Assets (Example: DAI)

Steps to withdraw assets:

1. **Go to “Your Supplies”**: Select the asset (e.g., `5.15 DAI`).  
2. **Click “Withdraw”**.  
3. **Choose Amount**:  
   - Example: “MAX” = `2.77 DAI` (not full `5.15 DAI`).  
   - Reason: Some DAI is locked as collateral for an ETH borrow.  
4. **Impact on Health Factor**:  
   - Before: HF = `2.19`.  
   - After withdrawal: HF drops to ~`1.01`.  
   - If HF ≤ 1.0 → **Liquidation risk**.  
5. **Confirm in Wallet**.  
6. **Wait for Confirmation** → “All done. You withdrew 2.78 DAI.”  
7. **Updated Balances**:  
   - Supplies = `2.37 DAI`.  
   - HF = `1.01` (risky zone).  

⚠️ Withdrawals are limited by **collateral requirements**.

---

## 📊 The Health Factor (HF)

- HF shows **safety of your loan position** relative to collateral.

- **HF > 1.0** → Safe, overcollateralized.  
- **HF ≤ 1.0** → At risk of liquidation.  

### ✅ Increases HF:
- Supplying more collateral.  
- Repaying debt.  
- Collateral value increases.  

### ❌ Decreases HF:
- Borrowing more.  
- Withdrawing collateral.  
- Collateral value drops or debt value rises.  

⚠️ Always monitor HF to **avoid liquidation**.

---

## 📖 Asset Details (Example: DAI)

Clicking **“Details”** reveals:

- **Reserve Size**: Total supplied in market (e.g., `$160.37M`).  
- **Available Liquidity**: Unborrowed amount (e.g., `$44.91M`).  
- **Utilization Rate**: % of supply being borrowed. Formula:  
  `(Reserve Size - Available Liquidity) / Reserve Size`.  
  Example: `72%`.  
- **Supply APY vs. APR**:  
  - **APY** = Annual yield with compounding.  
  - **APR** = Annual rate without compounding.  
  - APY > APR when compounding occurs.  

---

## ⚙️ Collateral Parameters

- **Can be collateral**: DAI = Yes.  
- **Max LTV (Loan-to-Value)**: % of collateral you can borrow. Example: 63% (supply $100 → borrow $63).  
- **Liquidation Threshold**: % at which liquidation starts (e.g., 77%).  
- **Liquidation Penalty**: Extra collateral taken as fee (e.g., 5%).  

---

## 📈 Interest Rate Model

- Borrow rates depend on **Utilization Rate**.  
- As utilization ↑ → Borrow APR ↑.  
- **Optimal Utilization Rate** (e.g., 92%): Borrow rates rise steeply above this to keep liquidity balanced.  

---

## 🖥️ Aave V3 UI Elements

- **Top Bar**: Net Worth, Net APY, Health Factor, Risk, Transactions, Wallet, Settings.  
- **Your Supplies**: Assets supplied, APY earned, collateral toggle, withdraw option.  
- **Your Borrows**: Assets borrowed, debt amount, APY paid, repay option.  
- **Assets to Supply**: Tokens available to supply with APY shown.  
- **Assets to Borrow**: Tokens available to borrow with borrow rates.  
- **Asset Detail Page**: Shows Reserve Size, Liquidity, Utilization, Collateral parameters.  

---

## 🏆 Best Practices for Aave V3

- **Earn by Supplying**: Passive yield on assets.  
- **Understand Borrow Costs**: Borrowing incurs variable interest.  
- **Monitor Health Factor**: Keep HF comfortably above 1.0.  
- **Action Impacts**: Supplying ↑ HF, Borrowing/Withdrawing ↓ HF.  
- **Withdrawal Limits**: You may not withdraw all collateral if it backs a loan.  
- **Know APY vs. APR**: APY includes compounding, APR does not.  
- **Avoid Liquidation Risks**: Always maintain a buffer above liquidation threshold.  

---

# 🎯 Key Takeaways

- Supplying earns interest; borrowing costs interest.  
- Health Factor is the **safety metric** — must stay > 1.0.  
- Withdrawals are limited by collateral and active borrows.  
- Aave V3 uses a **dynamic interest model** tied to utilization.  
- Smart navigation of the UI helps in **risk management**.  

---
