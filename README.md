# Ghostlly Server

MoneyChat is a real-time chat application designed for instant communication. It allows users to join chat rooms, send messages, share files, and see typing indicators.

[![Build Status](https://img.shields.io/travis/com/your-username/moneychat.svg?style=for-the-badge)](https://travis-ci.com/your-username/moneychat)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg?style=for-the-badge)](https://opensource.org/licenses/ISC)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg?style=for-the-badge)](https://semver.org)

## Tech Stack

This project is built with the following technologies:

*   **Backend:** Node.js
*   **Framework:** Express.js
*   **Real-time Communication:** Socket.IO
*   **Database:** MongoDB
*   **Middleware:** CORS
*   **Development:** Nodemon

## Features

*   **Real-time Messaging:** Instantly send and receive messages in chat rooms.
*   **Room-based Chat:** Create or join rooms for topic-based discussions.
*   **User Presence:** Get notifications when users join or leave a chat room.
*   **Typing Indicators:** See when another user is typing a message.
*   **File Sharing:** Share files with other users in the chat room.

## Installation Guide

To get a local copy up and running, follow these simple steps.

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/your-username/moneychat.git
    ```
2.  **Navigate to the project directory:**
    ```sh
    cd moneychat
    ```
3.  **Install NPM packages:**
    ```sh
    npm install
    ```

## Usage Instructions

To start the server, run the following command:

```sh
npm start
```

For development, you can use `nodemon` to automatically restart the server on file changes:

```sh
npm run dev
```

The server will start on `http://localhost:5000` by default.

## Configuration

This project uses a `.env` file for environment variables. Create a `.env` file in the root of the project and add the following variables:

```
PORT=5000
```

## API Documentation

The application uses Socket.IO for real-time communication, not a traditional REST API. Below are the main socket events used:

*   **Connection:**
    *   `connection`: Fired when a client connects to the server.

*   **Room Events:**
    *   `join_room`: Allows a user to join a specific chat room.
        *   **Payload:** `{ room: 'roomName', name: 'userName' }`

*   **Message Events:**
    *   `send_message`: Fired when a user sends a message.
        *   **Payload:** `{ room: 'roomName', author: 'userName', message: 'Hello!' }`
    *   `receive_message`: The event clients should listen for to receive messages.
        *   **Payload:** `{ author: 'userName', message: 'Hello!' }`

*   **File Sharing Events:**
    *   `send_file`: Fired when a user sends a file.
        *   **Payload:** `{ room: 'roomName', author: 'userName', filename: 'file.txt', file: <Buffer> }`
    *   `receive_file`: The event clients should listen for to receive files.
        *   **Payload:** `{ author: 'userName', filename: 'file.txt', file: <base64String> }`

*   **Typing Indicator Events:**
    *   `typing`: Fired when a user starts typing.
        *   **Payload:** `{ room: 'roomName', name: 'userName' }`
    *   `stop_typing`: Fired when a user stops typing.
        *   **Payload:** `{ room: 'roomName', name: 'userName' }`

*   **Disconnection:**
    *   `disconnect`: Fired when a client disconnects.

*Caption: The main chat interface.*

## Contact / Support

If you have any questions or need support, feel free to reach out:

*   **Email:** [yeasararefin007@gmail.com](mailto:yeasararefin007@gmail.com)
*   **Portfolio:** [yeasararefin.vercel.app](https://yeasararefin.vercel.app)
