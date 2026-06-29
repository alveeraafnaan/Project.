# SuitesOps - Hotel Operations Management System

A web-based hotel operations management system built for **RK Suites** (Hyderabad). It replaces manual paper-based front desk registers, provides precise payment & dues tracking, provides daily analytics, tracks supplies inventory with alerts, and provides a staff activity log for management accountability.

## Tech Stack
- **Frontend**: React.js with Vite
- **Styling**: Premium Custom Vanilla CSS (Slate & Indigo glassmorphism, responsive grid layouts)
- **Backend**: Node.js & Express
- **Database**: Local JSON database with transactional file-write utilities (zero configuration required)
- **PDF Export**: jsPDF integration for invoice downloads

---

## Pre-configured Demo Accounts

Use these accounts to log in and test role-based access control (RBAC):

| Role | Username | Password | Full Name | Permissions |
| :--- | :--- | :--- | :--- | :--- |
| **Manager** | `manager` | `manager123` | Jakkola Manisha | Full access (Logs, analytics, inventory modifications, check-ins/outs) |
| **Front Desk** | `frontdesk` | `frontdesk123` | Gurrampally Ganesh | Front desk operations only (Check-in/out, payment entries, read-only inventory) |

---

## Features Implemented

1. **Digital Guest Register**:
   - Check-in form with fields for Name, ID details, Phone number, Room allocation, and dates.
   - Interactive Room Status Grid showing Available vs. Occupied rooms. Clicking an available room opens the check-in modal.
   - Searchable and filterable guest list (filter by Checked-in, Checked-out, or Overdue departures).
2. **Payments & Dues Ledger**:
   - Balance calculator per guest: `Total Charges (Days * Rate) - Payments Received`.
   - Add new payments (Cash, Card, UPI) with reference logs.
   - Restrict check-out trigger with confirmations if guest has outstanding dues.
3. **Inventory Status Dashboard**:
   - Live tracking of supplies (Linen, toiletries, minibar snacks, water bottles).
   - Warnings when stock falls below thresholds.
   - Restock quantity panel (Manager role only).
4. **Daily Analytics & Reports**:
   - Occupancy rate calculations.
   - Financial summaries (Revenue collected today and current month) restricted to Manager role.
   - Daily Check-in & Check-out counters.
5. **Staff Activity Log**:
   - Real-time audit trail logs recording check-ins, check-outs, payment recordings, and log-ins with operator timestamps (Manager role only).
6. **PDF Invoice Export**:
   - Instant receipt generation on checkout using `jsPDF` capturing guest details, accommodation breakdown, payments history, and net dues.

---

## How to Run the Project Locally

Follow these quick commands to spin up the client and server concurrently:

1. **Start Development Server**:
   ```bash
   npm run dev
   ```
   This will concurrently spin up:
   - Express backend server on: `http://localhost:5000`
   - Vite React development server on: `http://localhost:5173` (with proxy forwarding `/api` requests to backend)

2. **Access application**:
   Open your browser and navigate to the Vite URL (usually `http://localhost:5173`).
