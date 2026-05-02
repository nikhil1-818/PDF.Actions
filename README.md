# PDF.Actions
# Table of Contents
Usage Examples
Modify Existing PDFs Get PDFDocument Object
Empty PDF Document
PDF Document From File
PDF Document From Unit8Array/ArrayBuffer
PDF Array from HTML File Object
PDF Array To Blob
Merge PDF
Rotate PDF
Split PDF
Break Single PDF File Into Multiple PDF
Flatten PDF Forms
Resize PDF
Add Margin to PDF
Edit PDF Metadata
Remove PDF Metadata
Add Page Numbers to PDF
JPG To PDF
Installation
Documentation
License
Usage Examples
A Project Made Using pdf-actions is PDFActions : GITHUB Repo
Modify Existing PDFs Get PDFDocument Object
To Modify Esisting PDF Files You Need to First Convert It Into a PDFDocument Object

Empty PDF Document
import { createFileDoc } from "pdf-actions";

const EmptyPDFDocument = await createFileDoc.EmptyPDFDocument();
PDF Document From File
import { createFileDoc } from "pdf-actions";

const PDFDocument = await createFileDoc.PDFDocumentFromFile(file); // file is a HTML File Object from input tag
PDF Document From Unit8Array/ArrayBuffer
import { createFileDoc } from "pdf-actions";

const PDFDocument = await createFileDoc.PDFDocumentFromPDFArray(fileArray); // fileArray is a Unit8Array/ArrayBuffer
PDF Array from HTML File Object
import { pdfArray } from "pdf-actions";

const PDFArray = await pdfArray(file); // file is a HTML File Object from input tag
PDF Array To Blob
import { pdfArrayToBlob } from "pdf-actions";

const PDFBlob = await pdfArrayToBlob(fileArray); // fileArray is a Unit8Array
Merge PDF
import { mergePDF } from "pdf-actions";

const MergedPDFDocument = await mergePDF(filesDocArray); // filesDocArray is a Array of PDFDocument Object
Rotate PDF
import { rotatePDF } from "pdf-actions";

const RotatedPDFDocument = await rotatePDF(fileDoc, degrees);
/*
fileDoc is a PDFDocument Object
degrees is a integer
*/
Split PDF
import { splitPDF } from "pdf-actions";

const SplitPDFDocument = await splitPDF(fileDoc, range, degree);
/*
fileDoc is a PDFDocument Object
range : Page Numbers(both inclusive) is array of two integers - [start,stop]
degree? is a optional parameter and integer
*/
Break Single PDF File Into Multiple PDF
import { breakPDF } from "pdf-actions";

const BreakPDFDocumentsArray = await breakPDF(
  fileDoc,
  pagesInEachFile,
  haveLastPDF,
  degree,
  breakRange
);
/*
fileDoc is a PDFDocument Object
pagesInEachFile is a integer denoting Number of Pages in Each Broken PDF
haveLastPDF is a boolean to whether return the last pdf document irrespective of maxPages
degree? is a optional parameter and integer
breakRange? is a optional paramenter that is a array of two integers [start,stop] that splits the pdf(both inclisive) before breaking it
*/
Flatten PDF Forms
import { flattenPDFForm } from "pdf-actions";

const PDFDocumentWithFormsFlattened = await flattenPDFForm(fileDoc);
/*
fileDoc is a PDFDocument Object
*/
Resize PDF
import { resizePDF } from "pdf-actions";

const PDFDocumentWithFormsFlattened = await resizePDF(
  fileDoc,
  size,
  orientation,
  position,
  degree
);
/*
fileDoc is a PDFDocument Object
size? optional paramenter : string : 2A0 , 4A0 , A[0-10] , B[0-10] , C[0-9] , Executive , Folio , Legal , Letter , RA[0-4] , SR[0-4] , Tabloid 
orientation? optional paramenter : string : Portrait or Landscape
position? optional parameter - Where The Content Should Be : string : Start , Center , End
degree? rotate pdf angle : integer
*/
Add Margin to PDF
import { addMarginPDF } from "pdf-actions";

const AddedMarginPDFDocument = await addMarginPDF(
  fileDoc,
  marginMillimeter,
  degree
);
/*
fileDoc is a PDFDocument Object
marginMillimeter? : optional paramenter : array of length 4
  marginMillimeter[0] -> Left
  marginMillimeter[1] -> Top
  marginMillimeter[2] -> Right
  marginMillimeter[3] -> Bottom
degree? rotate pdf angle : integer
*/
Edit PDF Metadata
import { editMetaData } from "pdf-actions";

const NewMetaDataPDFDocument = await editMetaData(fileDoc, options);
/*
fileDoc is a PDFDocument Object
options = {author,title,creator,keywords,documentCreationDate,documentModificationDate,subject,producer}
*/
Remove PDF Metadata
import { removeMetaData } from "pdf-actions";

const RemovedMetaDataPDFDocument = await removeMetaData(fileDoc);
/*
fileDoc is a PDFDocument Object
*/
Add Page Numbers to PDF
import { addPageNumbers } from "pdf-actions";

const PDFDocumentWithPageNumbers = await addPageNumbers(
  fileDoc,
  pageNumberPosition,
  margin,
  startingPage,
  endingPage,
  startingNumber,
  textSize
);
/*
fileDoc is a PDFDocument Object
pageNumberPosition? : optional : is one of the following string
  - b-l : Bottom Left
  - b-c : Bottom Center : Default
  - b-r : Bottom Right
  - t-l : Top Left
  - t-c : Top Center
  - t-r : Top Right
margin? : optional : is one of the following string
  - Recommended : Default
  - Small
  - Big
startingPage? : optional : is a integer should be >=1 and <=max pages in pdf
endingPage? : optional : is a integer should be >=1 and <=max pages in pdf and >= startingPage
startingNumber? : optional : is a integer denoting the first page number : 1 by default
textSize? : optional 16 by default is a integer
*/
JPG To PDF
import { imageToPDF } from "pdf-actions";

const PDFDocumentFromJPG = await imageToPDF(
  image,
  pageNumberPosition,
  margin,
  startingPage,
  endingPage,
  startingNumber,
  textSize
);
/*
image is a base64 data string
pageSize? : optional : is one of the following string
  - Same as Image
  - 2A0 , 4A0 , A[0-10] , B[0-10] , C[0-9] , Executive , Folio , Legal , Letter , RA[0-4] , SR[0-4] , Tabloid 
pageOrientation? : optional : should pe portrait in case of Same as Image
imagePosition? : optional : should be Start in case of Same as Image
degree? : rotate created PDF
marginMillimeter? : optional paramenter : array of length 4
  marginMillimeter[0] -> Left
  marginMillimeter[1] -> Top
  marginMillimeter[2] -> Right
  marginMillimeter[3] -> Bottom
*/
