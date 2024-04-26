# Battery-Notify

This script monitors the battery level of your laptop and sends notifications to your mobile using Pushbullet when the battery level is low or reaches a certain threshold. It also checks for internet connectivity to avoid errors.
## Requirements

- Python 3
- psutil library (`pip install psutil`)
- pushbullet library (`pip install pushbullet.py`)

## Usage

1. Clone or download this repository to your local machine.
2. Install the required libraries using pip.
3. Replace 'YOUR_API_KEY' with your actual Pushbullet API key in the `battery.py` file.
4. Run the script: `python battery.py` at test it.

## Adding to Startup

### Linux

1. Open your terminal.
2. Set your preferred text editor (e.g., nano): `export VISUAL=nano`.
3. Open the crontab file for editing: `crontab -e`.
4. Add the following line at the end of the file:

```bash
@reboot sleep 100 && /usr/bin/python3 /path/to/batterycheck/battery.py > /path/to/batterycheck/battery.log 2>&1
```

Replace `/path/to/batterycheck` with the actual path where you have saved the `battery.py` script.

5. Save the file and exit.

### Windows

1. Open Task Scheduler by searching for it in the Start menu.
2. Click on "Create Basic Task" in the Actions pane.
3. Follow the wizard to set up a new task:
   - Name the task.
   - Choose "When the computer starts" as the trigger.
   - Select "Start a program" as the action.
   - Browse and select the `battery.py` script.
4. Complete the wizard, and the script will run at startup.

### macOS

1. Open Terminal.
2. Edit your user's crontab file: `crontab -e`.
3. Add the following line at the end of the file:

```bash
@reboot sleep 100 && /usr/bin/python3 /path/to/batterycheck/battery.py > /path/to/batterycheck/battery.log 2>&1
```

Replace `/path/to/batterycheck` with the actual path where you have saved the `battery.py` script.

4. Save the file and exit.

## Note

If cron is not installed:

- **Linux**: Install cron using your package manager. For example, on Ubuntu, you can install it with `sudo apt-get install cron`.
- **macOS**: Consider using launchd or third-party tools like Lingon or cronie.

Make sure to replace placeholders with actual file paths and configurations.

