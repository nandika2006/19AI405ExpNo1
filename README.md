## ExpNo 1 :Developing AI Agent with PEAS Description

## AIM:
To find the PEAS description for the given AI problem and develop an AI agent.

### NAME: NANDIKA S
### REG NO: 212224230175

## Theory
## Medicine prescribing agent:
Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.

## PEAS DESCRIPTION:
<img width="831" height="162" alt="Screenshot 2025-09-17 112409" src="https://github.com/user-attachments/assets/a4934469-d1d2-4107-b972-00985ccbde9d" />

## DESIGN STEPS
## STEP 1:Identifying the input:
Temperature from patients, Location.

## STEP 2:Identifying the output:
Prescribe medicine if the patient in a random has a fever.

## STEP 3:Developing the PEAS description:
PEAS description is developed by the performance, environment, actuators, and sensors in an agent.

## STEP 4:Implementing the AI agent:
Treat unhealthy patients in each room. And check for the unhealthy patients in random room

## STEP 5:
Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented

## Program :
~~~
import random

class VacuumCleanerAgent:
    def __init__(self):  # Initialize the agent's state (location and dirt status)
        self.location = "A"  # Initial location (can be "A" or "B")
        self.dirt_status = {
            "A": True,
            "B": True,
        }  # Initial dirt status (False means no dirt)
        self.performance = 0

    def move_left(self):  # Move the agent to the left if possible
        if self.location == "B":
            self.location = "A"

    def move_right(self):  # Move the agent to the right if possible
        if self.location == "A":
            self.location = "B"

    def suck_dirt(self):  # Suck dirt in the current location if there is dirt
        if self.dirt_status[self.location]:
            self.dirt_status[self.location] = False
            print(f"Sucked dirt in location {self.location}")

    def do_nothing(self):  # Do nothing
        pass

    def perform_action(self, action):  # Perform the specified action
        if action == "left":
            self.performance = self.performance - 1
            self.move_left()
        elif action == "right":
            self.performance = self.performance - 1
            self.move_right()
        elif action == "suck":
            self.performance = self.performance + 10
            self.suck_dirt()
        elif action == "nothing":
            self.do_nothing()
        else:
            print("Invalid action")

    def print_status(self):  # Print the current status of the agent
        print(f"Location: {self.location}, Dirt Status: {self.dirt_status}, ", end="")
        print(f"Perfomance Measure: {self.performance}")


# Example usage:
agent = VacuumCleanerAgent()
# Move the agent, suck dirt, and do nothing
agent.perform_action("left")
agent.print_status()
agent.perform_action("suck")
agent.print_status()
agent.perform_action("right")
agent.print_status()
agent.perform_action("suck")
agent.print_status()
agent.perform_action("nothing")
agent.print_status()
~~~

## Output :
<img width="727" height="164" alt="image" src="https://github.com/user-attachments/assets/517672e9-a4a0-483e-8e52-bd0bd107b5fa" />

## Result :
Thus the Developing AI Agent with PEAS Description was implemented using python programming.
