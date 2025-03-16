# Hooker Integration

**Hooker** is a powerful integration tool that connects GoHighLevel CRM data with Google Sheets and Facebook Business assets. This application enables seamless data flow between platforms and provides a clean interface for managing your integration.

![Hooker Integration Logo](generated-icon.png)

## Features

- **GoHighLevel Integration**: Connect to your GoHighLevel account and access CRM data
- **Facebook Business Integration**: Link your Facebook Business assets including Pages, Ad Accounts, and Instagram accounts
- **Google Sheets Data Storage**: Store and manage integration data using Google Sheets
- **Webhook Support**: Receive and process webhooks from GoHighLevel
- **Custom Reporting**: Generate custom reports based on integrated data
- **User-Friendly Interface**: Clean and intuitive interface for managing integrations

## Documentation

This repository contains comprehensive documentation to help you set up and use the Hooker Integration application:

- [Local Development Guide](LOCAL-DEVELOPMENT-GUIDE.md): Instructions for setting up a local development environment
- [GoHighLevel Setup Guide](SETUP-GOHIGHLEVEL.md): How to create and configure a GoHighLevel Marketplace app
- [Facebook Setup Guide](SETUP-FACEBOOK.md): How to create and configure a Facebook app
- [Deployment Guide](deployment-guide.md): Instructions for deploying the application to Google Apps Script

## Quick Start

### Prerequisites

- Node.js v14 or higher
- npm package manager
- Google account
- GoHighLevel agency account
- (Optional) Facebook Developer account

### Installation

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd hooker-integration
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Configure API credentials:
   - Follow the setup guides to create GoHighLevel and Facebook apps
   - Update the configuration in the server files with your credentials

4. Start the OAuth server:
   ```bash
   node oauth-server.js
   ```

5. Visit `http://localhost:5000` to start using the application locally

## Project Structure

```
hooker-integration/
├── .clasp.json            # Google Clasp configuration
├── .clasprc.json          # Google Clasp authentication
├── Code.gs                # Main Google Apps Script code
├── Index.html             # Main web interface
├── JavaScript.html        # Client-side scripts
├── Styles.html            # CSS styles
├── appsscript.json        # Apps Script manifest
├── oauth-server.js        # OAuth authentication server
├── local-server.js        # Local development server
├── complete-auth.js       # Helper for authentication setup
├── clasp-auth.js          # Google Clasp authentication helper
├── service-auth.js        # Service account authentication
└── README.md              # Project documentation
```

## Authentication Flows

This application uses OAuth 2.0 for authentication with both GoHighLevel and Facebook:

1. **GoHighLevel Authentication**:
   - OAuth 2.0 authorization code flow
   - Scopes include contacts, locations, opportunities, etc.
   - Tokens are securely stored and refreshed as needed

2. **Facebook Authentication**:
   - OAuth 2.0 authorization code flow
   - Scopes include business_management, ads_management, pages_read_engagement, etc.
   - Tokens are securely stored and managed

## Development

For local development:

1. Start the OAuth server:
   ```bash
   node oauth-server.js
   ```

2. Use the authentication URLs provided by the server to authenticate with GoHighLevel and Facebook

3. Make changes to the application code and test locally

4. Use Clasp to push changes to Google Apps Script:
   ```bash
   clasp push
   ```

## Deployment

To deploy the application to Google Apps Script:

1. Follow the [Deployment Guide](deployment-guide.md) for detailed instructions
2. Use Clasp to push your code to Google Apps Script
3. Configure the necessary Script Properties
4. Deploy as a web app and share with users

## Security Considerations

- API keys and secrets are stored securely using environment variables locally and Script Properties in Google Apps Script
- OAuth tokens are managed securely and refreshed as needed
- User data is handled according to data protection regulations

## Support

If you encounter any issues or have questions about the Hooker Integration application, please:

1. Check the documentation in this repository
2. Look for error messages in the server logs
3. Contact support at [your-email@example.com](mailto:your-email@example.com)

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- GoHighLevel for their comprehensive API
- Facebook for their Marketing API
- Google for Google Apps Script and Sheets API
