# my-chat-bot

Skype chatbot

This bot has been created using [Bot Framework](https://dev.botframework.com), it shows how to create a simple bot that accepts input from the user and echoes it back.

## Prerequisites

- [Node.js](https://nodejs.org) version 10.14.1 or higher

    ```bash
    # determine node version
    node --version
    ```

## To run the bot

- Install modules

    ```bash
    npm install
    ```

- Start the bot

    ```bash
    npm start
    ```

## Testing the bot using Bot Framework Emulator

[Bot Framework Emulator](https://github.com/microsoft/botframework-emulator) is a desktop application that allows bot developers to test and debug their bots on localhost or running remotely through a tunnel.

- Install the Bot Framework Emulator version 4.9.0 or greater from [here](https://github.com/Microsoft/BotFramework-Emulator/releases)

### Connect to the bot using Bot Framework Emulator

- Launch Bot Framework Emulator
- File -> Open Bot
- Enter a Bot URL of `http://localhost:3978/api/messages`

## Deploy the bot to Azure

To learn more about deploying a bot to Azure, see [Deploy your bot to Azure](https://aka.ms/azuredeployment) for a complete list of deployment instructions.
After deploying get the APPID and APPPassword. 
Change the example.env to .env and paste the values.
## Code Explaination 

1. Environment Variables: Load environment variables from a .env file. These variables include the bot's Microsoft App ID, password, type, and tenant ID. 
 
2. Server Setup:  Sets up an HTTP server using restify. The server listens on a port specified by the environment variable port or PORT, or defaults to 3978 if neither is set. 
 
3. Bot Authentication:  Creates a ConfigurationServiceClientCredentialFactory with the Microsoft App credentials. This factory is used to create a botFrameworkAuthentication object, which is used to authenticate the bot with the Bot Framework service. 
 
4. Bot Adapter:  Creates a CloudAdapter with the botFrameworkAuthentication object. The adapter is responsible for sending and receiving messages from the user. 
 
5. Error Handling: sets up an error handler for the adapter. If an error occurs during a turn of the conversation, the bot sends a trace activity (visible in the Bot Framework Emulator) and two messages to the user. 
 
6. Bot Dialog: It creates an instance of EchoBot which contains the logic of Printing the User messages in console, This is where the bot's behavior is defined. 
 
7. Request Handling: It sets up two routes on the server for handling incoming requests. The /api/messages route is for normal HTTP requests, and the upgrade event is for WebSocket connections. Both routes use the adapter to process the requests and run the bot's dialog. 
## Further reading

- [Bot Framework Documentation](https://docs.botframework.com)
- [Bot Basics](https://docs.microsoft.com/azure/bot-service/bot-builder-basics?view=azure-bot-service-4.0)
- [Dialogs](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-dialog?view=azure-bot-service-4.0)
- [Gathering Input Using Prompts](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-prompts?view=azure-bot-service-4.0)
- [Activity processing](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-activity-processing?view=azure-bot-service-4.0)
- [Azure Bot Service Introduction](https://docs.microsoft.com/azure/bot-service/bot-service-overview-introduction?view=azure-bot-service-4.0)
- [Azure Bot Service Documentation](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0)
- [Azure CLI](https://docs.microsoft.com/cli/azure/?view=azure-cli-latest)
- [Azure Portal](https://portal.azure.com)
- [Language Understanding using LUIS](https://docs.microsoft.com/en-us/azure/cognitive-services/luis/)
- [Channels and Bot Connector Service](https://docs.microsoft.com/en-us/azure/bot-service/bot-concepts?view=azure-bot-service-4.0)
- [Restify](https://www.npmjs.com/package/restify)
- [dotenv](https://www.npmjs.com/package/dotenv)
