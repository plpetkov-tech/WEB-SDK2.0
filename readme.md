# Neo Smartpen Web Pen SDK

The Neo Smartpen Web Pen SDK provides tools and APIs to interact with Neo Smartpen devices via a web interface. This SDK enables developers to build applications that can connect to Neo Smartpens and process their input data in real-time.

---

## Table of Contents

1. [Features](#features)
2. [Installation](#installation)
3. [Getting Started](#getting-started)
4. [Usage](#usage)
5. [API Reference](#api-reference)
6. [License](#license)

---

## Features

- Real-time communication with Neo Smartpens
- Easy integration with web applications
- Comprehensive APIs for data processing
- Cross-browser compatibility

---

## Installation

To use the SDK in your project, you can install it via npm:

```bash
npm install neo-smartpen-sdk
```

Alternatively, you can include it in your project directly using a CDN:

```html
<script src="https://cdn.example.com/neo-smartpen-sdk.min.js"></script>
```

---

## Getting Started

1. Import the SDK into your project:

    ```javascript
    import NeoPenSDK from 'neo-smartpen-sdk';
    ```

2. Initialize the SDK:

    ```javascript
    const penSDK = new NeoPenSDK();
    penSDK.init();
    ```

3. Start listening for pen events:

    ```javascript
    penSDK.on('data', (data) => {
        console.log('Received data from pen:', data);
    });
    ```

4. Connect to a Neo Smartpen:

    ```javascript
    penSDK.connectToPen('pen-id')
        .then(() => console.log('Connected to pen'))
        .catch((error) => console.error('Failed to connect:', error));
    ```

---

## Usage

### Connecting to a Pen

Use the `connectToPen` method to establish a connection:

```javascript
penSDK.connectToPen('pen-id')
    .then(() => {
        console.log('Pen connected');
    })
    .catch((err) => {
        console.error('Connection error:', err);
    });
```

### Receiving Data

Register a listener for real-time pen data:

```javascript
penSDK.on('data', (data) => {
    console.log('Pen data received:', data);
});
```

### Disconnecting

Disconnect from the pen using the `disconnect` method:

```javascript
penSDK.disconnect()
    .then(() => {
        console.log('Disconnected from pen');
    })
    .catch((err) => {
        console.error('Disconnection error:', err);
    });
```

---

## API Reference

### `NeoPenSDK`

- **Methods:**
  - `init()`: Initializes the SDK.
  - `connectToPen(penId)`: Connects to a pen with the specified ID.
  - `disconnect()`: Disconnects the currently connected pen.
  - `on(event, callback)`: Registers an event listener.

- **Events:**
  - `data`: Fired when pen data is received.
  - `error`: Fired when an error occurs.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
