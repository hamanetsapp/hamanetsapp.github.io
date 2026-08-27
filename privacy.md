---
title: Hamanets — Privacy Policy
permalink: /privacy/
---

**English** · [Українська](/privacy-uk/)

# Hamanets — Privacy Policy

**Effective date:** 26 August 2026
**Last updated:** 26 August 2026

---

## 1. Summary

Hamanets is a personal finance app for iPhone. It has **no user accounts, no
sign-up, and no server operated by us**.

Your financial data — accounts, transactions, categories, tags, budgets, debts
and receipt photos — is created and stored **on your device only**. We cannot
see it, we do not receive it, and we have no technical means of accessing it.

The app contains **no analytics, no advertising, no tracking, and no
third-party SDKs**.

There are exactly three situations in which Hamanets communicates over the
network, and each is described in detail in Section 4. Only one of them —
sending us a problem report, which you start yourself — results in any
information reaching us.

---

## 2. Who is responsible for your data

The data controller is:

**Mykola Vasylevskyi**, an individual developer, Ukraine.
Contact: **[hamanets.app@icloud.com](mailto:hamanets.app@icloud.com)**

Because Hamanets stores your financial data exclusively on your device and
transmits it to no service of ours, we act as a controller only in respect of
the limited information you choose to send us, as described in Section 4.3.

---

## 3. What Hamanets stores on your device

All of the following is written to storage inside the app's own sandboxed
container on your iPhone. None of it is transmitted to us.

### 3.1. Financial and organisational data

- Accounts you create: name, type, currency, opening and current balances,
  and whether the account is excluded from totals.
- Transactions: amount, currency, date, description or note, category, tags,
  the accounts involved, and the exchange rate applied at the time.
- Categories and tags you define.
- Budgets and budget periods.
- Debts and credit-card grace-period information.
- The in-app notification history.
- App settings: base currency, appearance (light/dark/system), auto-lock
  interval, and whether reminders are enabled.

This is stored in a local database file inside the app container.

### 3.2. Receipt photos

If you attach a photo to a transaction, the selected image is copied into the
app's own storage as a file. Only the file name is recorded in the database.

Hamanets uses the **iOS system photo picker**. This means the app is not granted
access to your photo library: iOS shows the picker outside of the app, and
hands Hamanets only the single image you chose.

### 3.3. Credentials, held in the iOS Keychain

- **Your PIN.** If you set an app-lock PIN, the PIN itself is **not stored**.
  Hamanets stores only a salted verifier derived with PBKDF2-HMAC-SHA256, which
  can confirm a PIN you type but cannot be reversed to recover it.
- **Your monobank personal token**, if you connect a bank account (Section 4.2).

Both are stored in the iOS Keychain with the accessibility attribute
`kSecAttrAccessibleAfterFirstUnlockThisDeviceOnly`. In practice this means they
are tied to this one device: they are not included in iCloud Keychain
synchronisation and do not migrate to a new device through a backup restore.

### 3.4. Biometrics (Face ID / Touch ID)

If you enable biometric unlock, authentication is performed entirely by iOS.
Your biometric data never leaves the Secure Enclave and is never made available
to Hamanets; the app receives only a success or failure result. Hamanets neither
collects nor stores biometric information of any kind.

---

## 4. Network connections

This is the complete and exhaustive list of network destinations Hamanets
contacts. There are no others.

### 4.1. Exchange rates — `api.frankfurter.dev`

**Purpose:** to convert amounts between currencies.

**What is sent:** currency codes (for example `USD`, `EUR`, `UAH`) and dates.

**What is not sent:** no amounts, no balances, no transactions, no account
names, no device identifiers, no advertising identifiers, and no information
that identifies you or your device.

The service requires no API key and no account, so these requests carry no
credential that could link them to you.

### 4.2. Bank synchronisation — `api.monobank.ua`

This applies **only if you choose to connect a monobank account**. If you do
not use bank sync, Hamanets never contacts this service.

**How it works:** you create a personal API token yourself in monobank's own
web cabinet and paste it into Hamanets. Your device then talks **directly to
monobank's servers**. There is no Hamanets server anywhere in this path. We do
not receive, proxy, observe, or store your token, your bank credentials, your
account details, or your transactions.

**What is sent:** your own token, in the request header, to monobank only.

**What is received:** your account information and statement entries, which are
written to the local database on your device as described in Section 3.1.

Your use of monobank's API is governed by monobank's own terms and privacy
policy. You can revoke the token at any time in the monobank cabinet, and you
can disconnect the account inside Hamanets — with the option to delete the
imported data at the same time.

### 4.3. Problem reports — email to us

This is the **only** path by which any information reaches us, and it never
happens automatically. It occurs only when you open **Settings → Report a
Problem**, fill in the form, and send the message yourself.

**How it is sent:** Hamanets prepares a message and hands it to the standard iOS
Mail composer. The message is sent from your own email account, through your
own email provider. You can read, edit, shorten, or delete anything in it —
including the attachment — before sending, and you can cancel without sending.

**What the message contains:**

1. **Your three free-text answers** — what you were doing, what you expected,
   and what you saw. This text is entirely yours. The form explicitly asks you
   not to include account numbers, card numbers, or amounts.
2. **One attachment**, a plain-text JSON file named `hamanets_<date>_<time>_error.err`,
   containing only:
   - your device model and iOS version;
   - the Hamanets app version and build number;
   - the app's internal database schema version;
   - up to three records of errors that occurred during the current session,
     each identified by a fixed code chosen by the developer in advance (such
     as which internal operation failed), not by your data.

**What the attachment never contains:** no amounts, balances, account names,
account numbers, card numbers, transaction descriptions, categories, receipt
photos, PIN, bank token, or any other content you entered into the app. The
fields are a fixed, predetermined list; the app cannot place arbitrary data
into them.

**What we necessarily learn:** because the message arrives as ordinary email,
we will see **the email address you sent it from**, along with anything you
wrote.

**Legal basis (GDPR):** Article 6(1)(b) and 6(1)(f) — handling a support
request you initiated, and our legitimate interest in fixing defects in the
app. You are never required to send a report.

**Retention:** support correspondence is kept only as long as needed to deal
with your report and to fix the underlying problem, and is deleted no later
than **12 months** after our last exchange with you, unless you ask us to
delete it sooner.

**International transfer:** our support mailbox is operated by a third-party
email provider that may process the message on servers outside the European
Economic Area. Such transfers rely on the safeguards offered by that provider,
including the European Commission's Standard Contractual Clauses where
applicable.

---

## 5. What Hamanets does not do

To state the absences explicitly:

- **No user accounts.** There is nothing to register for and nothing to log in
  to.
- **No analytics.** No usage statistics, session tracking, screen tracking,
  event logging, or telemetry of any kind is collected or transmitted.
- **No advertising.** No ads, no ad networks, no advertising identifier
  (IDFA), and no App Tracking Transparency prompt, because there is nothing to
  track.
- **No tracking.** We do not link any data to you or your device across apps
  or websites, and we do not share data with data brokers.
- **No third-party SDKs.** The app is built on Apple's own frameworks only.
- **No cloud sync.** Hamanets does not use CloudKit or any other synchronisation
  service. Your data does not sync between devices.
- **No push notifications.** Reminders are generated and scheduled locally by
  your device. There is no push server and no device push token.
- **No data selling or sharing.** We do not sell, rent, trade, or share
  personal data with anyone, for any purpose.

---

## 6. Backups

If you have iCloud Backup enabled in iOS, your iPhone's backup — which
includes Hamanets' data, as it does for other apps — is stored in your own
iCloud account. This backup is created and controlled by Apple under
[Apple's Privacy Policy](https://www.apple.com/legal/privacy/), not by us. We
have no access to it.

As noted in Section 3.3, your PIN verifier and monobank token are marked
device-only and do not travel to a new device through a backup.

If you disable iCloud Backup in iOS Settings, Hamanets' data stays only on the
device.

---

## 7. Data we may receive through Apple

Independently of the app, Apple may provide us with:

- **Aggregated App Store and App Analytics reports** (downloads, territories,
  crash counts). These are aggregated statistics produced by Apple, and they
  do not identify individual users.
- **Crash and diagnostic reports**, but only if you have chosen to share
  analytics with app developers in **iOS Settings → Privacy & Security →
  Analytics & Improvements**. That choice is yours and is made in iOS, not in
  Hamanets; you can change it at any time.
- **App Store reviews and ratings** you choose to publish, and any message you
  send us through App Store Connect.

---

## 8. Security

- Your data resides in the app's sandboxed container, protected by iOS file
  protection and by your device passcode.
- Optional app lock with a PIN and/or Face ID / Touch ID, with a configurable
  auto-lock interval.
- The PIN is stored only as a salted PBKDF2-HMAC-SHA256 verifier, never in
  plain text.
- Credentials are held in the iOS Keychain, restricted to this device.
- Whenever the app is not in the foreground, an opaque privacy screen covers
  the interface, so that the iOS app-switcher preview never exposes your
  balances.
- An in-app toggle hides all monetary amounts on demand.

No method of storage is absolutely secure, but because there is no server and
no account, there is also no central store of user data that could be breached.

---

## 9. Your rights

Under the EU/EEA and UK General Data Protection Regulation and, in Ukraine,
under the Law of Ukraine "On Personal Data Protection" (No. 2297-VI), you have
the right to access, rectify, erase, restrict and object to the processing of
your personal data, the right to data portability, and the right to withdraw
consent at any time.

How these rights work in practice for Hamanets:

**Data on your device.** You control it directly and completely, without
needing to contact us. You can edit or delete any account, transaction,
category, tag, budget or receipt inside the app at any time. Deleting the app
from your iPhone removes its database, its stored receipt images and its
Keychain items. Copies may persist in your own iCloud backups until those
backups are overwritten or deleted by you in iOS Settings.

**Bank connection.** You can disconnect a bank account in
**Settings → Bank Sync**, and choose to delete the imported data at the same
time. You can additionally revoke the token in monobank's own cabinet.

**Support correspondence.** Write to **[hamanets.app@icloud.com](mailto:hamanets.app@icloud.com)** to request a copy of
what we hold from your report, to have it corrected, or to have it deleted. We
will respond within **30 days**.

**Complaints.** You may lodge a complaint with a supervisory authority — in the
EU/EEA, the data protection authority of your country of residence; in the UK,
the Information Commissioner's Office; in Ukraine, the Ukrainian Parliament
Commissioner for Human Rights (Уповноважений Верховної Ради України з прав
людини).

---

## 10. Children

Hamanets is a general-audience personal finance app. It is not directed to
children under 16, and we do not knowingly collect personal data from them.
Since the app has no accounts and collects nothing automatically, we have no
means of identifying a user's age. If you believe a child has sent us a support
report containing personal data, contact **[hamanets.app@icloud.com](mailto:hamanets.app@icloud.com)** and we will
delete it.

---

## 11. Changes to this policy

If this policy changes, the updated version will be published at this address
with a new effective date. Material changes — in particular any change to what
leaves your device — will also be noted in the app's release notes on the App
Store. Continuing to use Hamanets after a change means you accept the updated
policy.

---

## 12. Contact

Questions about this policy or about your data:

**{{SUPPORT_EMAIL}}**
