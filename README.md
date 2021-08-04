# DigitalBeing
A platform for letting researchers connect an intelligent AI directly to realtime communication networks and 3D worlds.

In partnership with SuperReality, a free open source teaching platform for everyone.

### How It Works
Under the hood you'll find an instance of Chrome (using Puppeteer) which can be run in headless or GUI mode. The bot uses control surfaces from the user API to interact, and also has some extra access to world state.

### Setup
1. Install python dependencies in requirements.txt
    ```pip install -r requirements.txt```
2. Install node.js dependencies
    ```npm install```
4. Create a local .env file with configuration variable for example.
    ```DISCORD_API_TOKEN=<Your Discord Bot API Token>```
    This will create a discord bot client which will listen for incomming messages when the bot gets mentioned in your server chat.
5. Use the parameters file for the agent inside ```server/agent_params.py``` here you can select which agents to launch along with some other flags. 
   you only need to edit the following parameter to launch the specific agents. Right now not all agents are working but the following list of agents have been tested and are working.
   ```
    SELECTED_AGENTS = [
                        'dialogpt.small',
                        'dialogpt.medium',
                        'dialogpt.large',
                        'gptneo.small',    
                        'gptneo.large',    
                        'gptneo.xlarge'    
                      ]
   ``` 
6. Run the host bot framework
    ```npm run start-gui```

### Getting Started

1. Run the bot with `npm start` -- by default it will connect to a test room on our dev server and open a port on gRPC
2. Run example.py to connect the default hello world implementation
3. Copy and paste the code from example.py into your project and hook your models into it.

### Docker

You can run it using docker, if you don't have node installed or need to test.
``` bash
# Build the image
docker build digital_being .

# Run the image
docker run -d digital_being
```

