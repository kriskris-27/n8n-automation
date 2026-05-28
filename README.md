Vitto Fintech Operations Automation
Overview
An automated n8n pipeline designed to streamline Vitto's document processing. The workflow monitors a dedicated Google Drive folder for new PDFs, extracts text, utilizes Google Gemini (1.5 Flash) to generate structured operational insights, and automatically archives the data into a Google Sheet for tracking.

Tech Stack
Workflow Engine: n8n

AI Service: Google Gemini (1.5 Flash via Google AI Studio API)

Integrations: Google Drive, Google Sheets, Gmail

Workflow Structure
Trigger: Polls Google Drive for new files in the designated /Fintech-Uploads folder.

Process: - Downloads the binary file.

Extracts text content.

Passes text to Gemini LLM with a strictly defined JSON-output system prompt.

Output: Appends structured data (Entity, Type, Operational Impact, Deadlines, Next Steps) to a Google Sheet.

Error Handling: Configured to catch extraction errors and log failures to prevent workflow crashes.

How to Re-import & Run
Import: Open your n8n instance and click Import from File, selecting the provided workflow.json.

Credentials: - Re-authenticate your Google Account (OAuth2) for the Drive, Sheets, and Gmail nodes.

Create a free API key at aistudio.google.com and paste it into the Google Gemini Chat Model credential.

Setup:

Ensure the Google Sheets API is enabled in your Google Cloud Console.

Create a new Google Sheet with headers: Company, Type, Operational Impact, Deadlines & Terms, and Next Steps.

Update the Spreadsheet ID and Folder ID in the respective nodes to match your local setup.

Execute: Drop a PDF into your Drive folder and click Execute Workflow in n8n to test the end-to-end integration.