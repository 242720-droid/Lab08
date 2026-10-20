
# Lab 08 — NestJS Dependency Injection, DTOs and Validation

## Requirements
Node.js 18+ and npm.

## Run
```bash
npm install
npm run start:dev
```
API base URL: `http://localhost:3000/api`.

## Environment options
- `STORAGE=file` (default) persists students/courses to JSON; set `STORAGE=memory` to use in-memory stores.
- `LOG_TO_FILE=true` writes timestamped application logs to `logs/app.log`.
- `FEE_POLICY=standard` calculates credit-hours × rate; `FEE_POLICY=merit` applies CGPA discounts.
- `FEE_RATE` is not needed; the lab's fixed rate is 5000 PKR per credit hour.

PowerShell:
```powershell
$env:STORAGE="memory"; $env:LOG_TO_FILE="true"; $env:FEE_POLICY="merit"; npm run start:dev
```
macOS/Linux:
```bash
STORAGE=memory LOG_TO_FILE=true FEE_POLICY=merit npm run start:dev
```

## Tests
```bash
npm test
npm run test:e2e
```
## Important
The screenshots folder includes a checklist. Run the app/tests and capture your own genuine terminal/Postman screenshots before submission. The project does not fabricate evidence screenshots.
