# Business Performance Dashboard

An enterprise-grade banking/business analytics dashboard built with React.js and Material UI (MUI), featuring KPI summary cards, cascading location filters, a sortable/paginated/searchable data grid (MUI X Data Grid), and a right-side drill-down drawer with account-level detail.

## Tech stack

- React 18 + Vite
- Material UI (MUI) v6 + MUI X Data Grid v7
- React Context API (`useReducer`) for state management
- SheetJS (`xlsx`) + `file-saver` for Excel/CSV export
- Mock data layer simulating a real API (see `src/services/api.js`)

## Getting started

```bash
npm install
npm run dev
```

Then open the printed local URL (default `http://localhost:5173`).

To rebuild the mock dataset (102 location records, 520 account records):

```bash
npm run generate-mock-data
```

To build for production:

```bash
npm run build
npm run preview
```

## Folder structure

```
src/
 ├── components/
 │    ├── SummaryCards/        KPI cards (top section)
 │    ├── FilterPanel/         Cascading Province/Region/Area/City filters
 │    ├── BusinessGrid/        MUI X DataGrid: sort, paginate, search, filter, export
 │    ├── AccountDrawer/       Right-side drill-down panel
 │    ├── LoadingSkeleton/     Skeleton loaders for cards & grid
 │    ├── EmptyState/          Empty-result UI
 │    └── ErrorState/          Error + retry UI
 ├── pages/
 │    └── BusinessDashboard/   Page composition
 ├── context/
 │    └── DashboardContext.jsx React Context: filters, grid data, selected row, drawer state
 ├── hooks/
 │    └── useBusinessData.js   Data fetching hook (loading/error/refetch)
 ├── services/
 │    └── api.js               Mock API layer (swap for real endpoints later)
 ├── utils/
 │    ├── exportUtils.js        CSV / Excel export
 │    ├── formatters.js         Currency / number / date formatting
 │    └── maskCnic.js           CNIC masking helper
 ├── theme/
 │    └── theme.js              MUI theme (palette, typography)
 └── mock-data/
      ├── locationHierarchy.json
      ├── businessData.json
      └── accountData.json
```

## Notes on design choices

- **State management**: Context API with `useReducer` was used (per the brief's first option) rather than Redux Toolkit, keeping the dependency footprint smaller while still centralizing filters, grid data, the selected row, and drawer open/close state in one place (`DashboardContext.jsx`).
- **Mock API**: `src/services/api.js` simulates network latency and exposes the same shape a real REST/GraphQL backend would. Swapping in real endpoints later only requires editing this one file.
- **Drill-down**: clicking a grid row opens the drawer and fetches (simulated) account-level records scoped to that row's Province/Region/Area/City.
- **Export**: both grid rows and drawer account lists can be exported to CSV; the grid can also export to Excel (`.xlsx`) via SheetJS.
