# LightAI
A Spigot plugin that adds a chatbot to Minecraft Villagers. With this plugin, you can bring your Minecraft world to life with intelligent and engaging NPC conversations.

## Demo

Check out this demo video to see the Chatbot for Minecraft Villagers in action:

**I put an AI Chatbot into a Villager - OpenAI + Minecraft**

[![Chatbot for Minecraft Villagers Demo Video](https://img.youtube.com/vi/7Z-VPBNbrWM/0.jpg)](https://www.youtube.com/watch?v=7Z-VPBNbrWM)

## Install video

[![Release + Tutorial Video](https://img.youtube.com/vi/FX0-mzqCuNE/0.jpg)](https://www.youtube.com/watch?v=FX0-mzqCuNE)

## Features

- Generate unique backstories for each NPC
- Memory: NPCs remember previous conversations and context
- Handle follow-up questions and provide more natural responses
- Customize NPC personalities and responses
- Create custom prompts for NPCs with different names
- Easy to install and use

## Prerequisites

- Spigot Minecraft server running in 1.19.3 ([paper](https://papermc.io/downloads) is recommended)
- [OpenAI](https://platform.openai.com/login/) account for the [API Key](https://platform.openai.com/account/api-keys)

## Installation

1. Download the latest version of the LightAI plugin from the releases page on GitHub.
2. Copy the plugin .jar file to the `plugins` folder of your Minecraft server.
3. Start or restart the server to load the plugin.

## Usage

1. Add your OpenAI api key using `/lightai <your-apikey>`
2. Summon a Villager NPC by using the `/spawnnpc` command in the game.
3. Right-click on the NPC to start a conversation.
4. Use natural language to ask the NPC questions and get responses.

## Details on extra features

- When the apikey is added, this will store the apikey under `/plugins/LightAI/apikey.txt` so it can be reused on server shutdown and startup
- To create a custom prompt for an NPC, create a file with the same name as the NPC and include the prompt in the file. The NPC will then use the prompt when interacting with players.
  - For example, if the NPC's name is "Ethan", you would create a file named "Ethan.txt" and include the custom prompt in the file. The next time the NPC interacts with a player, it will use the prompt from the file instead of the default prompt.
  - Add the [Ethan.txt](https://github.com/LightXEthan/LightAI/blob/main/build/LightAI/Ethan.txt) and [Pirate.txt](https://github.com/LightXEthan/LightAI/blob/main/build/LightAI/Pirate.txt) to the plugins/LightAI directory. 
  - Examples: `/spawnnpc Ethan` `/spawnnpc Pirate`
  - Note the prompt will only load if you have the file before you talk to the npc or when it is spawned
  - Note I am not an expert in Chatbots or AI, I'm just a developer who is interested in this stuff
  
## Technical Details

The Chatbot for Minecraft Villagers plugin uses the OpenAI API to generate responses to player questions. When a player interacts with an NPC, the plugin sends a request to the OpenAI API with the player's question, and the API returns a response which the plugin then displays to the player.

The plugin was built using Spigot code, making it compatible with any Minecraft server that runs the Spigot or Paper Spigot server software.

## Limitations
While the Chatbot for Minecraft Villagers is designed to provide engaging and intelligent responses, it is important to note that there are limitations to the technology. The responses generated by the OpenAI API are based on the data it was trained on, and may not always be accurate or appropriate. Additionally, the plugin is only as good as the quality of the data it was trained on, so there may be biases or inaccuracies in the responses generated by the plugin.

- This uses OpenAI APIs, please keep in mind the [usage policies](https://platform.openai.com/docs/usage-policies) when interacting with the NPC chatbot
- The bot may be biased on certain topics, and will sometimes be confiendently incorrect.
- Sometimes the NPC's text will cut off as if it had more to say. You can say `continue` to let the NPC finish it's message
  - I haven't found a way to fix this after much tweaking of the temperature and max_tokens field in the request and including text limitations in the prompt which the bot will often still go over
- This uses OpenAI api which gives you a generous $18 to use but please be warned, the code works by using the prompt + previous message history as prompt, so the cost would be exponential. This is very problematic for very long extended conversations with the bot and would not be scalable. I do have an idea to fix this but this is in the backlog for me.

## Ethical Implications

Using chatbots in Minecraft, or any other virtual environment, raises important ethical questions. It is important to consider the ethical implications of using chatbots, and to use them responsibly. This includes being mindful of player privacy and avoiding the use of chatbots for malicious purposes.

For transparency, this code and README file were partially generated with the assistance of ChatGPT for code and text generation, and for troubleshooting purposes. All code and text have been thoroughly reviewed and tested by me before being added.

As the developer of this plugin, I am committed to promoting responsible and ethical use of chatbots. Hopefully this demo can help spark discussion of these concerns and explore these further. I encourage all users to review the limitations and ethical implications of using chatbots, and to use our plugin with care.
