Youtube Demo: https://www.youtube.com/watch?v=6J-sMG3s5ig

# PDF to Google Docs Slide Extractor

A Google Apps Script project to convert PDF slides into images and insert them into a Google Doc, creating a structured note-taking template.  Each slide image is placed in a table alongside a dedicated note-taking area.

## Overview

This project automates the process of extracting lecture slides from a PDF file and inserting them as images into a Google Document.  It's designed to streamline note-taking by creating a visual reference of each slide paired with a corresponding space for notes. The script utilizes the [PDFApp](https://github.com/tanaikech/PDFApp) library by [tanaikech](https://github.com/tanaikech) for efficient PDF processing.

## Features

*   **PDF to Image Conversion:** Converts each page of a PDF file into a PNG image using the `PDFApp` library.
*   **Google Docs Integration:** Creates a new Google Document to host the extracted slides and note-taking areas.
*   **Structured Layout:** Organizes the slides and note areas in a two-column table for clear and organized note-taking.
*   **Image Resizing:**  Automatically resizes the inserted slide images to fit within a specified width (default: 300 pixels), maintaining a consistent aspect ratio based on a typical slide format (16:9).
*   **Easy Note-Taking:** Provides a designated space next to each slide image for adding relevant notes.
*   **Error Handling:** Includes robust error handling to gracefully manage potential issues such as invalid PDF IDs or library errors.
*   **User Feedback:** Uses `Browser.msgBox()` to display informative messages to the user, including the URL of the created document and any error messages that may occur.

## Prerequisites

*   **Google Account:** You need a Google account to use Google Apps Script and Google Drive.
*   **PDF File in Google Drive:** The PDF file you want to convert must be stored in your Google Drive.
*   **PDFApp Library:** This project relies on the `PDFApp` library by [tanaikech](https://github.com/tanaikech).  You must install this library in your Google Apps Script project.

## Installation

1.  **Create a Google Apps Script Project:**
    *   Open Google Drive ([https://drive.google.com/](https://drive.google.com/)).
    *   Click "New" > "More" > "Google Apps Script".

2.  **Install the `PDFApp` Library:**
    *   In the Script editor, go to "Resources" > "Libraries".
    *   Enter the following Project key: `1Xmtr5XXEakVql7N6FqwdCNdpdijsJOxgqH173JSB0UOwdb0GJYJbnJLk`
    *   Click "Add".
    *   Select the latest version of the library.
    *   Click "Save".
  
4.  **Copy the Script Code:**  Copy the complete script code (provided below) into the Google Apps Script editor.

5.  **Replace the Placeholder:**  In the script, replace `"YOUR_PDF_FILE_ID_HERE"` with the actual ID of your PDF file in Google Drive.  See "Finding the PDF File ID" below for instructions.

6.  **Run the Script:**
    *   Select the `convertPDFToImagesAndCreateDoc` function in the script editor.
    *   Click the "Run" button.
    *   Authorize the script when prompted. You will need to grant the script permissions to access your Google Drive and create Google Docs.

## Finding the PDF File ID

1.  Open Google Drive and locate your PDF file.
2.  Right-click on the PDF file and select "Get link" or "Share".
3.  Copy the link. The File ID is the long string of letters and numbers in the URL between `/d/` and `/view?`.
    *   Example: `https://drive.google.com/file/d/YOUR_FILE_ID_HERE/view?usp=sharing`

## Customization

*   **`maxImageWidth`:**  Adjust this value (in pixels) to control the maximum width of the inserted slide images.  This affects the overall layout of the document and the space available for notes.
*   **`slideAspectRatio`:**  Modify this value to match the aspect ratio of your slides.  The default is `16 / 9` (widescreen).  Use `4 / 3` for older slides.
*   **Table Styling:** You can further customize the table's appearance (e.g., borders, cell padding) by modifying the script to use the Google Docs API's table styling options.

## Troubleshooting

*   **"No images were generated from the PDF"**: This usually means the PDF file is either corrupted or doesn't contain any raster images.  Try opening the PDF in a PDF viewer to verify its contents.  Also, double-check that the PDF ID is correct.
*   **Authorization Errors:**  Make sure you have granted the script the necessary permissions to access your Google Drive and create Google Docs.  If you accidentally denied permissions, you can revoke them in your Google account settings and then re-run the script.
*   **Script Execution Timeout:**  For very large PDFs, the script might exceed the maximum execution time allowed by Google Apps Script.  Consider splitting the PDF into smaller files or using a more powerful server-side solution.

## Known Limitations

*   **Aspect Ratio Assumption:**  The script assumes a fixed aspect ratio for all slides.  Slides with significantly different aspect ratios might be slightly distorted.
*   **Google Apps Script Quotas:** Google Apps Script has daily quotas for API usage. If you process a large number of PDFs, you might hit these quotas.
*   **Complex PDFs:** The `PDFApp` library might have trouble converting very complex PDFs with unusual formatting or embedded elements.

## License

This project is licensed under the MIT License - see the [LICENCE](LICENCE) file for details.

## Credits

*   This project utilizes the excellent [PDFApp](https://github.com/tanaikech/PDFApp) library by [tanaikech](https://github.com/tanaikech).

## Contributing

Contributions are welcome! Please submit a pull request with any bug fixes, improvements, or new features.

