# SEC Stock Data Viewer

This project provides a single-page, responsive web application built with HTML and Tailwind CSS that displays common stock shares outstanding data for publicly traded companies, fetched directly from the SEC EDGAR API. The application is capable of dynamically loading data for different companies based on their Central Index Key (CIK).

## Features

*   **Dynamic Data Fetching**: Retrieves real-time company concept data from the SEC EDGAR API.
*   **CIK-driven Content**: Displays data for a default company (Align Technology) or any company specified via a URL parameter (`?CIK=...`).
*   **Key Financials at a Glance**: Highlights the highest and lowest common stock shares outstanding for fiscal years greater than 2020.
*   **Responsive Design**: Built with Tailwind CSS, ensuring a consistent and appealing user experience across various devices.
*   **Single-File Application**: All application logic and styling are contained within a single `index.html` file for easy deployment.

## How to Use

1.  **Clone the Repository (or save `index.html` locally)**:
    Save the `index.html` content to a file named `index.html` on your local machine.

2.  **Open in Browser**:
    Simply open the `index.html` file with your web browser.

3.  **View Default Data**:
    By default, the application will display data for **Align Technology (CIK: 0001097149)**.

4.  **View Data for Other Companies**:
    To view data for a different company, append `?CIK=` followed by the company's 10-digit CIK to the URL in your browser.
    *   Example for **Align Technology**: `file:///path/to/index.html` or `http://localhost/index.html`
    *   Example for **Apple Inc.**: `file:///path/to/index.html?CIK=0000320193`
    *   Example for **Microsoft Corp.**: `file:///path/to/index.html?CIK=0000789019`

    The application will automatically fetch and update the displayed information without requiring a page reload.

## Technology Stack

*   **HTML5**: Structure of the web page.
*   **Tailwind CSS (CDN)**: Utility-first CSS framework for rapid and responsive styling.
*   **JavaScript (ES6+)**: For fetching data from the SEC API, processing it, and dynamically updating the DOM.
*   **SEC EDGAR API**: Primary data source for company financial information.
*   **allorigins.win**: A CORS proxy used for client-side API requests to bypass cross-origin restrictions.

## SEC API User-Agent Note

When making requests to the SEC EDGAR API, it is recommended to set a descriptive `User-Agent` header to identify your application. For client-side `fetch` requests, especially when using a CORS proxy like `allorigins.win`, directly controlling the `User-Agent` sent to the target SEC server is generally not possible from the browser due to security restrictions. The proxy itself may apply its own `User-Agent` or simply pass the browser's default. For server-side implementations, a custom `User-Agent` (e.g., `YourCompanyName YourEmail@example.com`) should always be provided.

## License

This project is open-sourced under the MIT License. See the `LICENSE` file for more details.
