🕒 PyQt5 Stopwatch Application

A simple GUI Stopwatch built using Python & PyQt5.
It allows the user to start, stop, and reset time with millisecond precision.

📌 Features

Start stopwatch

Stop/Pause stopwatch

Reset timer to zero

Millisecond accuracy (updates every 10ms)

Clean modern UI using Qt Stylesheet

🛠 Technologies Used

Python 3

PyQt5 (GUI Framework)

QTimer (for real-time updates)

QTime (for time handling)

▶️ How It Works

The application uses a QTimer that triggers every 10 milliseconds.
Each trigger increases the stored time and updates the label display.

🧠 Code Explanation
1. Importing Libraries
from PyQt5.QtWidgets import QApplication, QWidget, QLabel, QPushButton, QHBoxLayout, QVBoxLayout
from PyQt5.QtCore import QTimer, QTime, Qt


QWidget → Main window

QLabel → Shows stopwatch time

QPushButton → Control buttons

QTimer → Updates time repeatedly

QTime → Stores time value

2. Creating Stopwatch Class
class Stopwatch(QWidget):


This class represents the whole stopwatch window.

3. Initial Setup
self.time = QTime(0, 0, 0, 0)
self.timer = QTimer()


Time starts at 00:00:00.00

Timer object repeatedly updates time

4. UI Layout

Vertical Layout → Time Display
Horizontal Layout → Buttons

[   TIME DISPLAY   ]
[ Start | Stop | Reset ]

5. Button Functions
Start
def start(self):
    self.timer.start(10)


Starts updating every 10 ms

Stop
def stop(self):
    self.timer.stop()


Pauses stopwatch

Reset
def reset(self):
    self.timer.stop()
    self.time = QTime(0, 0, 0, 0)


Stops and resets to zero

6. Updating Time
def update_display(self):
    self.time = self.time.addMSecs(10)
    self.time_label.setText(self.format_time(self.time))


Adds 10 milliseconds each cycle and updates label

7. Formatting Output
return f"{hours:02}:{minutes:02}:{seconds:02}.{milliseconds:02}"


Displays time like:

00:01:23.45

8. Running the App
app = QApplication(sys.argv)
window = Stopwatch()
window.show()
sys.exit(app.exec_())


Creates the GUI application and launches the window.

📷 Output

A digital stopwatch window with Start, Stop, and Reset buttons.

📦 Installation
pip install PyQt5


Run the program:

python stopwatch.py

