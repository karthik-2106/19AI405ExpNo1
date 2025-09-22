## ExpNo 1 : Developing AI Agent with PEAS Description

**Name :** KARTHIKEYAN M  
**Register Number :** 212223110020  


## AIM:
To find the PEAS description for the given AI problem and develop an AI agent.


## THEORY
### Plant Watering Agent:
This agent monitors the soil moisture level of plants and waters them if the moisture is below a threshold (considered dry). The environment consists of multiple plants in different locations. The agent senses the moisture level of each plant and decides whether to water it. The agent’s performance is measured by the number of plants properly watered, and each unnecessary movement reduces performance. Hence, the agent ensures plants are properly maintained.

---

## PEAS DESCRIPTION:

| Agent Type             | Performance                     | Environment           | Actuators          | Sensors                      |
|------------------------|---------------------------------|---------------------|------------------|-------------------------------|
| Plant watering agent   | Watering dry plants, agent movement | Plants, Soil Moisture | Watering mechanism | Location, Soil Moisture level |

---

## DESIGN STEPS

**STEP 1: Identifying the input:**  
Soil moisture level of plants, Location of each plant.

**STEP 2: Identifying the output:**  
Water the plant if the soil is dry.

**STEP 3: Developing the PEAS description:**  
PEAS description is developed by specifying the performance, environment, actuators, and sensors in the agent.

**STEP 4: Implementing the AI agent:**  
Check the soil moisture of each plant and water the plant if dry.

**STEP 5: Measure the performance parameters:**  
For each plant watered, performance is incremented; for each unnecessary movement, performance is decremented.


## CODE

```python
import random

class PlantWateringAgent:
    def __init__(self):
        self.plants = ["Plant 1", "Plant 2", "Plant 3"]
        self.performance = 0

    def sense(self, moisture_level):
        """Sense the moisture level of a plant"""
        return moisture_level

    def act(self, plant, moisture_level):
        """Act based on moisture level"""
        if moisture_level < 30:  # Less than 30% moisture → water the plant
            self.water_plant(plant)
        else:
            self.skip_plant(plant)

    def water_plant(self, plant):
        print(f"{plant}: Soil is dry! Watering the plant.")
        self.performance += 1

    def skip_plant(self, plant):
        print(f"{plant}: Soil is moist. No watering needed.")

def main():
    agent = PlantWateringAgent()
    # Example moisture levels (can be replaced with real sensor input)
    plant_moisture = [25, 45, 20]  # % moisture for each plant

    for i, moisture in enumerate(plant_moisture):
        plant = agent.plants[i]
        sensed_moisture = agent.sense(moisture)
        agent.act(plant, sensed_moisture)

    print(f"Total actions performed by agent: {agent.performance}")

if __name__ == "__main__":
    main()
```

## OUTPUT:
<img width="587" height="90" alt="image" src="https://github.com/user-attachments/assets/1cafa1ca-abd5-46cf-9b47-be5cfbae6716" />

## RESULT:
The Plant Watering Agent senses soil moisture and waters plants when needed, showing its PEAS-based AI functionality.

