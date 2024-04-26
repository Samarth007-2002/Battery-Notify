# Battery-Notify
This script monitors the battery level of your laptop and sends notifications using Pushbullet when the battery level is low or reaches a certain threshold. It also checks for internet connectivity to ensure timely notifications.
#Requirements

    Python 3
    psutil library (pip install psutil)
    pushbullet library (pip install pushbullet.py)

Usage

    Clone or download this repository to your local machine.
    Install the required libraries using pip: pip install -r requirements.txt.
    Replace 'YOUR_API_KEY' with your actual Pushbullet API key in the battery.py file.
    Run the script: python battery.py.

Adding to Startup
Linux

    Open your terminal.

    Set your preferred text editor (e.g., nano): export VISUAL=nano.

    Open the crontab file for editing: crontab -e.

    Add the following line at the end of the file:

    bash

    @reboot sleep 100 && /usr/bin/python3 /path/to/batterycheck/battery.py > /path/to/batterycheck/battery.log 2>&1

    Replace /path/to/batterycheck with the actual path where you have saved the battery.py script.

    Save the file and exit.

Windows

    Open Task Scheduler by searching for it in the Start menu.
    Click on "Create Basic Task" in the Actions pane.
    Follow the wizard to set up a new task:
        Name the task.
        Choose "When the computer starts" as the trigger.
        Select "Start a program" as the action.
        Browse and select the battery.py script.
    Complete the wizard, and the script will run at startup.

macOS

    Open Terminal.

    Edit your user's crontab file: crontab -e.

    Add the following line at the end of the file:

    bash

    @reboot sleep 100 && /usr/bin/python3 /path/to/batterycheck/battery.py > /path/to/batterycheck/battery.log 2>&1

    Replace /path/to/batterycheck with the actual path where you have saved the battery.py script.

    Save the file and exit.

Note

If cron is not installed:

    Linux: Install cron using your package manager. For example, on Ubuntu, you can install it with sudo apt-get install cron.
