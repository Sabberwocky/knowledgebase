**Grobe Projekt-Übersicht (für erste Partner-Gespräche)**

**1) Gesamtbild: Was ist „Recordo“?**

Recordo ist eine Plattform für **Dokumenten- und Automations-Workflows** (z.B. Audio/Datei rein → KI/Extraktion → strukturiertes Ergebnis → PDF/Output).

Sie besteht aus drei Hauptteilen:

- **Mobile App**: Apps/Recordo (React Native)
- **Admin Web UI**: Apps/Recordo-Admin (Next.js)
- **Backend API**: Services/Recordo-API (Node.js/Express)

Ergänzend existiert (plattformseitig) ein separater Processing-Stack („Switchboard“), der die eigentliche Dokumentverarbeitung übernimmt (Job Queue / Transkription / Rendering), und vom Backend angesteuert wird.

**2)** **Apps/Recordo** **(Mobile App)**

- **Status:** Near Feature complete for P1. Needs bugfixing and some polishing (design and workflow).
- **Technologie**: React Native + TypeScript
- **Architektur**:
    - Redux Toolkit als State-Management
    - RTK Query für API Calls
    - React Navigation für Auth-Flow und App-Navigation
- **Kernfunktionen**:
    - Auth (JWT + Social Login)
    - Dokument-Erstellung (Audio aufnehmen / Medien hochladen)
    - Anzeige von Dokumenten/Status
    - Realtime Updates (Socket.IO Client)
    - Subscriptions / IAP (iOS/Android)

**3)** **Apps/Recordo-Admin** **(Admin Panel)**

- **Status:** Needs bugfixing. Might need the one or other extension for first release. Heavy development for next phase expected.
- **Technologie**: Next.js (App Router) + TypeScript
- **UI**: TailwindCSS + MUI
- **State/API**: Redux Toolkit + RTK Query (zentrale Endpoint-Definition in services.ts)
- **Auth-Konzept**: Cookie-basierte Session (z.B. session) + Route-Protection via middleware.ts
- **Kernmodule**:
    - Dashboard/Analytics
    - User/Customer Management
    - Rollen & Berechtigungen
    - Templates (Dokument + E-Mail)
    - Plans/Subscriptions
    - Notifications (Push, geplant/History)
    - Feedback/Bug Reports
    - System Settings (z.B. Switchboard URLs/Keys)

**4)** **Services/Recordo-API** **(Backend)**

- **Status:** Generally done and feature complete. Might need the one or other bugfix or optimization when we find something before going live. A bit of development for next phase expected.
- **Technologie**: Node.js + Express (primär JavaScript)
- **Datenbank**: MongoDB (Mongoose)
- **Auth**: JWT, Apple/Google Sign-In
- **Realtime**: Socket.IO (serverseitig)
- **Storage/Integrationen**:
    - S3-kompatibler Storage (z.B. Linode Object Storage)
    - Push Notifications (Firebase/FCM)
    - Mail (Nodemailer)
    - Cloud Drives (Google Drive / OneDrive / iCloud je nach Modul)
- **Kernlogik**:
    - Dokument-Workflow: Upload → Request an Processing-Service (Switchboard) → Polling/Status → Ergebnis speichern
    - Subscription-/Minutes-System inkl. Bonus-Minuten und Deduction-Middleware
    - Admin-Routen für Management-Funktionen

**5) Zusammenspiel (typischer End-to-End Flow)**

- **Mobile App** oder **Admin** triggert einen Prozess via **Recordo-API**
- API validiert Auth/Subscription/Minutes und lädt ggf. Dateien hoch
- API schickt Job an Processing-Komponente (Switchboard) und überwacht Fortschritt
- Ergebnisse werden an Clients zurückgeliefert
- Realtime-Updates via Socket.IO