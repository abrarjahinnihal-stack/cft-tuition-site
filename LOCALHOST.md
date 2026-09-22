# CFT Complete Local Backend

This project now includes a free local backend for CFT using **Express** and **SQLite built into Node.js**. No hosting, cloud database, SMS service, or paid API is required for local use.

## Requirements

Install Node.js 22 or newer and pnpm. Node 22.5+ provides the SQLite runtime used by this project.

## First run

From the project folder:

```bash
pnpm install
pnpm dev
```

Open the website at `http://localhost:3000`.

The development command starts both the Vite website and the local API. The API runs on port `4000` and the website proxies `/api` requests to it.

## Local admin

Open `http://localhost:3000/admin/login`.

The default development credentials are:

- Email: `admin@cft.local`
- Password: `ChangeMe123!`

Before real use, set your own values. Linux/macOS example:

```bash
CFT_ADMIN_EMAIL=your-email@example.com CFT_ADMIN_PASSWORD='your-strong-password' pnpm dev
```

On Windows PowerShell:

```powershell
$env:CFT_ADMIN_EMAIL="your-email@example.com"
$env:CFT_ADMIN_PASSWORD="your-strong-password"
pnpm dev
```

## Included features

- Student application form at `/apply?role=student`
- Teacher application form at `/apply?role=teacher`
- SQLite application storage in `data/cft.sqlite`
- Local admin login and cookie session
- Application review and status changes
- Student-teacher matching workflow
- Health endpoint at `/api/health`
- SQLite backup command: `pnpm db:backup`

## Data and privacy

All submitted applications stay in the local `data/cft.sqlite` file. Keep the computer secure and back up the database carefully. Do not share the admin password. The local system is not automatically public on the internet.

## Production-like local run

To build and run the compiled local version:

```bash
pnpm build
pnpm start
```

Then open `http://localhost:4000`.
