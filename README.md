# NukeScript

NukeScript is the scripting system of NukeRat. It lets you automate actions and build custom functionality.

It's built on Python, with a native event and command system for carrying out those actions, so you get all the flexibility Python already offers, especially external libraries.

## Usage

To use NukeScript, go to *NukeRat* > *NukeScript* and click *Add* to create a new script. After that, just hit play on the script.

### Minimal example

```python
def on_connect(event):  # event holds all the information from the event
    echo(f"[+] new implant: {event['user']} @ {event['hostname']}")
    cmd(event["tag"], "whoami")

# Event trigger
event.new_host:on_connect()
```
### Libraries

Since NukeScript is built on Python, you can use any Python library you want.

```python
import requests

def example(event):
    echo(requests.get("https://example.com").text)

event.heartbeat_1s:example()
```

If you need an external library, install it with `./nukerat.py server venv install <package>`. That installs the package into the NukeScript venv.

```bash
./nukerat.py server venv install requests
```

### Debug

To follow the output from echo, open the *NS Debugger* from *Tabs* > *NS Debugger*.

## Documentation

To read more about NukeScript, see the docs at [www.nukerat.com/docs/nukescripts](https://www.nukerat.com/docs/nukescripts).
- Events: [www.nukerat.com/docs/nukescripts/events](https://www.nukerat.com/docs/nukescripts/events)
- Commands: [www.nukerat.com/docs/nukescripts/commands](https://www.nukerat.com/docs/nukescripts/commands)
- Examples: [www.nukerat.com/docs/nukescripts/examples](https://www.nukerat.com/docs/nukescripts/examples)
