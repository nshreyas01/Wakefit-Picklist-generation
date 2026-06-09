# Wakefit Hub Picklist Generator & Dispatch Dashboard

A premium, serverless, client-side web application designed to streamline daily warehouse picklist compiles, route consolidations, and driver allocations at the Wakefit BLR Hub.

## 🚀 Overview

In high-volume furniture warehouse operations, dispatch controllers must merge data from multiple sources (Route Planners, CRM Forward Picklists, and Daily Inventory Scans) to allocate loads to drivers and compile clear picklists for warehouse pickers.

This dashboard automates these manual operations entirely in the browser, eliminating copy-paste errors, matching bin/rack locations to SKUs using a sequential FIFO allocation queue, and generating clean, formatted, print-ready spreadsheets for the operational team.

---

## ✨ Features

### 1. Multi-File Drag & Drop Pipeline
- **Route Plan Excel:** Load the daily logistics route planning sheets.
- **CRM Picklist Excel:** Load the raw CRM forward picking records.
- **Inventory Scan (Optional):** Load the daily scan spreadsheet to map physical rack locations (`sloc`) for furniture items.

### 2. Auto-Consolidation & Boards
- **Route Consolidated Boards:** Automatically groups all docket references by their mapped routes (e.g., driver routes, special logistics partners like Bluwheel). Includes a quick **Copy Dockets** feature to copy space-separated reference lists ready for pasting into shipping tools like Shipzy.
- **Carpenter Rider Allocations:** Automatically counts and lists dockets assigned to each rider.
- **Picking Rack Summary:** Lists exact counts of items to be picked from each specific bin location.

### 3. FIFO Storage Location (Sloc) Mapping
- Supports sequential FIFO allocation for inventory locations. If multiple items of the same SKU are scanned in different bins, they are matched sequentially in order to the picklist, preventing bin allocation conflicts.

### 4. Custom Exports
- **Cleaned Picklist (.xlsx):** Downloads a formatted Excel sheet with routed dockets, picker information, date headers, and automatic bold styling for `RT01` / `RTP1` items.
- **Hardware Picklist (.xlsx):** Generates a dedicated spreadsheet for the hardware packing team. It filters strictly for unique `FG01` docket numbers, completely removes duplicate orders, and strips out unnecessary driver and sloc columns, making it print-ready.
- **Scan Cleaning Tool:** Converts and cleans raw inventory barcodes/scans into a structured material-batch-bin format.

---

## 🛠️ Technology Stack

- **Frontend Core:** HTML5, Vanilla JavaScript.
- **Styling:** Vanilla CSS with custom glassmorphism, responsive grid layout, and vibrant glowing states.
- **Icons:** FontAwesome v6.4.0.
- **Fonts:** Google Fonts (Inter & Outfit).
- **Parsing & Generation:** [SheetJS (XLSX)](https://sheetjs.com/) for client-side Excel ingestion and export.

---

## 💻 How to Run Locally

Since this is a client-side serverless utility, it runs directly in the browser without any database or backend server requirement:

1. Clone this repository:
   ```bash
   git clone https://github.com/nshreyas01/Wakefit-Picklist-generation.git
   ```
2. Navigate to the project folder and open `index.html` in any modern web browser (Double-click the file or drag it into Chrome/Edge).
3. Ensure `xlsx.full.min.js` is in the same folder as the HTML file, as it is loaded locally.

---

## 📁 Repository Structure

- `index.html` - The main dashboard utility (UI, styles, and processing logic).
- `xlsx.full.min.js` - SheetJS library for parsing and exporting Excel sheets locally.
- `test_xlsx.html` - A utility script to test Excel file download functionality.

---

## 📝 License

This project is developed for Wakefit Hub logistics optimization.
