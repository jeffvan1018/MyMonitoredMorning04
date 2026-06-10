# Vision and Scope Document: My Monitored Morning (V1)

## 1. Vision Statement
To provide a secure, simple, and flexible web-based daily journal that empowers individuals and their delegated caregivers to track, categorize, and filter personal medical and wellness data over time.

---

## 2. Target Audience
*   **Primary Users (Patients/Individuals):** Individuals tracking their own chronic illnesses, symptoms, daily habits, or general wellness.
*   **Caregivers:** Family members, guardians, or healthcare assistants who need to log medical events, meals, or symptoms on behalf of the primary user, with delegated permission access.

---

## 3. Scope (In-Scope Features for V1)

### 3A. Secure Multi-User Access & Delegation
*   **User Authentication:** Secure registration and login using Firebase/Firestore-based authentication.
*   **Role-Based Delegation:**
    *   Primary users can generate or delegate access permissions to specific caregivers.
    *   Caregivers can switch profiles to view or write journal entries on behalf of the individuals they care for.
    *   Audit tracking: Every journal entry must record *who* created it (the patient themselves vs. a specific caregiver).

### 3B. Flexible & Tag-Based Data Entry
*   **Dynamic Tagging:** Users and caregivers can categorize entries using custom, user-defined tags (e.g., `#bloodGlucose`, `#seizure`, `#meal`, `#bowelMovement`).
*   **Rich Journal Entries:** Each entry should support:
    *   Date and Time (timestamp).
    *   A main text field/notes area.
    *   Multiple dynamic tags.
    *   Author attribution (e.g., "Logged by Caregiver John").

### 3C. Master-Detail Journal Interface (CRUD)
*   **Daily Timeline (Master View):** A chronologically ordered, advanceable list of daily journal entries.
*   **Entry Detail View:** Clicking an entry drills down into its full details, metadata, and tags.
*   **Full CRUD Lifecycle:** Users can:
    *   **Create** new entries (with auto-timestamps or customizable times).
    *   **Read** past entries in detail.
    *   **Update** existing entries (maintaining history or an "edited" status if needed).
    *   **Delete** entries (with confirmation dialogs).

### 3D. Dynamic Multi-Dimensional Filtering
*   **Attribution Filtering:** Filter entries by who logged them (Self vs. Caregiver X).
*   **Tag Filtering:** Search/filter entries by one or more specific tags (e.g., show only `#seizure` and `#bloodGlucose` entries).
*   **Date Range Filtering:** Easily narrow down records to a specific week, month, or custom date range.

---

## 4. Non-Goals / Out-of-Scope (Deferred to Future Versions)
*   **External Data Integrations:** No automatic weather, fitness tracker API (e.g., Fitbit/Apple Health), or external sensor integrations.
*   **Social & Community Sharing:** No public feeds, social media sharing, or patient community integrations. All data remains private to the user and their delegated caregivers.
*   **Advanced Analytics/AI:** No predictive modeling, automated medical advice, or AI-generated trend summaries in V1 (only raw filtering and timeline navigation).

---

## 5. Architectural & Technical Constraints
*   **Platform:** Web-based, responsive interface designed to work on both desktop and mobile viewports.
*   **Front-end Design:** Premium, cohesive, modern aesthetic (not a standard bootstrap look) emphasizing visual accessibility (high contrast options, readable typography).
*   **Database & Auth:** Firebase/Firestore Authentication for user registration/delegation, and Firestore Database for real-time document storage.
*   **Hosting & Deployment:** Structured for local development, with paths and configurations that support standard Google Cloud serverless hosting (e.g., Firebase Hosting, Cloud Run) for smooth deployment.
