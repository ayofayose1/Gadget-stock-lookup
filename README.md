Gadget Stock Lookup

An n8n automation that checks gadget inventory using Google Sheets, verifies product availability, and suggests in-stock alternatives through webhook responses.

Project Overview

This workflow allows a customer-facing application to submit a gadget search request. It checks the inventory and returns the product’s availability, brand, stock quantity, and price.

If the requested product is unavailable, the workflow retrieves other available products as alternatives.

Technologies Used

* n8n
* Google Sheets
* Webhooks
* Hoppscotch
* JSON

Workflow Features

* Receives product requests through a POST webhook.
* Searches Google Sheets for the requested product.
* Checks product brand and stock availability.
* Returns product details when available.
* Retrieves in-stock alternatives when unavailable.
* Responds with structured JSON.

Project Status

Version 0.2 : Core inventory lookup and alternative product retrieval implemented and tested.

Future Improvements

* Connect a WhatsApp Business interface.
* Add automated inventory updates.
* Improve alternative product recommendations.
* Add customer order processing.