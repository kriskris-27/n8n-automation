VITTO OPERATIONS INTERN ASSESSMENT: SYSTEM WRITE-UP

What was built:
An end-to-end automated document parsing engine that monitors inbound operational files via Google Drive, extracts their content, structures key insights using GenAI, and publishes them immediately to Google Sheets for the operations team.

Tool Choices & Justification:
- Engine: n8n. Offers highly visual data lineage tracking and granular node execution control.
- LLM Layer: Google Gemini 1.5 Flash. Picked for its exceptional speed, high token context windows, and generous free tier capabilities.
- Storage: Google Sheets. Provides an immediate, low-friction tabular interface for operations monitoring.

Limitations & Edge Cases:
- Scope Constraints: Currently uses a Google ecosystem baseline (Drive + Sheets). 
- PDF Type: Native text PDFs process flawlessly. Hand-scanned, heavily blurred documents or images would fail text extraction without an OCR pre-processing layer.

Next Steps / Production Roadmap:
1. Multi-Service Branching: Expand the destination layer to include external notification pathways like Discord webhooks or Slack messaging.
2. Granular Error Logging: Route extraction failures to a dedicated administrative error log tab in Google Sheets using automated IF/THEN routing parameters to track corruption events.