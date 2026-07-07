# HelpKidz – NFC-Kindersicherheitsarmband

> **Status:** In aktiver Entwicklung / Pre-Launch — End-to-End funktionsfähig auf Staging-Umgebung. Noch nicht öffentlich verkauft.

## Was ist HelpKidz?

HelpKidz ist ein NFC-basiertes Notfallarmband für Kinder. Scannt ein Ersthelfer im Notfall das Armband (per NFC oder QR-Code), sieht er sofort die wichtigsten Notfallinformationen des Kindes — **ohne App, ohne Anmeldung**.

Eltern aktivieren das Armband einmalig über einen privaten Code und pflegen das Notfallprofil in einem geschützten Elternbereich. Datenschutz ist von Grund auf eingebaut: Auf dem Armband selbst liegen keine Kinderdaten. Daten werden erst nach bewusster Eltern-Aktivierung sichtbar.

---

## Features

- 🆘 **Öffentliche Notfallanzeige** — Name, Allergien, Notfallkontakt sofort sichtbar per NFC/QR
- 🔐 **Geschützter Elternbereich** — Login, Profilverwaltung, Aktivierung
- 📦 **Datenschutz by Design** — keine Kinderdaten auf dem Armband, strikte Datentrennung
- 🔁 **Austauschbares Backend** — Mock-Modus oder Supabase per ENV-Variable
- 🛡️ **Sicherheitsarchitektur** — SHA-256-gehashte Aktivierungscodes, httpOnly-Cookies, RLS, anon-RPC

---

## Technologien

| Bereich | Technologie |
|---|---|
| Framework | Next.js 16 (App Router, RSC, Server Actions) |
| Sprache | TypeScript |
| Styling | Tailwind CSS |
| Backend / DB | Supabase (PostgreSQL, RLS, Postgres-RPC) |
| Auth | E-Mail/Passwort, PKCE/OTP-Flows, Custom SMTP |
| Hardware | NFC-Tags + QR-Codes |
| Hosting | Vercel |

---

## Architektur-Highlights

- **Data-Access-Layer** austauschbar: Mock-Backend (lokal, ohne externe Abhängigkeiten) oder Supabase (Produktion) per ENV
- **Middleware Auth-Guard** schützt alle privaten Routen
- **SHA-256-gehashte Aktivierungscodes** — Klartext wird nie gespeichert
- **Öffentlicher Notfall-Read** ausschließlich über eine anon-RPC (kein direkter Tabellenzugriff)
- **Strikte Trennung** von öffentlichem Token und privatem Aktivierungscode

---

## Demo

🌐 Staging-Umgebung: [portal.helpkidz.de](https://portal.helpkidz.de) *(läuft gegen Staging-DB ohne echte Kundendaten)*

> Code auf Anfrage verfügbar. Das Repository ist aktuell privat (Pre-Launch).

---

## Entwickler

**Youssef Azzaoui**
Student der Angewandten Informatik, Hochschule RheinMain Wiesbaden
youssef.azzaoui01@gmail.com
