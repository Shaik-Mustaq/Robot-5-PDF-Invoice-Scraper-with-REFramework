# PDF Invoice Scraper with REFramework

An end-to-end UiPath automation that reads PDF invoice files, sends their file paths to an Orchestrator queue through a Dispatcher, and processes each invoice through a Performer built with the Robotic Enterprise Framework (REFramework). The extracted invoice data is then captured in a Google Sheet using UiPath Integration Service.

## Project Overview

This solution is divided into two UiPath processes:

### 1. Dispatcher

The Dispatcher is a linear UiPath workflow (not an REFramework template).

- Reads the invoice PDF files from the configured input folder.
- Creates Orchestrator queue items using the invoice file paths.
- Makes the invoice files available for the Performer to process.

### 2. Performer

The Performer uses the UiPath REFramework template.

- Retrieves invoice file paths from the Orchestrator queue.
- Processes each queue transaction.
- Scrapes the required information from the PDF invoice.
- Writes the extracted invoice data to a Google Sheet through UiPath Integration Service.
- Uses REFramework transaction handling and exception handling.

## Workflow

1. Place the PDF invoices in the configured input folder.
2. Run the Dispatcher to add the invoice file paths to the Orchestrator queue.
3. Run the Performer.
4. The Performer retrieves each queue item and processes the corresponding PDF invoice.
5. The extracted invoice information is added to the configured Google Sheet.

## Project Structure

```text
Robot-5-PDF-Invoice-Scraper-with-REFramework/
│
├── PDF Invoice Scraper with REFramework Dispatcher/
│   └── Dispatcher project files
│
└── PDF Invoice Scraper with REFramework Perfomer/
    ├── Data/
    │   └── Input/
    │       └── PDF invoice files
    ├── Output-Screenshots/
    │   └── Screenshots of the Excel output and published processes
    └── Performer project files
```

> The folder names above reflect the project folders in this repository. The `Data\Input` folder is used for the invoice files, and `Output-Screenshots` contains project evidence.

## Output Screenshots

The `Output-Screenshots` folder inside the Performer project contains screenshots showing:

- **Excel Output** – an example of the extracted invoice data.
- **Dispatcher Publish** – the published Dispatcher process.
- **Performer Publish** – the published Performer process.

Open the [Output_Screenshots folder](./PDF%20Invoice%20Scraper%20with%20REFramework%20Perfomer/Output-Screenshots/) to view the screenshots.

## Technologies Used

- UiPath Studio – 2026.0.204
- UiPath Orchestrator – queue-based transaction processing
- UiPath REFramework – Performer transaction processing
- UiPath Integration Service – Google Sheets integration
- PDF invoice processing and data extraction
- JSON configuration (`config.json`)

## Configuration

The project uses `config.json` for configuration in the current UiPath Studio project setup.

Before running the automation, review the configuration and make sure that:

- The invoice input folder path is valid.
- The Orchestrator queue name and related settings match your environment.
- The Google Sheets connection and destination spreadsheet are configured.
- Any required credentials or connection assets are available in the appropriate secure UiPath configuration.

Do not commit passwords, access tokens, client secrets, or other sensitive credentials to the repository.

## Prerequisites

- UiPath Studio 2026.0.204 or a compatible version.
- Access to a UiPath Orchestrator tenant.
- The required Orchestrator queue created and configured.
- A configured UiPath Integration Service connection for Google Sheets.
- Access to the destination Google Sheet.
- PDF invoice files for processing.

## How to Run

1. Clone or download this repository.
2. Open the Dispatcher project in UiPath Studio.
3. Check its `config.json` and confirm the input folder and Orchestrator queue settings.
4. Publish and run the Dispatcher.
5. Open the Performer project in UiPath Studio.
6. Check its `config.json`, Orchestrator queue settings, and Google Sheets integration.
7. Ensure the required Orchestrator and Integration Service connections are available.
8. Publish and run the Performer.
9. Verify that the extracted invoice data appears in the configured Google Sheet.

## Learning Outcomes

This project demonstrates:

- Building a Dispatcher–Performer automation.
- Using Orchestrator queues to pass work between processes.
- Implementing REFramework in a Performer process.
- Processing PDF invoices.
- Integrating UiPath with Google Sheets through Integration Service.
- Managing project configuration with `config.json`.
- Publishing UiPath automation processes.

## Author

**Mustaq Shaik**

GitHub: [Shaik-Mustaq](https://github.com/Shaik-Mustaq)

## Project Portfolio

Explore more of my projects on my portfolio:

[View the project
portfolio](https://www.notion.so/p/Shaik-Mustaq-s-UiPath-Project-Portfolio-37c6bf78bd76838a8d9e01defb6a0288)

## Repository

[Robot 5 – PDF Invoice Scraper with REFramework](https://github.com/Shaik-Mustaq/Robot-5-PDF-Invoice-Scraper-with-REFramework)
