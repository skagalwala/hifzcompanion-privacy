# Privacy Policy — Hifz Musaa'id

**Effective Date:** May 16, 2026
**Last Updated:** May 16, 2026

---

> **Draft notice:** This document is a working draft prepared for review by qualified legal counsel before publication. The clauses below describe the app's actual data practices as of the effective date, but legal sufficiency in your jurisdiction is a separate question that a lawyer should sign off on — particularly the limitation-of-liability, indemnification, and governing-law sections.

---

## 1. Introduction

This Privacy Policy explains how Hifz Musaa'id ("the App", "we", "our", or "us") collects, uses, stores, and protects your personal information. Hifz Musaa'id is an iOS application for Quran memorization (Hifz) and revision (Muraja'ah), operated as an individual venture by **Shhabbir Kagalwala** ("the operator").

We take your privacy seriously. The App was designed from the start to collect the minimum data necessary to provide its functionality. We do not run advertising. We do not embed third-party analytics or behavioral-tracking SDKs. We do not sell user data to third parties for any purpose.

If you have questions about this policy or about how your information is handled, contact us at **shabbir.com@gmail.com**.

## 2. Information We Collect

### 2.1 Information you provide directly

**Sign in with Apple (optional).** When you choose to sign in with Apple, Apple shares with us:

- A unique, Apple-issued user identifier (a string opaque to us — not your Apple ID email or username).
- Your email address. Depending on what you choose in Apple's sign-in sheet, this may be your real email or an Apple-relay email that forwards to your real address.
- Your name (first and last), if and only if you choose to share it in the Apple sign-in sheet. You can choose to omit it; the App functions normally without it.

We never see your Apple ID password and have no way to authenticate you outside the Apple sign-in flow.

**Activation codes.** If you redeem an activation code (a 12-character alphanumeric string distributed by us for promotional or institutional access), the code itself is sent to our server for validation and stored locally on your device alongside the entitlement it grants.

### 2.2 Information we collect automatically

**Device identifier.** On first launch, the App generates a random UUID and stores it in iOS Keychain. This identifier is unique to the App on your device (it is not your Apple ID, your IDFV alone, or your phone number). We send this identifier to our backend when you redeem an activation code or when we verify an existing activation, so we can recognize your device across requests. The identifier is reset only by a full device factory reset.

**Practice session timestamps.** The App records the date and time of each practice session you complete (when you tap Build My Program and audio plays). These timestamps are stored locally on your device in user defaults. They are used to power the streak counter and any future progress-tracking features. They are not transmitted to our servers at present.

**Subscription state.** When you subscribe to Lite or Pro through the App Store, Apple manages the transaction. Our app reads the resulting "entitlement" from Apple's StoreKit framework — a verified token that confirms you have an active subscription. We do not see your credit card number, billing address, or any other Apple ID details. Apple's privacy policy governs Apple-side data: https://www.apple.com/legal/privacy/

**Network metadata.** When the App makes requests to our backend (for audio file URLs or to verify activations), our server briefly observes your device's public IP address. The IP is used solely for rate-limiting (rejecting brute-force attempts at code redemption) and is not retained in logs beyond the rate-limit window (5 minutes by default).

### 2.3 What we do NOT collect

We do not collect, request, or transmit:

- Your real name (unless you explicitly share it via Sign in with Apple).
- Your phone number.
- Your physical or precise location (the App does not request location permission).
- Camera or microphone data (the App does not request these permissions).
- Your contacts, calendar, or photo library.
- Cross-app advertising identifiers (IDFA — the App does not request the tracking-transparency prompt).
- Health, fitness, financial, or browsing history data.

We do not use cookies. The App is not a web browser and does not embed web views that load third-party trackers.

## 3. How We Use Your Information

We use the limited information described above only for the following purposes:

- **Authentication** — recognizing you across launches and devices so your saved programs, subscription status, and activation codes follow you.
- **Subscription delivery** — confirming via Apple's StoreKit that your Lite or Pro entitlement is active and serving you the corresponding tier of features.
- **Activation code validation** — verifying that codes you redeem are valid, unused (or within their per-code redemption limit), and not expired.
- **Audio content delivery** — fetching Quran recitation audio files from our content delivery network when you build a program.
- **Service operation and security** — preventing abuse of our backend (rate limiting), debugging crashes, and improving the App's reliability.

We do not use your information for advertising, profiling, automated decision-making about you, or any commercial purpose beyond operating the App you paid for.

## 4. How We Share Your Information

We share information only with the following parties, and only for the purposes described:

**Apple Inc.** — Apple processes your subscription purchases, free trial activations, and Sign in with Apple flows. Apple receives information necessary to do this directly from you, not from us. Apple's handling of your data is governed by Apple's privacy policy.

**Supabase, Inc.** — Our backend (database, authentication, edge functions, content storage) is hosted by Supabase, Inc., a U.S.-based service provider. Supabase processes activation verifications, device identifiers, and audio file URLs on our behalf under a data processing agreement. Supabase does not use the data for its own purposes. Supabase's privacy policy: https://supabase.com/privacy

**Quran.com API (incidental, fallback only).** If our bundled Arabic text data does not contain a specific verse you view (rare), the App may fetch the verse text from the public Quran.com API. These requests are made directly from your device and include only the verse identifier (e.g., "67:1"). No personal information is sent to Quran.com.

We do not sell your personal information. We do not share it with advertisers, data brokers, or any third party not listed above. We do not transmit your information for cross-context behavioral advertising.

We may disclose your information to comply with a valid legal process (subpoena, court order, search warrant) if compelled to do so, but we will challenge requests that appear overbroad and will notify you when permitted by law.

## 5. Data Security

We protect your information using industry-standard practices:

- **In transit:** All network traffic between the App and our backend uses HTTPS with TLS 1.2 or newer. App Transport Security is enabled and we do not allow exceptions.
- **At rest on your device:** Sensitive information (your auth tokens, activation code, device identifier) is stored in iOS Keychain, which is encrypted by hardware. Downloaded audio files are stored on disk encrypted with AES-256-GCM under filenames generated by HMAC-SHA-256; plaintext audio bytes never touch the filesystem.
- **At rest on our servers:** Supabase encrypts data at rest. Access to the database is restricted to the operator and is gated behind row-level security policies and a service-role key that is never embedded in the App.
- **Authentication:** Sign in with Apple uses asymmetric cryptographic proofs (nonces + identity tokens) — Apple authenticates you, not us. We never see or store any password.

No security measure is perfect. If we discover a breach affecting your information, we will notify you and the appropriate authorities within the timeframes required by applicable law.

## 6. Your Rights

### 6.1 Universal rights

Regardless of where you live, you may:

- Ask what information we hold about you.
- Ask us to correct inaccurate information.
- Ask us to delete your information.
- Ask us to export your information in a portable format.
- Withdraw consent for any optional processing.
- Object to processing on legitimate-interests grounds.

To exercise any of these rights, email **shabbir.com@gmail.com** with your request. We will respond within 30 days. We may need to verify your identity (typically by sending a verification email to the address on your Sign in with Apple record) before fulfilling the request.

### 6.2 European Economic Area, United Kingdom, and Switzerland (GDPR / UK GDPR)

If you are located in the EEA, UK, or Switzerland, you have additional rights under the General Data Protection Regulation:

- Lawful basis for our processing is **performance of a contract** (operating the App you've signed in to or subscribed to) and **legitimate interest** (preventing abuse, debugging crashes). Where neither applies, we rely on your consent.
- You have the right to lodge a complaint with your national data protection authority. A list of EU authorities: https://edpb.europa.eu/about-edpb/board/members_en
- We do not engage in automated decision-making or profiling that produces legal or similarly significant effects on you.

### 6.3 California (CCPA / CPRA)

If you are a California resident:

- You have the right to know what categories of personal information we collect and the sources and purposes thereof (this policy describes them).
- You have the right to delete your personal information (subject to limited exceptions).
- You have the right to correct inaccurate personal information.
- You have the right to opt-out of sale or sharing of personal information for cross-context behavioral advertising. **We do not sell or share personal information**, so there is nothing to opt out of, but the right exists.
- We do not knowingly collect personal information of California residents under age 16.

### 6.4 International data transfers

Our servers are located in the United States. If you are located outside the United States, your information will be transferred to and processed in the U.S. We rely on Standard Contractual Clauses (SCCs) approved by the European Commission to safeguard transfers from the EEA to the U.S., and on equivalent mechanisms for the UK and Switzerland.

## 7. Children's Privacy

Hifz Musaa'id is intended for users aged **13 and older**. We do not knowingly collect personal information from children under 13. If you are under 13, please do not use the App or provide any personal information to us.

If you are a parent or guardian and become aware that your child under 13 has provided personal information to us, contact **shabbir.com@gmail.com** and we will delete the information promptly.

Apple's App Store enforces age ratings independently. The App Store category rating for Hifz Musaa'id is 4+ for content, meaning the content itself is suitable for all ages, but the requirement to sign in with Apple (which Apple itself restricts to age 13+) sets the effective minimum at 13.

## 8. Data Retention

We retain personal information only as long as needed to operate the App or to meet a legal obligation:

- **Sign in with Apple records** (Apple user identifier, email): retained as long as you have an active account. If you have not used the App for **24 months**, we may delete your account record. You can request deletion sooner at any time.
- **Subscription state**: managed by Apple, not us. Apple's retention is governed by Apple's privacy policy.
- **Activation code redemption records**: retained as long as the code's entitlement is active (typically the trial duration), plus 12 months for refund / dispute handling, then deleted.
- **Rate-limit logs**: 5 minutes, then automatically purged.
- **Crash logs** (Apple's TestFlight + App Store crash reporting): 12 months, then deleted by Apple per Apple's policy.
- **Locally on your device**: anything stored locally (saved programs, encrypted audio cache, streak data) is deleted when you uninstall the App.

## 9. Third-Party Services

The following third-party services are integral to the App's functionality. Their privacy practices are governed by their own policies, which we link below for your reference:

- **Apple Inc.** — Sign in with Apple, StoreKit (subscriptions), App Store, iCloud Keychain. https://www.apple.com/legal/privacy/
- **Supabase, Inc.** — Backend database, edge functions, content storage. https://supabase.com/privacy
- **Quran.com** — Public Arabic text API (incidental fallback only). https://quran.com/privacy

We do not embed any other third-party SDKs or services. The App does not include Google Analytics, Firebase Analytics, Crashlytics, Mixpanel, Segment, Branch, AppsFlyer, Adjust, or any similar product.

## 10. Changes to This Policy

We may update this Privacy Policy from time to time. Material changes (anything that would expand the data we collect or how we use it) will be communicated to you through the App or via the email address associated with your Sign in with Apple record, at least 30 days before taking effect.

Non-material updates (typos, clarifications, links) will be posted here with a revised "Last Updated" date.

If you continue using the App after a material change takes effect, you accept the updated policy. If you do not accept it, you may stop using the App at any time and request deletion of your information.

## 11. Contact

For any privacy question, request, or complaint:

**Shhabbir Kagalwala**
Operator, Hifz Musaa'id
Email: shabbir.com@gmail.com

We are based in the State of Texas, United States of America.

---

*This policy is governed by the laws of the State of Texas, USA, without regard to its conflict-of-laws principles, except where applicable consumer-protection law in your jurisdiction provides otherwise. Disputes will be resolved in the state or federal courts located in Texas, subject to your rights under local law.*
