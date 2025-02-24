# ckptw-wabot - WhatsApp Bot with @mengkodingan/ckptw

> **Notes:** This script has been re-maintained.

## Overview

`ckptw-wabot` is a WhatsApp Bot built using the [@mengkodingan/ckptw](https://ckptw.mengkodingan.my.id/) library. This bot allows you to automate various tasks on WhatsApp, and it supports a modular architecture through commands.

## Features

- **Message Handling:** Handle incoming messages and respond accordingly.
- **Command Parsing:** Parse commands sent by users to trigger specific actions.
- **Interactive Responses:** Provide interactive and dynamic responses to user queries.
- **Media Handling:** Support for sending and receiving media files such as images, videos, and documents.
- **Command System:** Easily extend and customize the bot by adding new commands.

## Getting Started

Follow these steps to set up and run `ckptw-wabot`:

1. **Clone Repository:**
   ```bash
   git clone https://github.com/itsreimau/ckptw-wabot.git
   cd ckptw-wabot
   ```

2. **Install Dependencies:**
   ```bash
   npm install
   ```

3. **Configuration:**
   Copy the `config.example.js` file to `config.js` and update the necessary configuration values, such as Owner number, API key, etc.

4. **Run the Bot:**
   ```bash
   npm start
   ```

5. **QR Code Authentication:**
   Scan the QR code generated by the bot using your WhatsApp mobile app to authenticate.

6. **Start Interacting:**
   Once authenticated, the bot is ready to handle incoming messages and execute commands.

## Customization

### Adding a New Command

To add a new Command, follow these steps:

1. Create a new JavaScript file in the `commands` folder with your desired functionality. For example, `ping.js`:

   ```javascript
   // commands/info-ping.js

   module.exports = {
       name: "ping",
       category: "info",
       code: async (ctx) => {
           const {
               status,
               message
           } = await global.handler(ctx, {
               admin: Boolean,
               botAdmin: Boolean,
               banned: Boolean,
               coin: Number,
               group: Boolean,
               owner: Boolean,
               premium: Boolean,
               private: Boolean
           });
           if (status) return ctx.reply(message);

           return ctx.reply("Pong!");
       }
   };
   ```

2. Your Command is now ready to use. Users can trigger it by sending `/ping` in the chat.

### [Check @mengkodingan/ckptw Documentation](https://ckptw.mengkodingan.my.id/)

For more details on using the underlying library, refer to the [ckptw documentation](https://ckptw.mengkodingan.my.id/).

## Contributions

Contributions are welcome! If you find a bug or have an idea for a new feature, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

---

Feel free to explore, modify, and enhance `ckptw-wabot` to suit your specific needs. Happy coding!
