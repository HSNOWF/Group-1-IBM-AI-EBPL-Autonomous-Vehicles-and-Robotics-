# Group-1-IBM-AI-EBPL-Autonomous-Vehicles-and-Robotics-
README: How to Run the Autonomous Vehicle Simulation

This guide helps you run the simulation step by step in Google Colab or Jupyter Notebook.

Step 1: Upload Required Icon Files
Before running the simulation, upload the following PNG files:
car.png
flag.png
rock.png
battery.png
charging.png
---------------------------------------------------------------------------------

Step 2: Install Required Library
Run this once to ensure the widget interface works:
!pip install ipywidgets
Then enable widget rendering in Colab:
from google.colab import output
output.enable_custom_widget_manager()

---------------------------------------------------------------------------------

Step 3: Load All Icons
In a new cell, paste and run this code:
import cv2
icons = {}
for icon in ['car', 'flag', 'rock', 'battery', 'charging']:
    icons[icon] = cv2.imread(f"{icon}.png", cv2.IMREAD_UNCHANGED)
    assert icons[icon] is not None, f"Failed to load {icon}.png"
    
----------------------------------------------------------------------------------
    
Step 4: Define Helper Functions and Classes
Run each of the following classes in a separate cell in order:
1. overlay_icon(img, icon, pos, size)
2. PathPlanner
3. AutonomousVehicle


----------------------------------------------------------------------------------


Step 5: Run the Simulation
Finally, in a new cell, create the vehicle instance:
av = AutonomousVehicle()
This will display:
The destination input box
Start/Emergency Stop buttons
A live battery slider
Output status logs

----------------------------------------------------------------------------------

How It Works:
The car moves from (0, 0) to the destination you provide.
If battery drops below 20%, it detours to the nearest charging station.
Dynamic obstacles randomly move during travel.
You can stop at any time with the Emergency Stop button.
