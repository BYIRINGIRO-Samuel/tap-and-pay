# 💳 RFID Dashboard - team_07

A modern and intuitive RFID card management system built with Node.js, Express, and WebSocket technology. This dashboard allows users to view their card balance in real-time and perform top-up transactions seamlessly.

## 🌐 Live Site

Access the application here: **[http://157.173.101.159:9210](http://157.173.101.159:9210)**

## ✨ Features

- **Real-time Updates**: WebSocket-based live balance updates
- **Card Detection**: Automatic RFID card detection and display
- **Top-up Functionality**: Easy balance top-up with instant confirmation
- **MQTT Integration**: Connected to MQTT broker for card status updates
- **Modern UI**: Clean black and white design with smooth animations
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Status Feedback**: Real-time success and error messages

## 🛠️ Technology Stack

- **Backend**: Node.js with Express.js
- **Real-time Communication**: WebSocket (WS)
- **IoT Integration**: MQTT Protocol
- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Port**: 9210

## 📋 Project Structure

```
card/
├── backend.js          # Express server & WebSocket handler
├── index.html          # Dashboard UI
├── card.ino            # Arduino RFID card reader code
├── package.json        # Dependencies
└── README.md           # This file
```

## 🚀 Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm

### Installation

```bash
# Install dependencies
npm install

# Start the server
node backend.js
```

The server will start on `http://localhost:9210`

## 📡 How It Works

1. **Card Detection**: The Arduino-based RFID reader detects card UIDs and publishes them to the MQTT broker
2. **WebSocket Connection**: The client connects via WebSocket to receive real-time balance updates
3. **Balance Management**: Balances are stored on the backend and synchronized across all connected clients
4. **Top-up API**: POST requests to `/topup` endpoint update card balances

## 🔌 API Endpoints

### POST `/topup`

Add funds to a card

**Request Body:**

```json
{
  "uid": "card_uid_here",
  "amount": 100
}
```

**Response:**

```json
{
  "uid": "card_uid_here",
  "balance": 150
}
```

## 🔗 WebSocket Events

- **Connection**: Establishes real-time communication with server
- **Message**: Receives card UID and balance updates
  ```json
  {
    "uid": "card_uid_here",
    "balance": 150
  }
  ```

## 🎨 UI Design

- **Color Scheme**: Black and white minimalist design
- **Responsive**: Optimized for all screen sizes
- **Accessibility**: Clear feedback and error messages
- **Performance**: Smooth animations and instant updates

## 📦 Dependencies

- `express`: Web server framework
- `ws`: WebSocket library
- `mqtt`: MQTT client
- `cors`: Cross-origin resource sharing
- `body-parser`: Request body parsing

## 👥 Team

Developed by **team_07**

## 📝 License

ISC
