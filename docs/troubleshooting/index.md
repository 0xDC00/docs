---
sidebar_position: 4
tags:
  - help
  - troubleshooting
  - guides
---

# Troubleshooting

Before troubleshooting further, first restart both Agent and your emulator or game, and attach before starting the game (for emulators).

## Agent is Not Hooking Text

If Agent is not hooking text for your game, please check the following:

- Your scripts are up to date (update in the Agent UI).
- You are using the [latest version](https://github.com/0xDC00/agent/releases/latest) of Agent.
- If you're hooking an emulated game, ensure that you have attached to the emulator **before** starting the game.
- Ensure you have the right game for the script you are using.
  - PC Games - Check that your game matches the game the script was created for (e.g. if the script is for Steam, you got the game from Steam and not GOG).
  - Emulators - Make sure the game's ID matches your game. For example, the script may be for the Japanese copy of the game, but your game is the US copy.
- For emulated games, make sure you are using the correct version of the game specified by the script. For example, your game is 1.0.2 but the script is for 1.0.0.
- You have selected the correct process and script for this game.

If all of these steps have been taken, and the game will still not hook text, please reach out to us [on Discord](https://discord.gg/sWeFsmJYJc).

## Errors

### Module <name_of_the_module> not found! 

```
Error: Error: Module ./libYuzu.js not found!
```
If you see this error, it means the script you attached couldn't find it's dependencies in the folder it's located in.

To fix this error, please make sure that the script is in `<agent_path>\data\scripts\`.

If a script is already in the scripts repository, you should just use the update button. 

### Unable to Find DLL

```
Unable to find DLL at 'C:\Users\...\AppData\Local\Temp\frida-fddab22b1574f0f686be62d756aa8aca\32\frida-agent.dll`
```

If you see this error, close all Agent windows and restart Agent, and ensure you only have one instance of Agent running.

### MergeNotSupportedError

```
MergeNotSupportedError: Merges with conflicts are not supported yet.
```

If you see this error, delete the `data/scripts` directory at the root of your Agent installation folder and restart Agent.

### Agent.app is damaged (on macOS)

![](./img/macos.png)

Apple will sometimes quarantine .app files that are not downloaded from the App store. You can resolve this issue by opening the Terminal app and running the following command (assuming Agent.app is your `/Applications` folder):

```bash
xattr -c /Applications/Agent.app
```
