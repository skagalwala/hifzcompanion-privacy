# Privacy Policy — Hifz Musaa'id

**Effective Date:** May 24, 2026
**Last Updated:** May 24, 2026


## 1. Introduction

This Privacy Policy explains how Hifz Musaa'id ("the App", "we", "our", or "us") collects, uses, stores, and protects your personal information. Hifz Musaa'id is a mobile application for Quran memorization (Hifz) and revision (Muraja'ah), available on iOS (via the Apple App Store) and on Android (via the Google Play Store), operated as an individual venture by **Shhabbir Kagalwala** ("the operator").

We take your privacy seriously. The App was designed from the start to collect the minimum data necessary to provide its functionality. We do not run advertising. We do not embed third-party analytics or behavioral-tracking SDKs. We do not sell user data to third parties for any purpose.

If you have questions about this policy or about how your information is handled, contact us at **shabbir.com@gmail.com**.

## 2. Information We Collect

### 2.1 Information you provide directly

**Sign in with Apple (optional).** When you choose to sign in with Apple, Apple shares with us:

- A unique, Apple-issued user identifier (a string opaque to us — not your Apple ID email or username).
- Your email address. Depending on what you choose in Apple's sign-in sheet, this may be your real email or an Apple-relay email that forwards to your real address.
- Your name (first and last), if and only if you choose to share it in the Apple sign-in sheet. You can choose to omit it; the App functions normally without it.

We never see your Apple ID password and have no way to authenticate you outside the Apple sign-in flow.

On iOS, Sign in with Apple uses Apple's native sign-in sheet. On Android, Sign in with Apple uses Apple's OAuth web flow: the App opens a secure in-app browser tab (Chrome Custom Tab) to Apple's authentication page, you authenticate with Apple, and Apple redirects an authorization code back to the App via a registered callback URL. We exchange that code for an identity token through our backend, but at no point do we receive your Apple ID password.

**Activation codes.** If you redeem an activation code (a 12-character alphanumeric string distributed by us for promotional or institutional access), the code itself is sent to our server for validation and stored locally on your device alongside the entitlement it grants.

### 2.2 Information we collect automatically

**Device identifier.** On first launch, the App generates a random UUID and stores it in an encrypted on-device keystore. On iOS this is the iOS Keychain; on Android this is `EncryptedSharedPreferences` backed by the Android Keystore using AES-256-GCM (via Google's Tink cryptographic library). This identifier is unique to the App on your device. It is not your Apple ID, your IDFV, your Google Advertising ID, your `Settings.Secure.ANDROID_ID`, or your phone number. We send this identifier to our backend when you redeem an activation code, when we verify an existing activation, or when we request a signed URL to download audio. The identifier is reset only by uninstalling the App or by a full device factory reset.

**Practice session timestamps.** The App records the date and time of each practice session you complete (when you tap Build My Program and audio plays). These timestamps are stored locally on your device — in user defaults on iOS, in Jetpack DataStore on Android. They are used to power the streak counter and any future progress-tracking features. They are not transmitted to our servers at present.

**Subscription state.** When you subscribe to Lite or Pro, the purchase is processed by the platform's billing system — Apple StoreKit on iOS, Google Play Billing on Android. Our App reads the resulting "entitlement" from that billing system: a verified token that confirms you have an active subscription. We do not see your credit card number, billing address, or any other payment-account details. Apple's privacy policy governs Apple-side data: <https://www.apple.com/legal/privacy/>. Google's privacy policy governs Google-side data: <https://policies.google.com/privacy>.

**Network metadata.** When the App makes requests to our backend (for audio file URLs, to verify activations, or to validate in-app-purchase receipts), our server briefly observes your device's public IP address. The IP is used solely for rate-limiting (rejecting brute-force attempts at code redemption or receipt forgery) and is not retained in logs beyond the rate-limit window (5 minutes by default).

### 2.3 What we do NOT collect

We do not collect, request, or transmit:

- Your real name (unless you explicitly share it via Sign in with Apple).
- Your phone number.
- Your physical or precise location (the App does not request location permission).
- Camera or microphone data (the App does not request these permissions).
- Your contacts, calendar, or photo library.
- **Cross-app advertising identifiers.** On iOS, the App does not request the App Tracking Transparency prompt and does not access IDFA. On Android, the App does not access the Google Advertising ID and does not include the `com.google.android.gms.permission.AD_ID` permission.
- **Hardware or telephony identifiers.** On Android, the App does not access `Settings.Secure.ANDROID_ID` (SSAID), `Build.SERIAL`, IMEI, or any `TelephonyManager` identifier. On iOS, the App does not access any private hardware identifier beyond the IDFV that iOS itself surfaces (and we do not transmit IDFV either).
- Health, fitness, financial, or browsing history data.

We do not use cookies. The App is not a web browser. The only embedded web view is the Sign-in-with-Apple OAuth flow on Android (a Chrome Custom Tab) and the rendered Apple sign-in sheet on iOS — neither loads third-party trackers.

## 3. How We Use Your Information

We use the limited information described above only for the following purposes:

- **Authentication** — recognizing you across launches and devices so your saved programs, subscription status, and activation codes follow you.
- **Subscription delivery** — confirming via Apple StoreKit (iOS) or Google Play Billing (Android) that your Lite or Pro entitlement is active and serving you the corresponding tier of features.
- **Activation code validation** — verifying that codes you redeem are valid, unused (or within their per-code redemption limit), and not expired.
- **Audio content delivery** — fetching Quran recitation audio files from our content delivery network when you build a program.
- **Service operation and security** — preventing abuse of our backend (rate limiting), debugging crashes, and improving the App's reliability.

We do not use your information for advertising, profiling, automated decision-making about you, or any commercial purpose beyond operating the App you paid for.

## 4. How We Share Your Information

We share information only with the following parties, and only for the purposes described:

**Apple Inc.** — Apple processes your iOS subscription purchases, free trial activations, and Sign in with Apple flows (on both iOS and Android — Apple is the SIWA identity provider for both platforms). Apple receives information necessary to do this directly from you, not from us. Apple's handling of your data is governed by Apple's privacy policy: <https://www.apple.com/legal/privacy/>.

**Google LLC.** — On Android, Google processes your subscription purchases and free trial activations through Google Play Billing, distributes the App through the Google Play Store, and provides the Google Play Services infrastructure that the App's billing client depends on. Google receives information necessary to do this directly from you (Google account, payment information, device information used for license verification), not from us. Google may also collect device-level diagnostic information about App stability if you have opted in to share diagnostic data with Google. Google's handling of your data is governed by Google's privacy policy: <https://policies.google.com/privacy>.

**Supabase, Inc.** — Our backend (database, authentication, edge functions, content storage) is hosted by Supabase, Inc., a U.S.-based service provider. Supabase processes activation verifications, device identifiers, in-app-purchase receipt validations, and signed audio file URLs on our behalf under a data processing agreement. Supabase does not use the data for its own purposes. Supabase's privacy policy: <https://supabase.com/privacy>.

**Quran.com API (iOS only, incidental, fallback only).** On iOS, if our bundled Arabic text data does not contain a specific verse you view (rare), the App may fetch the verse text from the public Quran.com API. These requests are made directly from your device and include only the verse identifier (e.g., "67:1"). No personal information is sent to Quran.com. The Android App does not include this fallback at present; all Arabic text is bundled.

We do not sell your personal information. We do not share it with advertisers, data brokers, or any third party not listed above. We do not transmit your information for cross-context behavioral advertising.

We may disclose your information to comply with a valid legal process (subpoena, court order, search warrant) if compelled to do so, but we will challenge requests that appear overbroad and will notify you when permitted by law.

## 5. Data Security

We protect your information using industry-standard practices:

- **In transit:** All network traffic between the App and our backend uses HTTPS with TLS 1.2 or newer. On iOS, App Transport Security is enabled and we do not allow exceptions. On Android, network security configuration enforces TLS and blocks cleartext HTTP traffic for all production hosts.
- **At rest on your device — iOS:** Sensitive information (your auth tokens, activation code, device identifier) is stored in iOS Keychain, which is encrypted by hardware. Downloaded audio files are stored on disk encrypted with AES-256-GCM under filenames generated by HMAC-SHA-256; plaintext audio bytes never touch the filesystem.
- **At rest on your device — Android:** Sensitive information (your auth tokens, activation code, device identifier) is stored in `EncryptedSharedPreferences`, backed by the Android Keystore. Keys are 256-bit AES-GCM managed by Google's Tink library; the underlying key material is hardware-bound on devices that support the Android Keymaster HAL. Downloaded audio files are stored on disk encrypted with AES-256-GCM under filenames generated by HMAC-SHA-256; plaintext audio bytes never touch the filesystem. This matches the iOS implementation byte-for-byte.
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
- You have the right to lodge a complaint with your national data protection authority. A list of EU authorities: <https://edpb.europa.eu/about-edpb/board/members_en>.
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

The Apple App Store and Google Play enforce age ratings independently. The Apple App Store category rating for Hifz Musaa'id is 4+ for content, meaning the content itself is suitable for all ages, but the requirement to sign in with Apple (which Apple itself restricts to age 13+) sets the effective minimum at 13. The Google Play target audience and content rating for Hifz Musaa'id is **13+** (Everyone / PEGI 3 content rating; target audience set to teens and older).

## 8. Data Retention

We retain personal information only as long as needed to operate the App or to meet a legal obligation:

- **Sign in with Apple records** (Apple user identifier, email): retained as long as you have an active account. If you have not used the App for **24 months**, we may delete your account record. You can request deletion sooner at any time.
- **Subscription state**: managed by Apple on iOS and Google on Android, not us. Each platform's retention is governed by its own privacy policy.
- **Activation code redemption records**: retained as long as the code's entitlement is active (typically the trial duration), plus 12 months for refund / dispute handling, then deleted.
- **In-app-purchase receipt records**: retained as long as the subscription is active, plus 12 months for refund / dispute handling, then deleted.
- **Rate-limit logs**: 5 minutes, then automatically purged.
- **Crash logs**: On iOS, crash logs are collected by Apple via TestFlight and App Store Connect, retained by Apple for up to 12 months per Apple's policy, and then deleted. On Android, crash logs are collected by Google Play Console for devices whose users have opted in to share diagnostic data with Google. We do not embed any third-party crash reporting SDK (no Crashlytics, no Sentry, no Bugsnag).
- **Locally on your device**: anything stored locally (saved programs, encrypted audio cache, streak data) is deleted when you uninstall the App.

## 9. Third-Party Services

The following third-party services are integral to the App's functionality. Their privacy practices are governed by their own policies, which we link below for your reference:

- **Apple Inc.** — Sign in with Apple (iOS + Android), StoreKit subscriptions (iOS), App Store, iCloud Keychain. <https://www.apple.com/legal/privacy/>
- **Google LLC** — Google Play Billing subscriptions (Android), Google Play Store distribution, Google Play Services (required by Google Play Billing client). <https://policies.google.com/privacy>
- **Supabase, Inc.** — Backend database, edge functions, content storage. <https://supabase.com/privacy>
- **Quran.com** — Public Arabic text API (iOS-only, incidental fallback only). <https://quran.com/privacy>

We do not embed any other third-party SDKs or services. The App does not include Google Analytics, Firebase Analytics, Firebase Crashlytics, Mixpanel, Segment, Branch, AppsFlyer, Adjust, Bugsnag, Sentry, Datadog, or any similar product on either platform.

## 10. Android Runtime Permissions

The Android version of the App declares only the following permissions in its manifest. All are required for core App functionality, and none are used to collect personal data:

- **`INTERNET`** — required to communicate with our backend (activation verification, audio URL signing).
- **`ACCESS_NETWORK_STATE`** — required to detect whether the device is offline so the App can serve cached audio gracefully.
- **`FOREGROUND_SERVICE`** and **`FOREGROUND_SERVICE_MEDIA_PLAYBACK`** — required so audio playback continues when the App is in the background, with the user's awareness via a media-playback notification.
- **`POST_NOTIFICATIONS`** (Android 13+) — required so the media-playback notification can be displayed. You will see a runtime prompt the first time playback begins; if you deny, audio still plays but the system media controls (lock screen / status shade) will not appear.
- **`WAKE_LOCK`** — required to keep the audio engine running during playback when the screen is off.

The App does not declare permissions for camera, microphone, location, contacts, calendar, photos, SMS, phone state, or storage beyond its own scoped sandbox. The App does not declare the `com.google.android.gms.permission.AD_ID` permission.

## 11. Changes to This Policy

We may update this Privacy Policy from time to time. Material changes (anything that would expand the data we collect or how we use it) will be communicated to you through the App or via the email address associated with your Sign in with Apple record, at least 30 days before taking effect.

Non-material updates (typos, clarifications, links) will be posted here with a revised "Last Updated" date.

If you continue using the App after a material change takes effect, you accept the updated policy. If you do not accept it, you may stop using the App at any time and request deletion of your information.

## 12. Contact

For any privacy question, request, or complaint:

**Shhabbir Kagalwala**
Operator, Hifz Musaa'id
Email: shabbir.com@gmail.com

We are based in the State of Texas, United States of America.

---

*This policy is governed by the laws of the State of Texas, USA, without regard to its conflict-of-laws principles, except where applicable consumer-protection law in your jurisdiction provides otherwise. Disputes will be resolved in the state or federal courts located in Texas, subject to your rights under local law.*
