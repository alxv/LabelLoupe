# LabelLoupe: FODMAP & IBS Scan

**No-barcode AR ingredient lens** for Low FODMAP (IBS), Celiac / Coeliac, Low Histamine, and Dairy-Free shopping.

LabelLoupe reads the **printed ingredients** on packaging with on-device VisionKit OCR—not a cloud barcode database. Hover your camera over a label and watch high, caution, and safe-exception matches highlight in real time. Freeze or stitch curved cans when the text wraps. No account wall. Camera processing stays on your iPhone.

> **Not a medical device.** LabelLoupe is an optical reading aid for educational convenience. It does not diagnose, treat, or certify food safety. Always verify packaging yourself—especially for IgE-mediated allergies. See [Docs/PRIVACY_POLICY.md](Docs/PRIVACY_POLICY.md) and the in-app disclaimer.

---

## What’s new in version 1.0

- Live AR ingredient highlighting for **Low FODMAP**, **Celiac / Coeliac**, **Low Histamine**, and **Dairy-Free** profiles  
- **Freeze & Stitch** for curved cans, foil bags, and hard-to-read packaging  
- On-device matching against a **curated, citation-backed** trigger ruleset (`rulesVersion` 2026.10.2)  
- Optional on-device structured parse via **Apple FoundationModels** when Apple Intelligence is available (deterministic risk classification always)  
- **10 free pantry scans**, then **Lifetime Unlock** or optional **Monthly Pass** (StoreKit 2)  
- Zero-account design; optional iCloud sync via the system Apple ID  
- Photo-import fallback when the camera is unavailable (e.g. Simulator)

---

## Features

| Feature | Detail |
|---|---|
| Live AR scan | VisionKit `DataScannerViewController` + colorblind-safe overlays |
| Deep pass | Freeze / Stitch + parenthetical / “contains 2% or less” parsing |
| Profiles | Low FODMAP, Celiac/Coeliac, Low Histamine, Dairy-Free, custom |
| Offline | Matching and history work without network |
| History | SwiftData scan log + Safe List favorites |
| Monetization | 10 free committed scans → lifetime or monthly IAP |

---

## Stack

- **Swift 6** / **SwiftUI** / **iOS 26+** (minimum deployment as configured in the Xcode project)
- VisionKit live OCR; UIKit bridge for the camera scanner
- `LabelLoupeCore` — Aho-Corasick matcher, deterministic parsers, quota policy
- Apple **FoundationModels** (structured parse when available)
- SwiftData (+ CloudKit on device builds) · StoreKit 2 · TipKit · WidgetKit / App Intents

---

## Open in Xcode

1. Open `LabelLoupe.xcodeproj`
2. Select the **LabelLoupe** scheme (StoreKit config: `LabelLoupe.storekit`)
3. Run on a **physical iPhone** for live camera scanning  
   Simulator uses the branded **Choose label photo** path

Developer Portal / App Store Connect setup: [Docs/DEVELOPER_PORTAL_SETUP.md](Docs/DEVELOPER_PORTAL_SETUP.md)

---

## Tests & rules dataset

```bash
cd Packages/LabelLoupeCore && swift test
```

```bash
python3 Scripts/compile_curated_rules.py
python3 Scripts/validate_rules.py --verify-dois
```

- Sources: [Docs/DATASET_SOURCES.md](Docs/DATASET_SOURCES.md)  
- Clinical promotion gate: [Docs/CLINICAL_REVIEW_CHECKLIST.md](Docs/CLINICAL_REVIEW_CHECKLIST.md)  
- Release builds exclude `draft` rules (`includeDraftRules = false`)

---

## Documentation

| Doc | Purpose |
|---|---|
| [Docs/PRIVACY_POLICY.md](Docs/PRIVACY_POLICY.md) | Privacy policy (App Store URL–ready) |
| [Docs/ASO_AppStoreConnect.md](Docs/ASO_AppStoreConnect.md) | Listing copy, keywords, description |
| [Docs/APP_STORE_CONNECT_METADATA.md](Docs/APP_STORE_CONNECT_METADATA.md) | Full ASC populate checklist |
| [Docs/API_CONTRACTS.md](Docs/API_CONTRACTS.md) | OTA rules + feedback webhook contracts |
| [LabelLoupe_documents.md](LabelLoupe_documents.md) | Product / architecture spec |

---

## Privacy (short)

- **No LabelLoupe account.** No advertising ID. No tracking.  
- **Camera / OCR** processed on-device for scanning.  
- **Purchases** via Apple StoreKit.  
- **Optional** iCloud sync of local app data via your Apple ID.  
- **Optional** misclassification feedback leaves the device **only if you submit it**.  

Full policy: [Docs/PRIVACY_POLICY.md](Docs/PRIVACY_POLICY.md)

---

## License

`TODO:` Add your chosen open-source or proprietary license before publishing the repository.
