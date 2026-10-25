# LabelLoupe Privacy Policy

**Effective date:** 25 October 2026  
**Product:** LabelLoupe: FODMAP & IBS Scan  
**Developer / operator:** `TODO: Legal entity name` (“we”, “us”, “our”)  
**Contact:** `TODO: privacy@labelloupe.app`  
**App Store Privacy Policy URL:** host this document at a stable HTTPS URL (for example `https://labelloupe.app/privacy`).

This Privacy Policy explains what information LabelLoupe (“the App”) processes, how it is used, and the choices you have. Please read it carefully.

**Important — not medical advice**  
LabelLoupe is an **optical ingredient reading aid** for educational and informational convenience. It is **not** a medical device, is **not** intended to diagnose, treat, cure, or prevent any disease, and is **not** a substitute for advice from a qualified clinician or registered dietitian. Always inspect physical product packaging yourself. If you have a severe or life-threatening food allergy (including IgE-mediated allergy / anaphylaxis risk), **do not rely on the App** for safety decisions. See [Section 12](#12-important-notices-not-medical-advice).

---

## 1. Scope

This policy applies to:

- The LabelLoupe iOS application (`com.labelloupe.app`) and its widget / App Intent extensions  
- Optional network features described below (rule dictionary updates; opt-in feedback)  
- This document as published for App Store Connect and user reference  

It does **not** cover third-party websites, Apple’s own services (App Store, iCloud, Apple Intelligence), or other apps, except as those services interact with LabelLoupe as described here. Apple’s handling of payment and account data is governed by Apple’s privacy policies.

---

## 2. Summary

| Topic | Our practice |
|---|---|
| LabelLoupe account | **None.** No sign-up, no password, no LabelLoupe user ID. |
| Tracking / ads | **No.** No advertising identifier, no ad networks, no cross-app tracking. |
| Camera & OCR | Processed **on your device** to read ingredient text and highlight matches. |
| Dietary profile & scan history | Stored **on your device** (and optionally in **your** iCloud if enabled). |
| Purchases | Processed by **Apple** via StoreKit. We do not receive your full payment card details. |
| Analytics / crash vendors | **None** built into the App at this time. |
| Children | Not directed at children under 13 (see [Section 10](#10-children)). |

Apple’s App Privacy “nutrition label” for LabelLoupe should match this policy. The binary privacy manifest (`PrivacyInfo.xcprivacy`) declares **no tracking** and, by default, **no collected data types** in the App Privacy report sense, except as you opt into feedback that leaves the device (see [Section 6](#6-optional-features-that-may-leave-your-device)).

---

## 3. Information we process

### 3.1 Information processed only on your device

The following is created or used locally to operate the App. It is **not** uploaded to LabelLoupe servers as part of ordinary scanning:

| Category | Examples | Purpose |
|---|---|---|
| Camera frames / OCR text | Live or still images of packaging; recognized ingredient strings | Detect and highlight dietary trigger phrases for your selected profile |
| Dietary profile | Low FODMAP, Celiac/Coeliac, Low Histamine, Dairy-Free, custom exclusions; onboarding acknowledgement | Personalize which rules apply |
| Scan history | Product name you enter, transcript, trigger counts, notes, Safe List favorites, timestamps | Let you review past scans |
| Free-scan quota | Remaining free committed analyses | Enforce the free-trial scan limit (stored in a way intended to survive reinstall; see Keychain note below) |
| App preferences | UI settings, TipKit state, last checked rules version | App functionality |
| Bundled rules | Ingredient / additive rules and citations shipped in the App | Matching and educational rationales |

**Keychain:** A free-scan counter may be stored in the iOS Keychain so that deleting and reinstalling the App does not necessarily reset the trial. This is stored on-device (and subject to Apple’s Keychain / device backup behavior), not on a LabelLoupe account server.

**UserDefaults / App Group:** The App may use UserDefaults (including an App Group shared with the widget) for preferences such as the last rules-update check. This is declared in the privacy manifest under the UserDefaults accessed-API reason used for app functionality.

### 3.2 Information we do not collect by default

Under normal use (scanning labels, viewing history, using Free scans), LabelLoupe does **not**:

- Create a LabelLoupe login or profile on our servers  
- Sell personal data  
- Use your camera feed for advertising  
- Share scan history with other users  
- Require location, contacts, microphone, or photo library access for core scanning (photo library is used **only** if you choose **Import / Choose label photo**)

---

## 4. Camera and photo library

**Camera**  
Access is requested when you start scanning. Purpose: read and highlight ingredient text on packaging in real time. Processing is designed to run **on-device**. Camera permission can be changed anytime in iOS Settings.

**Photo library**  
Used only if you voluntarily pick a photo (for example when the camera is unavailable). The selected image is processed on-device for OCR / analysis. We do not upload your photo library wholesale.

---

## 5. Purchases (StoreKit)

In-App Purchases (Lifetime Unlock and optional Monthly Pass) are processed by **Apple**. Apple may provide us with purchase / entitlement status needed to unlock features (for example via StoreKit transaction verification). We do not receive your full credit card number. Refunds and subscription management are handled through Apple (Settings → Subscriptions, or App Store support).

---

## 6. Optional features that may leave your device

### 6.1 Optional iCloud sync (Apple)

On non-Simulator builds, local SwiftData (dietary profile, saved scans, pending feedback tickets stored locally) may sync through **Apple CloudKit / iCloud** using **your** Apple ID when iCloud is enabled for the App. That sync is between your devices and Apple’s iCloud infrastructure. It is not a LabelLoupe account. You can manage iCloud in system Settings. Simulator builds use local storage without CloudKit.

### 6.2 Optional rules dictionary update (network)

When online, the App may periodically request a public **rules manifest** and, if a newer validated rules file is available, download it to keep ingredient synonyms current. This request is for app functionality. It is not used to build an advertising profile. The update is applied only after local validation.

### 6.3 Optional “Flag misclassified” feedback (you choose to send)

If you submit a misclassification report, the App may queue a ticket that includes:

- A ticket identifier  
- Related rule identifier  
- OCR text snippet you are reporting about  
- Your optional note  
- App version and device locale  

Tickets are stored locally first and sent only when connectivity is available to our feedback endpoint (configured as `https://feedback.labelloupe.app/feedback` in the client). **If you never submit feedback, this data is not sent.**

If this endpoint is enabled in production, we treat submitted content as **user-provided content** used solely to improve ingredient classification. Do not include sensitive personal information in notes. We may retain submissions for a limited period to investigate and improve rules, then delete or anonymize them when no longer needed.

If feedback is disabled or limited to a local / mailto-only flow in a given release, nothing is posted to that endpoint; App Store privacy answers should match that configuration.

### 6.4 System logs

On-device logging (for example via Apple’s unified logging) may record operational messages for debugging on your device. We do not operate a third-party analytics SDK that automatically uploads usage events.

---

## 7. How we use information

We use information only to:

1. Provide scanning, matching, history, and unlock features  
2. Enforce free-scan limits and restore legitimate purchases  
3. Improve ingredient rules when you opt in to feedback  
4. Comply with law or protect rights if legally required  

We do **not** use camera content or dietary profiles for advertising or cross-app tracking.

---

## 8. Sharing

We do not sell personal information.

We may share information only as follows:

| Recipient | When |
|---|---|
| **Apple** | Purchases, iCloud sync you enable, OS-level processing (including Apple Intelligence / FoundationModels when available on your device) |
| **Service operators we control** | Only to receive opt-in feedback or host public rules files, under our instructions |
| **Legal** | If required by valid legal process, or to protect users, us, or the public from harm or fraud |

Government or law-enforcement requests will be evaluated under applicable law. We will not provide data we do not have (for example, we cannot produce a LabelLoupe “account profile” that does not exist).

---

## 9. Retention and deletion

| Data | Retention |
|---|---|
| On-device history / profile | Until you delete items, clear app data, or delete the App (subject to iCloud backups you control) |
| Keychain free-scan counter | May persist after App deletion until cleared by system / device reset behavior |
| Opt-in feedback we receive | Retained only as long as needed to review and improve rules, then deleted or de-identified |
| Purchase records | Entitlement status as provided/retained via Apple’s commerce systems |

**Your controls:**

- Delete individual history entries in the App  
- Turn off camera / photo access in iOS Settings  
- Disable iCloud for the App in system Settings  
- Delete the App  
- Manage subscriptions and purchase history with Apple  
- Contact us (`TODO: privacy@labelloupe.app`) to request deletion of **feedback you submitted to us**, identifying approximate date and content if possible  

Because we do not run a LabelLoupe user account database for scanning, we generally cannot “export an account.” Data that exists only on your device must be deleted by you on that device (and in iCloud if synced).

---

## 10. Children

The App is not directed to children under 13 (or the minimum age required in your jurisdiction). We do not knowingly collect personal information from children. If you believe a child has submitted feedback containing personal information to us, contact us and we will delete it.

---

## 11. International users and security

Processing primarily occurs **on your device**. Optional network features use HTTPS. If you use iCloud, Apple may store synced data in regions Apple operates. No method of transmission or storage is perfectly secure; we apply reasonable technical and organizational measures appropriate to a zero-account, on-device design, but we cannot guarantee absolute security.

---

## 12. Important notices (not medical advice)

To reduce misunderstanding and legal risk, the following is stated clearly:

1. **Not a medical device.** LabelLoupe is software for reading and highlighting printed ingredient text. It is not FDA/CE-cleared (or equivalent) as a medical device.  
2. **Not professional advice.** Output is not medical, dietary, or legal advice.  
3. **Not allergy-safe certification.** Matching is based on text rules and may miss reformulations, OCR errors, incomplete labels, regional naming, or ingredients not in the dataset.  
4. **Always verify packaging.** Especially for severe allergies, celiac disease management decisions, or medically prescribed diets, rely on the physical label and qualified professionals.  
5. **Citations are educational.** Peer-reviewed or regulatory citations linked from rules support category-level classification for label scanning; they are not a personal clinical assessment.  
6. **You assume responsibility** for how you use the App’s highlights when shopping or eating.

Nothing in this Privacy Policy creates a doctor–patient or dietitian–client relationship.

---

## 13. Your privacy rights

Depending on where you live (for example GDPR/UK GDPR, CCPA/CPRA, or other laws), you may have rights to access, correct, delete, or restrict certain personal data, or to object to certain processing, and to lodge a complaint with a supervisory authority.

Because LabelLoupe is designed to keep ordinary scanning data on-device (and in your iCloud if you enable it), many rights are exercised by using device controls. For personal data we actually hold (typically **opt-in feedback** you sent us), contact `TODO: privacy@labelloupe.app`. We will respond within the time required by applicable law. We may need enough information to locate your submission and will not discriminate against you for exercising rights.

If a regional “Do Not Sell or Share” right applies: **we do not sell or share personal information for cross-context behavioral advertising.**

---

## 14. Third-party services

| Service | Role |
|---|---|
| Apple App Store / StoreKit | Distribution and payments |
| Apple iCloud / CloudKit | Optional sync of local app data you enable |
| Apple Vision / FoundationModels | On-device text recognition and optional on-device language features |
| Rules / feedback hosts (if enabled) | Public rules files; opt-in feedback intake |

Those providers process data under their own terms and privacy policies when you use their services.

---

## 15. Changes to this policy

We may update this Privacy Policy from time to time. The **Effective date** at the top will change when we do. Material changes will be highlighted in the App Store “What’s New” notes or in-app notice when appropriate. Continued use after the effective date means you acknowledge the updated policy.

---

## 16. Contact

Privacy questions, feedback-deletion requests, or concerns:

- **Email:** `TODO: privacy@labelloupe.app`  
- **Postal / legal entity:** `TODO: full legal name and address`  

For App Store billing issues, contact Apple Support.

---

## 17. Operator checklist before publishing this URL

Complete before using this document as the live App Store Privacy Policy:

- [ ] Replace all `TODO:` fields (legal entity, email, address)  
- [ ] Confirm whether production feedback webhook is **on** or **off** and align Section 6.3 + App Store privacy answers  
- [ ] Confirm CloudKit is enabled for release builds as described  
- [ ] Host this file on HTTPS and paste the URL into App Store Connect  
- [ ] Have counsel review if you require jurisdiction-specific clauses (EEA representative, California notice at collection, etc.)  

This document is provided to describe LabelLoupe’s intended data practices accurately. It is **not** a substitute for legal advice tailored to your company and markets.
