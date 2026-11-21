# Shape Squad Diet Chart Generator

A browser-based tool for building, reviewing, and sharing meal plans. Create a diet chart with meal timings, food portions, calories, and macronutrients, then print it or export it as a PDF or Excel workbook.

**Live app:** [r3con-ng.github.io/Diet-chart](https://r3con-ng.github.io/Diet-chart/)

## Features

- **Meal planning:** add, duplicate, reorder, and remove meal rows. Record the meal time, food, portion, protein, fats, carbohydrates, and calories.
- **Calorie tracking:** calculate meal calories automatically from macros using `4 × protein + 4 × carbohydrates + 9 × fat`, or switch to manual calorie entry.
- **Food suggestions:** search a built-in list of common foods to fill in portion and nutrition values.
- **Daily nutrition summary:** see daily macro and calorie totals, with visual macro breakdowns by grams or calories.
- **Client and trainer details:** include client information, the plan date, a goal, and trainer notes.
- **Print and export:** print a landscape chart, save it as a PDF, or export the data to Excel.
- **Mobile-friendly layout:** use compact meal cards and the same editing controls on phones and tablets.
- **Installable and offline-capable:** install the app as a PWA; previously cached app resources remain available offline.
- **Local data storage:** client charts and gym details are saved in the browser’s local storage on the device.

## Getting started

The app is static HTML, CSS, and JavaScript. There is no build step or package installation.

1. Clone or download this repository.
2. Start a local web server from the project directory:

   ```bash
   python3 -m http.server 8000
   ```

3. Open [http://localhost:8000](http://localhost:8000) in a browser.

Serving the files over HTTP enables service worker and offline features. The app loads its charting, PDF, spreadsheet, and font libraries from CDNs.

## How to use

1. Enter client and trainer details.
2. Add or edit meals and their nutrition values. Calories update automatically from the macros by default; turn off **Auto-calc** to edit calories directly.
3. Review the daily totals and macro breakdown.
4. Print the chart or export it as a PDF or Excel file.

Use **Edit Info** to update the gym profile and logo. The **New Client** action resets the client chart to the default meal plan.

## Project files

| File | Purpose |
| --- | --- |
| `index.html` | App structure, controls, and dialogs |
| `app.js` | Chart state, meal editing, calculations, rendering, and exports |
| `style.css` | Desktop, mobile, and print layouts |
| `sw.js` | PWA installation, caching, and offline behavior |
| `manifest.json` | Installable app metadata |
| `logo.png` | Default Shape Squad branding and app icon |

## Technology

The app uses plain JavaScript with no framework or build tool. External libraries are loaded from CDNs:

- [D3.js](https://d3js.org/) for nutrition visualizations
- [html2canvas](https://html2canvas.hertzen.com/) and [jsPDF](https://github.com/parallax/jsPDF) for PDF export
- [SheetJS](https://sheetjs.com/) for Excel export
- Barlow Condensed and DM Sans fonts from Google Fonts

## Data and privacy

Client chart data and gym profile settings are stored in the browser’s local storage. They are not sent to an application server. Exported files are generated in the browser. Clearing site data in the browser removes saved charts and settings.

## Contributing

Issues and pull requests are welcome. For changes to the app, include a brief description of the behavior affected and the devices or browsers you checked.

## License

This repository does not currently include a license file. Public availability on GitHub does not itself grant permission to reuse or redistribute the code.
