# Zakkaart Anesthesiemedewerkers (AM)

A comprehensive digital reference tool for anesthesia workers, designed for quick access to critical information during perioperative care.

## Overview

**Zakkaart AM** is a web-based pocket card application built for anesthesia professionals at the **Amsterdam Medical Center (AMC)** and **VU Medical Center (VUMC)**. It provides instant access to standardized dosing, contact directories, medication color codes, and clinical protocols—all optimized for mobile devices in the operating theater.

**Version**: Mei 2026

## Features

### 🎨 Medication Color Coding
Color-coded medication system conforming to physical label rolls used in the OR:
- **Yellow**: Induction agents (Propofol, Thiopental, Ketamine, Sevofluraan)
- **Light Blue**: Opioids (Sufentanil, Remifentanil, Fentanyl, Morfine)
- **Red**: Muscle relaxants (Rocuronium, Succinylcholine, Atracurium)
- **Purple**: Anticholinergics & Sympatholytics (Atropine, Efedrine, Glycopyrronium)
- **Orange**: Sedatives & Non-opioid analgesics (Midazolam, Metamizol, Paracetamol)
- **Tan**: Local anesthetics (Lidocaïne, Bupivacaïne)
- **Dark Red**: Antagonists (Sugammadex, Naloxone, Neostigmine, Flumazenil)
- **Beige/Brown**: Antiemetics (Ondansetron, Dexamethason, Droperidol)
- **White**: Antibiotics (Cefazoline, Metronidazol)

### 📱 iOS-Style Scroll Picker
Intuitive drum roller interface for:
- **Age selection**: 1 month to 18 years
- **Weight selection**: 3–80 kg

### 📋 Clinical Content

#### Medication References
- **Standard dosing** - Common perioperative medications with induction/maintenance doses
- **Detailed medication table** - Concentration, volume, duration, and clinical notes
- **Pediatric medications** - Age-appropriate dosing for children
- **Emergency medications** - Adrenaline, Atropine, Defibrillation protocols

#### Hospital Systems
- **Phone directories** - AMC and VUMC contact lists organized by department
- **Shift codes** - Shift names and hours for both hospitals
- **OR specializations** - Operating theater assignments by surgical specialty
- **Building sections** - AMC layout guide with departments by building (A–Q)

#### Laboratory & Clinical Protocols
- **Blood tube types** - 17 tube types with anticoagulants, volumes, order numbers, and clinical purposes
- **ABCDE Protocol** - Systematic airway, breathing, circulation, disability, exposure assessment
- **Vital sign ranges** - Pediatric heart rate, blood pressure, respiration by age
- **Blood gas values** - Normal ranges for pH, pO₂, pCO₂, HCO₃⁻, Base Excess, O₂ saturation
- **Ventilation parameters** - Tidal volume, EtCO₂, frequency, PEEP targets
- **SBAR handoff** - Structured communication template (Situation, Background, Assessment, Recommendation)

#### Schiphol Board (OR Scheduling)
Color-coded patient flow phases for operating theater scheduling

#### Emergency Numbers
- Fire: 8888
- Resuscitation: 2222
- Central desk: 9

### 🌓 Theme Support
- Dark mode (default) for OR environments
- Light mode (respects system preferences or data-theme attribute)

## Technology Stack

- **Frontend Framework**: React 18.2 (CDN)
- **React DOM**: 18.2 (CDN)
- **JavaScript Compiler**: Babel Standalone 7.23
- **Styling**: Inline CSS with custom properties
- **Deployment**: Static HTML file

## Installation & Usage

### Local Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/spijkerjaap-cloud/zakkaart-am.git
   cd zakkaart-am
   ```

2. Open `index.html` in a modern web browser:
   ```bash
   # macOS
   open index.html
   
   # Linux
   xdg-open index.html
   
   # Or simply double-click the file
   ```

### Deployment
The application is a single static HTML file with no build process required:
- Upload `index.html` to any web server
- Serve over HTTP or HTTPS
- No dependencies to install
- Works offline once loaded

### Mobile Access
Optimize for mobile use:
- Add to home screen on iOS/Android
- Configured as a PWA-compatible web app
- Full-screen capability on mobile devices
- No scrollbars, optimized touch interactions

## Customization

Edit data directly in `index.html`:

### Update Version
```javascript
const VERSIE = "Mei 2026";  // Line 190
```

### Modify Phone Directories
```javascript
const TELEFOON_AMC = {
  vast: [
    { naam: "OK-balie", nummer: "63313" },
    // Add or edit entries...
  ],
  // ...
};
```

### Add Medications
Add to `MED_KLEUREN` object (line 195):
```javascript
"Medication Name": { bg: "#HexColor", text: "#TextColor" }
```

### Update Dosing Tables
Modify `MEDICATIE_DETAIL` array (line 881):
```javascript
{
  categorie: "Category Name",
  kleur: "#HexColor",
  meds: [
    { 
      naam: "Drug Name", 
      dosis: "X–Y mg/kg", 
      obv75: "75kg dose", 
      // ...
    }
  ]
}
```

## Clinical Protocols

### ABCDE Assessment
Quick reference for post-operative monitoring:
- **A (Airway)**: Tube placement, patency, resistance
- **B (Breathing)**: SpO₂, EtCO₂, thorax excursion
- **C (Circulation)**: HR, BP, MAP, urine output
- **D (Disability)**: Anesthesia depth, glucose, post-op alertness
- **E (Exposure)**: Temperature, inspection for complications

### SBAR Communication
Structured handoff template for patient transitions

### Standard Weight Calculation
Automatic calculation based on age (1 month to 18+ years)

## Browser Compatibility

- ✅ Chrome/Edge 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Mobile Safari (iOS 14+)
- ✅ Chrome Mobile (Android 9+)

## Features Highlights

### Collapsible Sections
All data organized in expandable cards:
- State persists during session
- Color-coded headers by category
- Smooth open/close animations

### Responsive Design
- Optimized for small screens (operating theater)
- Touch-friendly interface
- Full-width responsive layout
- Vertical scrolling with smooth scroll physics

### No Dependencies
- Runs entirely in the browser
- No external API calls
- Offline-capable after first load
- CDN-hosted React/Babel libraries

## Data Sources

- **Medications**: AMC Anesthesiology Department (T.M.S. van Winden, 2016)
- **Laboratory**: Centraal Diagnostisch Laboratorium (updated 06-08-2022)
- **Phone Numbers**: AMC & VUMC internal directories (May 2026)
- **Clinical Protocols**: Hospital-specific anesthesia workflows

## Development Notes

### Code Structure
- Single HTML file with embedded React/Babel
- All data defined as JavaScript constants
- Component-based UI (Collapse, ScrollPicker, etc.)
- Inline styling for portability

### Key Functions
- `calcStandardWeight(ageYears)` - Pediatric weight estimation
- `getMedKleur(naam)` - Medication color lookup
- `Collapse` component - Collapsible card wrapper
- `ScrollPicker` component - iOS-style selector

## License

Internal use only for Amsterdam Medical Center anesthesia department.

## Support

For updates or corrections, contact the anesthesiology department at AMC.

---

**Last Updated**: Mei 2026  
**Optimized For**: AMC & VUMC Operating Theaters
