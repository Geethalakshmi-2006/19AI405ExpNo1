ExpNo 1 :Developing AI Agent with PEAS Description
Name:GEETHALAKSHMI D
Register Number: 212224060079
AIM:

To find the PEAS description for the given AI problem and develop an AI agent.


Theory
Medicine prescribing agent:
Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.

PEAS DESCRIPTION:
Agent Type	Performance	Environment	Actuators	Sensors
Medicine prescribing agent	Treating unhealthy, agent movement	Rooms, Patient	Medicine, Treatment	Location, Temperature of patient
DESIGN STEPS
STEP 1:Identifying the input:
Temperature from patients, Location.

STEP 2:Identifying the output:
Prescribe medicine if the patient in a random has a fever.

STEP 3:Developing the PEAS description:
PEAS description is developed by the performance, environment, actuators, and sensors in an agent.

STEP 4:Implementing the AI agent:
Treat unhealthy patients in each room. And check for the unhealthy patients in random room

STEP 5:
Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented

PROGRAM:
  import random
  random.seed(1)   
  class MedicinePrescribingAgent:
  
      def __init__(self):
          self.performance = 0
          self.rooms = ["Room1", "Room2"]
          self.current_room = random.choice(self.rooms)
  
      def sense_environment(self):
          return round(random.uniform(97, 102), 1)
  
      def prescribe_medicine(self, temperature):
          if temperature > 98.5:
              print(f"Patient in {self.current_room} has fever ({temperature}°F). Prescribing medicine.")
              self.performance += 10
          else:
              print(f"Patient in {self.current_room} is healthy ({temperature}°F). No medicine required.")
  
      def move_to_other_room(self):
          other_room = [r for r in self.rooms if r != self.current_room][0]
          print(f"Moving from {self.current_room} to {other_room}.")
          self.current_room = other_room
          self.performance -= 1
  
      def run_agent(self, cycles=6):
          for _ in range(cycles):
              temp = self.sense_environment()
              self.prescribe_medicine(temp)
              self.move_to_other_room()
              print(f"Current Performance: {self.performance}\n")
  agent = MedicinePrescribingAgent()
  agent.run_agent()
  print("Final Performance Score:", agent.performance)
OUTPUT:
image
RESULT:
Thus the AI agent is developed successfully
