# Krishna Smile Care — Dental Clinic Dashboard

**Full-stack patient management system** for Krishna Smile Care, Dr. Navaneethakrishnan MDS (Ortho).

## Architecture

| Layer | Tech | Location |
|---|---|---|
| Frontend | React + Vite + Tailwind + TanStack Query + wouter | `artifacts/dental-dashboard/` |
| API | Express + Drizzle ORM + TypeScript | `artifacts/api-server/` |
| Database | PostgreSQL (Replit managed) | `lib/db/` |
| Shared types | Zod schemas, API client (Orval codegen) | `lib/api-zod/`, `lib/api-client-react/` |
| Object Storage | Replit GCS-backed object storage | `artifacts/api-server/src/lib/objectStorage.ts` |

## Features

- **Role-based access control**: Admin / Receptionist / Duty Doctor
- **Charge locking**: Non-admins cannot edit treatment costs from previous days (midnight boundary)
- **X-ray uploads**: PNG/JPG/PDF via presigned GCS URLs; stored per patient
- **PDF invoices**: Client-side jsPDF with clinic header, itemized treatments, footer
- **Patient management**: Registration, OPD number auto-generation (`OPD-00001`)
- **Treatment tracking**: Record, update, mark paid/cancelled
- **Dashboard**: KPI tiles, revenue chart, treatment breakdown, OPD quick-search
- **Staff management**: Admin can create/delete staff accounts and reset passwords

## Default Login

| Username | Password | Role |
|---|---|---|
| `admin` | `KrishnaSmile@2024` | Administrator |

## User Preferences

- Currency: Indian Rupees (₹), locale `en-IN`
- Color scheme: Pink/mauve primary `hsl(330 58% 48%)`, dark plum sidebar `hsl(330 35% 20%)`
- Clinic footer: "KRISHNA SMILE CARE - SMILES FOR ETERNITY"
- All monetary amounts formatted with `toLocaleString("en-IN")`
