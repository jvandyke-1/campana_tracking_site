# Campana Charge and Usage Tracker - User Manual

## Table of Contents
1. [Introduction](#1-introduction)
2. [Getting Started](#2-getting-started)
    - [System Requirements](#21-system-requirements)
    - [Initial Configuration](#22-initial-configuration)
3. [Dashboard Overview](#3-dashboard-overview)
    - [Instrument Status Grid](#31-instrument-status-grid)
    - [Fund Monitoring](#32-fund-monitoring)
4. [Usage Tracking](#4-usage-tracking)
    - [Recording Usage](#41-recording-usage)
    - [Usage vs Post Dates](#42-usage-vs-post-dates)
5. [Administrative Features](#5-administrative-features)
    - [Balance Adjustments](#51-balance-adjustments)
    - [Deleting Entries](#52-deleting-entries)
    - [Exporting Data](#53-exporting-data)
6. [Auditing and Compliance](#6-auditing-and-compliance)
    - [Adjustment Logs](#61-adjustment-logs)
    - [Delete History Logs](#62-delete-history-logs)
7. [Synchronization and Multi-Admin Support](#7-synchronization-and-multi-admin-support)
8. [Data Reset and Security](#8-data-reset-and-security)

---

## 1. Introduction
The **Campana Charge and Usage Tracker** is a application designed to allow FCSR staff to monitor and manage reamining laboratory funds/usage remaining from Campana's balence in real-time. The system uses a centralized GitHub repository as a "source of truth," allowing multiple staff members to stay synchronized across different machines.

## 2. Getting Started

### 2.1 System Requirements
- Windows 10/11
- Active Internet Connection (for GitHub synchronization)
- GitHub Personal Access Token (PAT) with `repo` permissions

### 2.2 Initial Configuration
Upon first launch, tap the **Gear Icon** (top right) to configure your administrator profile:
1. **User Name**: Enter your name (e.g., Jonathan Van Dyke). This will tag all your entries in the history.
2. **GitHub Credentials**:
   - **Repo**: The `owner/repository` where your data is stored.
   - **Path**: The specific file name (e.g., `ledger.json`).
   - **Token**: Your secure GitHub Personal Access Token.
3. Tap **Save & Sync** to establish the connection.

## 3. Dashboard Overview

### 3.1 Instrument Status Grid
The status grid shows the current available hours (h) or seats for each lab service.
- **Color Coding**: Balances turn **Red** if they drop below zero, indicating over-usage.
- **Dynamic Updates**: Values refresh automatically after every transaction or manual refresh.

### 3.2 Fund Monitoring
Total Lab Funds are calculated dynamically based on the current instrument hours multiplied by their respective service rates.
- **Critical Warning**: If funds drop below $0.00, a dramatic red banner will appear at the top of the screen to alert the administrator.

## 4. Usage Tracking

### 4.1 Recording Usage
To log a session:
1. Select the **Researcher** from the dropdown.
2. Select the **Instrument / Service**.
3. **Required**: Tap "Select Usage Date" to pick the actual day the service was used.
4. Enter the **Hours/Seats** to debit. Use the quick-add buttons (+0.5, +1.0, +2.0) for speed.
5. Tap **Submit** and confirm the details in the popup.

### 4.2 Usage vs Post Dates
The system tracks two distinct timestamps for every entry:
- **Usage Date**: The actual date of work (selected by the admin).
- **Logged Date**: The date the entry was actually entered into the system.

## 5. Administrative Features

### 5.1 Balance Adjustments
Accessed via the **Add Chart Icon** in the app bar. This allows you to manually add or subtract hours/seats from the starting pool.
- Use the **+/- buttons** to stage changes.
- Click **Update Pool** and provide a mandatory reason for the adjustment.

### 5.2 Deleting Entries
Mistakes can be corrected by deleting entries in the **Full Ledger History** list:
1. Locate the entry and tap the **Red Trash Icon**.
2. Provide a mandatory reason for removal.
3. The system will automatically "refund" the hours and funds to the lab totals.

### 5.3 Exporting Data
Tap the **Export CSV** button above the history list to download the entire ledger as a spreadsheet-compatible file for reporting.

## 6. Auditing and Compliance

### 6.1 Adjustment Logs
View a detailed history of all manual hour/seat modifications by tapping **View Adjustment Logs** inside the adjustment screen.

### 6.2 Delete History Logs
View a full post-mortem of all removed transactions by tapping **Delete History Logs** above the main history list.

## 7. Synchronization and Multi-Admin Support
The app features built-in **Conflict Resolution**. If two administrators update the ledger simultaneously, the app will automatically merge the changes to ensure no data is lost. Tap the **Refresh Icon** at any time to pull the latest data from GitHub.

## 8. Data Reset and Security
To start a fresh tracking period, go to Settings and tap **Reset All**.
- **Password Protection**: You must type `RESET` to confirm.
- **Scope**: This clears the main ledger, the deletion history, and the adjustment logs simultaneously.
