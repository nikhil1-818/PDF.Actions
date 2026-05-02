# PDF Utility Toolkit

# A powerful and flexible PDF processing project built using pdf-actions, enabling developers to perform multiple PDF operations directly in JavaScript.

# Features
Create and modify PDF documents
Merge multiple PDFs into one
Split PDFs or break into multiple files
Rotate PDF pages
Resize PDFs and add margins
Add page numbers
Convert JPG images to PDF
Edit and remove PDF metadata
Flatten PDF forms
Handle multiple input types (File, Blob, ArrayBuffer)
Tech Stack
Frontend
JavaScript (ES6+)
Browser File APIs (File, Blob, ArrayBuffer)
Backend (Optional)
Node.js (for server-side processing)
Core Library
pdf-actions
Installation
npm install pdf-actions
Usage Example
import { mergePDF } from "pdf-actions";

const mergedPDF = await mergePDF(filesDocArray);
Supported Inputs
HTML File Object
Uint8Array
ArrayBuffer
Base64 Image Data
Use Cases
Document management systems
PDF editors and converters
Automation tools
Web applications handling file uploads
Highlights
Lightweight and easy to use
Works in both browser and Node.js
No complex setup required
Handles advanced PDF operations with simple functions
