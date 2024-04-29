# Command Line

You can launch Agent from the command line by running the `agent` executable from your terminal.

## Usage

```
Usage:
  agent [options]

Options:
  --target="path to executable"   Path to executable (run)
  --script="path to script"       Path to script
  --args="command line"           Arguments to the executable
  --delay=0                       [optional] Wait (ms)
  --pname="process name"          [optional] Attach to process name instead target
```

:::warning

Paths in the `--args` flag need to be escaped, for example `-g \"C:\\path\\to\\game.nsp\"`.

:::

## Examples


### Yuzu

```bash
agent --target="C:\path\to\yuzu.exe" --script="C:\path\to\script.js" --args="-g \"C:\\path\\to\\game.nsp\""
```

### Ryujinx

```bash
agent --target="C:\path\to\Ryujinx.exe" --script="C:\path\to\script.js" --args="\"C:\\path\\to\\game.nsp\""
```

### PC

```bash
# Run -> wait 3s -> attach (for PC games)
agent --target="C:\path\to\game.exe" --script="C:\path\to\script.js" --delay=3000
  
# Run -> wait 3s -> attach game.bin
agent --target="C:\path\to\game.exe" --script="C:\path\to\script.js" --delay=3000 --pname="game.bin"
  
# Attach to an existing process
agent --script="C:\path\to\script.js" --pname="<process-name>"
```