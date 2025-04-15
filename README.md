# FOCUS_TIMER
###Overview
This Python script creates a stylish circular countdown timer GUI.

Built using tkinter for the interface and plyer for desktop notifications.

Users enter a time in minutes, click "Start", and a circle arc animation visually shows the countdown.

When time reaches zero, a notification pops up.

🧱 Code Breakdown
1. Imports
python
Copy
Edit
import tkinter as tk
from tkinter import ttk
from math import pi, cos, sin
from plyer import notification
tkinter: GUI library for window, buttons, canvas, etc.

ttk: Themed tkinter widgets (e.g., better-looking buttons).

math: Not fully used here but typically used for circular UI elements.

plyer: Sends cross-platform system notifications.

2. CircularTimer Class
Handles all GUI logic, countdown, and notification.

✅ __init__()
python
Copy
Edit
def __init__(self, root):
Initializes variables like time_left, running, and binds the GUI to root.

✅ create_widgets()
Creates and places all UI elements:

Label to prompt user input.

Entry box to input minutes.

Canvas to draw a circular countdown arc and time text.

Buttons:

Start: Begins the countdown.

Stop: Stops the countdown.

Canvas items:

self.timer_text: Displays MM:SS.

self.arc: Visual progress (circular countdown animation).

✅ update_canvas()
python
Copy
Edit
def update_canvas(self):
Converts remaining seconds to MM:SS format.

Updates the canvas text and arc extent.

Arc extent changes proportionally to the time left, making the countdown visually circular.

✅ countdown()
python
Copy
Edit
def countdown(self):
Decreases time_left every second.

Updates the canvas after each tick.

When time_left hits zero:

Sends notification via plyer.

Resets UI button states.

✅ start_timer()
python
Copy
Edit
def start_timer(self):
Reads user input (in minutes).

Converts it to seconds.

Starts the countdown and disables the "Start" button to prevent multiple clicks.

✅ stop_timer()
python
Copy
Edit
def stop_timer(self):
Stops the countdown.

Re-enables the "Start" button and disables "Stop".

3. Main Function
python
Copy
Edit
if __name__ == "__main__":
Starts the tkinter main loop.

Instantiates and displays the timer GUI.

🎨 UI Features
Dark theme (bg="#1e1e2f")

Stylish arc animation for time progress

Responsive canvas that updates every second

System notification to alert user when timer ends

📝 Example Usage:
Run the program.

Enter minutes (e.g., 5).

Click Start.

The circle animates and shrinks as time passes.

On timeout, a popup notifies you: “Time's up!”
