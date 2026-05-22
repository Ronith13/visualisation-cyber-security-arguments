# Visualisation of Logical Cyber Security Arguments

**An ePassport Security Case Study**

> MSc Advanced Computer Science with Data Science — University of Strathclyde, Glasgow  
> Student: Ronith Naveen Kumar (202357131)  
> Supervisor: Professor Lisa McCann

---

## Overview

This repository contains all materials for the MSc dissertation:

> *"Visualisation of Logical Cyber Security Arguments: An ePassport Security Case Study"*

The research investigates how **interactive visualisation** of formal Attack-Defence Trees and Dung-style argumentation semantics can improve understanding of cybersecurity arguments, using ePassport (ICAO 9303) security as a case study.

---

## 🚀 Live Demo — Try the Prototype

**Open `prototype/epassport_visualiser.html` directly in your browser — no installation needed.**

The tool features:
- Interactive Attack-Defence Tree with real-time argumentation labelling
- Toggle individual defences (BAC/PACE, Active Auth, PKI, Random UID, EAC)
- Live IN/OUT status recomputation using Dung's grounded semantics
- Threat Matrix and Argumentation Status views
- Click any node for detailed ICAO reference and DREAD score

---

## Repository Structure

```
├── README.md
│
├── prototype/
│   └── epassport_visualiser.html     ← Interactive tool (open in browser)
│
├── dissertation/
│   ├── dissertation_FULL.docx        ← Complete dissertation (all chapters)
│   └── dissertation_outline.docx    ← Project roadmap and chapter plan
│
├── chapters/
│   ├── chapter1_introduction.docx
│   ├── chapter2_literature_review.docx
│   ├── chapter3_methodology.docx
│   ├── chapter4_framework.docx
│   ├── chapter5_implementation.docx
│   ├── chapter6_evaluation.docx
│   ├── chapter7_discussion.docx
│   └── chapter8_conclusion.docx
│
└── evaluation/
    ├── eval_01_consent_form.docx
    ├── eval_02_background_questionnaire.docx
    ├── eval_03_sus_comprehension.docx
    ├── eval_04_interview_guide.docx
    └── eval_05_marking_scheme.docx   ← Researcher use only
```

---

## Theoretical Foundations

| Concept | Reference |
|---|---|
| Attack Trees | Schneier (1999) |
| Attack-Defence Trees (ADTs) | Kordy et al. (2010, 2012) |
| Abstract Argumentation | Dung (1995) |
| Grounded Labelling Semantics | Dung (1995) |
| ePassport Standard | ICAO Doc 9303 (2021) |
| EAC / Biometric Protection | BSI TR-03110 |

---

## ePassport Threat Model

### Attacks (6 nodes across 3 vectors)

| Attack | Vector | DREAD | Defeated By |
|---|---|---|---|
| RFID Skimming | RF Interface | 7.2 | BAC / PACE |
| Eavesdropping | RF Interface | 6.4 | BAC / PACE |
| Chip Cloning | Data Integrity | 9.1 | Active Authentication |
| Data Forgery | Data Integrity | 8.8 | PKI / Passive Auth |
| Holder Tracing | Privacy | 7.6 | Random UID |
| Biometric Theft | Privacy | 9.4 | Extended Access Control |

### Defences (5 nodes)

| Defence | Standard | Defeats |
|---|---|---|
| BAC / PACE | ICAO 9303 Part 11 | RFID Skimming, Eavesdropping |
| Active Authentication | ICAO 9303 §6.1 | Chip Cloning |
| Passive Auth / PKI | ICAO 9303 Part 12 | Data Forgery |
| Random UID | ISO/IEC 14443-3 | Holder Tracing |
| Extended Access Control | BSI TR-03110 | Biometric Theft |

---

## Argumentation Semantics

The tool implements **Dung's (1995) grounded labelling semantics**:

```
Attack a is OUT  iff  ∃ active defence d such that (d, a) ∈ defeats
Attack a is IN   iff  no active defence defeats it
Root Goal is OUT iff  all leaf attack nodes are OUT
```

Labels are recomputed in **O(n)** time on every user interaction.

---

## Evaluation

The prototype is evaluated against static reference materials using:
- **System Usability Scale (SUS)** — 10-item validated usability instrument
- **Comprehension Assessment** — 4 questions mapped to Bloom's taxonomy
- **Semi-structured interviews** — thematic analysis of user experience

Pilot results (n=5): SUS 82.5 (interactive) vs 61.0 (static); Comprehension 6.4/8 vs 4.2/8.

---

## How to Run the Prototype

1. Clone or download this repository
2. Open `prototype/epassport_visualiser.html` in any modern browser
3. No server, no installation, no internet connection required

```bash
git clone https://github.com/YOUR_USERNAME/visualisation-cyber-security-arguments.git
cd visualisation-cyber-security-arguments
open prototype/epassport_visualiser.html
```

---

## Citation

If you reference this work:

```
Naveen Kumar, R. (2025) 'Visualisation of Logical Cyber Security Arguments: 
An ePassport Security Case Study'. MSc Dissertation, University of Strathclyde.
```

---

## License

This project is submitted as academic work. All rights reserved.  
© 2025 Ronith Naveen Kumar, University of Strathclyde.
