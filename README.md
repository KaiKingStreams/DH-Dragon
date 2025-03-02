# Project Setup Guide

This guide will walk you through setting up the necessary environment variables and configurations required for this project.

## Prerequisites

Before proceeding, ensure you have the following:

- A valid bot token
- A MongoDB database connection string
- API keys for weather and image commands
- Webhook URLs (if needed)
- Spotify API credentials

## Environment Variables

Create a `.env` file in the root directory and add the following configurations:

```env
# Bot Token [Required]
BOT_TOKEN=your_bot_token_here

# Mongo Database Connection String [Required]
MONGO_CONNECTION=your_mongo_connection_string_here

# Webhooks [Optional]
ERROR_LOGS=your_error_logs_webhook_here
JOIN_LEAVE_LOGS=your_join_leave_logs_webhook_here

# Dashboard [Required for dashboard]
BOT_SECRET=your_bot_secret_here
SESSION_PASSWORD=your_session_password_here

# Required for Weather Command (https://weatherstack.com)
WEATHERSTACK_KEY=your_weatherstack_api_key_here

# Required for Image Commands (https://strangeapi.hostz.me/dashboard)
STRANGE_API_KEY=your_strange_api_key_here

# Spotify [Required for Spotify Support] (https://developer.spotify.com)
SPOTIFY_CLIENT_ID=your_spotify_client_id_here
SPOTIFY_CLIENT_SECRET=your_spotify_client_secret_here
```

## Setup Instructions

1. Clone the repository:

   ```sh
   git clone <repository_url>
   cd <repository_name>
   ```

2. Install dependencies:

   ```sh
   npm install  # or yarn install
   ```

3. Create and configure your `.env` file:

   - Copy the template above and fill in the required details.

4. Start the bot using `start.bat`:

   - Create a file named `start.bat` in the project root and add the following content:
     ```bat
     @echo off
     title Bot Startup
     echo Starting the bot...
     npm start
     pause
     ```
   - Double-click `start.bat` to run the bot.

## Lavalink Setup

Lavalink is required for music playback in the bot. You need to set up a Lavalink server or use a public one.

### Lavalink Configuration in `config.js`

Instead of adding Lavalink credentials to `.env`, configure them inside `config.js` as follows:

```js
module.exports = {
  lavalink: {
    host: 'your_lavalink_host_here',
    port: your_lavalink_port_here,
    password: 'your_lavalink_password_here'
  }
};
```

### Setting Up Lavalink

1. Download Lavalink from [Lavalink GitHub](https://github.com/freyacodes/Lavalink).
2. Install Java (at least Java 11).
3. Edit the `application.yml` file to configure your host, port, and password.
4. Run Lavalink using the following command:
   ```sh
   java -jar Lavalink.jar
   ```
5. Ensure your bot is correctly configured to connect to Lavalink.

## Websites to Get Required Credentials

- **Bot Token:** [Discord Developer Portal](https://discord.com/developers/applications)
- **MongoDB Connection String:** [MongoDB](https://www.mongodb.com)
- **Weather API Key:** [WeatherStack](https://weatherstack.com)
- **Image API Key:** [StrangeAPI](https://strangeapi.hostz.me/dashboard)
- **Spotify API Credentials:** [Spotify Developer](https://developer.spotify.com)

## Additional Notes

- If using webhooks, make sure to set up the appropriate URLs.
- Ensure all required API keys and credentials are correctly added.
- If you encounter issues, verify your environment variables and API credentials.

### Need Help?

If you run into any issues, feel free to open an issue in the repository or contact support.

Join our Discord server for support: [Discord Server](https://discord.gg/CcNhDGea7M)
If you run into any issues, feel free to open an issue in the repository or contact support.

