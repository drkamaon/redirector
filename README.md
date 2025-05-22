# Redirector

A website that serves as a redirector to comic sites, displaying thumbnails and information in a grid layout.
Or your sins or whatever, all the better for those who see but don't believe.

This project includes two versions:

1. **Vercel Version**: Optimized for deployment on Vercel with serverless functions
2. **Local Version**: Can be run on a local machine without external dependencies

## Features

- Display comic thumbnails and information in a responsive grid
- Search functionality to filter comics
- Sorting options (newest, oldest, alphabetical)
- Infinite scrolling for pagination
- Dark-themed UI for comfortable viewing
- Redirects to original comic pages when clicked

## Vercel Version

The Vercel version uses serverless functions to handle the scraping of comic information from the source website.

### Deployment

1. Clone this repository
2. Navigate to the `vercel` directory
3. Install dependencies:
   ```
   npm install
   ```
4. Deploy to Vercel:
   ```
   npm run deploy
   ```

Alternatively, you can connect your GitHub repository to Vercel for automatic deployments.

### Development

To run the Vercel version locally for development:

```
npm run dev
```

This will start the Vercel development server, which will emulate the serverless functions locally.

## Local Version

The local version uses mock data to simulate the comic information. In a real-world scenario, you would need to implement a proper scraping solution that respects the website's terms of service.

### Installation

1. Clone this repository
2. Navigate to the `local` directory
3. Install dependencies:
   ```
   npm install
   ```

### Running the Local Server

To start the local server:

```
npm start
```

This will start the server at http://localhost:3000

For development with auto-reload:

```
npm run dev
```

## Project Structure

```
redirector/
├── vercel/                 # Vercel-optimized version
│   ├── api/                # Serverless functions
│   │   └── scrape.js       # Comic scraping API
│   ├── css/                # Stylesheets
│   │   └── style.css       # Main stylesheet
│   ├── js/                 # JavaScript files
│   │   └── script.js       # Main script
│   ├── index.html          # Main HTML file
│   └── package.json        # Dependencies and scripts
│
├── local/                  # Local machine version
│   ├── css/                # Stylesheets
│   │   └── style.css       # Main stylesheet
│   ├── js/                 # JavaScript files
│   │   └── script.js       # Main script with mock data
│   ├── index.html          # Main HTML file
│   ├── server.js           # Simple Node.js server
│   └── package.json        # Dependencies and scripts
│
└── README.md               # This file
```

## Customization

To customize the website for different comic sources:

1. Update the `SITE_URL` constant in the JavaScript files
2. Modify the scraping logic in `api/scrape.js` (Vercel version) to match the HTML structure of the target website
3. Update the mock data generator in the local version if needed

## Notes

- This project is for demonstration purposes only
- Make sure to respect the terms of service of any website you scrape
- Consider implementing proper rate limiting and caching to avoid overloading the source website