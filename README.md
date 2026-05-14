# WhatsApp CRM - Day 1: Wiring Up

This project is a WhatsApp-integrated CRM backend. Day 1 focuses on "Wiring Up"—establishing a secure, verified connection between the Meta Cloud API and a local Express server using a Webhook.

## Features

- Express-based backend server
- WhatsApp webhook verification (Meta Cloud API)
- Incoming webhook listener for WhatsApp updates
- Health endpoint for service status checks
- Placeholder routes for future lead and stats functionality (Days 3-4)
- SQLite database integration ready (better-sqlite3)

## Prerequisites

- Node.js 18+ 
- npm
- ngrok (for local webhook testing)
- Meta WhatsApp Cloud API credentials

## Quick Start

Navigate to the server folder and install dependencies:

```bash
cd whatsapp-crm/server
npm install
```

Create a `.env` file:

```env
META_VERIFY_TOKEN=your_verify_token_here
PORT=3001
```

Start the development server:

```bash
npm run dev
```

The server runs on `http://localhost:3001`

## API Endpoints

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/whatsapp/webhook` | GET | Webhook verification (Meta challenge) |
| `/whatsapp/webhook` | POST | Receive incoming WhatsApp messages |
| `/api/health` | GET | Health check |
| `/api/leads` | GET | Leads management (Day 3) |
| `/api/stats` | GET | Statistics (Day 3) |

## Project Structure

```
whatsapp-crm/
├── server/
│   ├── index.js          # Express app entry point
│   ├── package.json      # Dependencies
│   └── .env             # Environment variables
├── routes/
│   └── whatsapp.js      # WhatsApp webhook routes
└── README.md            # Setup instructions
```

## Testing Locally with ngrok

1. Start the server: `npm run dev`
2. In another terminal, expose your local server:
   ```bash
   ngrok http 3001
   ```
3. Register the ngrok URL + `/whatsapp/webhook` with Meta as your webhook URL
4. Use your `META_VERIFY_TOKEN` in Meta app settings

## Screenshots

### Meta Developer App
![Meta App](./screenshots/day1-meta-app.png)

### Verified Webhook
![Verified Webhook](./screenshots/day1-verified.png)

### Incoming WhatsApp Message
![Inbound Message](./screenshots/day1-inbound.png)

## Stack

- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: SQLite3 (ready for integration)
- **HTTP Client**: Axios
- **Dev Tools**: Nodemon

## Author

Created for WhatsApp CRM integration learning project

## License

ISC
