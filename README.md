# Cardano DRep Governance Dashboard

A simple, client-side web interface designed for Cardano **Delegate Representatives (DReps)** to easily track, filter, and manage active governance proposals, voting deadlines, and historical participation.

👉 **Try it Live:** [kostaspanagias.github.io/drep_dashboard](https://kostaspanagias.github.io/drep_dashboard/)

The application runs entirely in the browser, querying blockchain data directly using the Koios API. No servers, databases, or backend logic are required.

---

## 🌟 Key Features

- **Control Panel Dashboard**: Get a high-level statistical overview of governance actions categorized by action types (e.g., Treasury Withdrawals, Parameter Changes, Hard-Fork Initiations, Constitution updates).
- **Proposals Tracker**: Filter actions by status (*Needs Vote*, *Voted*, *Expired*) or by action type. Sort proposals based on expiry deadlines (closest/furthest first).
- **Epoch Progress Tracker**: Visual progress bar tracking the state of the current Cardano epoch in real-time.
- **Cardano Epoch Calendar**: Interactive calendar view highlighting upcoming epoch transitions overlaid on regular calendar months to help you schedule voting windows.
- **Dynamic Metadata Resolution**: Resolves proposal anchor hashes dynamically via IPFS/HTTP gateways, loading titles and details directly into the dashboard.
- **Cardano Explorers Integration**: Quick-links to view transaction details on popular Cardano block explorers like *AdaStat*, *CExplorer*, and *GovTool*.

---

## 🚀 How to Use

### 1. Get a Koios API Key
To retrieve live blockchain data (like proposal lists, active epochs, and DRep history), the dashboard requires an API key from Koios:
1. Go to the [Koios Developer Portal](https://api.koios.rest).
2. Sign up for a free developer account.
3. Generate a **Free Tier API Token**.

### 2. Access the Dashboard
You can run the dashboard in three ways:

* **Option A (No Installation - Live Demo)**: Visit the hosted version directly at [kostaspanagias.github.io/drep_dashboard](https://kostaspanagias.github.io/drep_dashboard/).
* **Option B (Run Locally - Direct File)**: Clone this repository and open `index.html` in any web browser.
  ```bash
  git clone https://github.com/kostaspanagias/drep_dashboard.git
  cd drep_dashboard
  # Open index.html in a web browser
  ```
* **Option C (Run Locally - Server)**: Run a quick local server in the repository directory (to avoid potential browser CORS restrictions with certain file protocols):
  ```bash
  # Python 3
  python -m http.server 8000
  
  # Node.js (npx)
  npx serve
  ```
  Then navigate to `http://localhost:8000` (or the port specified by the command).

### 3. Configure Your DRep Details
1. When you first open the app (or by clicking the **⚙️ Settings** button in the navbar), a configuration modal will appear.
2. Enter your **Koios API Token**.
3. Enter your **DRep ID** (starting with `drep1...`).
4. Toggle your preferred block explorer links (*AdaStat* and/or *CExplorer*).
5. Click **Save & Fetch Data**.

> [!NOTE]
> **Data Privacy & Security**: Your API Token and DRep ID are stored locally in your browser's secure `localStorage`. They are only sent to the official Koios API endpoints to fetch data and are never sent to or stored by any other third party.

---

## 🛠️ Built With

- **HTML5 & CSS3**: Responsive grid layouts, interactive modals, and clean UI styling.
- **Vanilla JavaScript**: Lightweight asynchronous fetching (`fetch`, `Promise.all`), local storage management, and dynamic DOM manipulation.
- **Koios API (v1)**: Robust Cardano blockchain indexing API for fast lookups.
