Gadget Stock Lookup — Testing Documentation

Overview

This document records the tests performed on the Gadget Stock Lookup n8n workflow.

The workflow receives product requests through a POST webhook, checks the Google Sheets inventory, and returns product availability or alternative products.

Test Environment

* Automation platform: n8n
* Inventory database: Google Sheets
* API testing tool: Hoppscotch
* HTTP method: POST
* Webhook path: gadget-stock-lookup

Test 1: Product Available

Input:

{
  "product": "iphone 16",
  "brand": "Apple"
}

Inventory condition:

The iPhone 16 had a stock quantity of 5.

Expected result:

* Status should be available.
* Product and brand should match the request.
* Stock quantity and price should be returned.
* A success message should be included.

Observed result: PASS

The webhook returned HTTP 200 with the correct product details, stock quantity, price, and availability message.

Test 2: Product Out of Stock

Input:

{
  "product": "iphone 16",
  "brand": "Apple"
}

Inventory condition:

The iPhone 16 stock quantity was temporarily changed to 0.

Expected result:

* Status should be unavailable.
* The requested product should be identified.
* The workflow should retrieve alternative products that are in stock.

Observed result: PASS

The workflow returned an unavailable status and retrieved alternative products.

Test 3: Alternative Product Retrieval

Inventory condition:

The workflow retrieved the inventory records and filtered out products with zero stock and the originally requested product.

Expected result:

* Only available alternative products should be included.
* Alternatives should be returned together in an array.
* The customer should be able to see multiple alternatives in one response.

Observed result: PASS

The response contained an alternatives array with available products.

Conclusion

The core Gadget Stock Lookup workflow successfully passed the three tests.

It can:

* Receive product requests through a webhook.
* Search inventory using Google Sheets.
* Check product availability and stock quantity.
* Return product details when available.
* Retrieve and return in-stock alternatives when unavailable.

Project version: 0.2