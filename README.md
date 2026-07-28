## Design and Integration of a Hotel Availability Checker Using LLM

### AIM:
To design and implement a Python function for checking hotel room availability and integrate it with a chat completion system using the function-calling feature of a Large Language Model (LLM).

### PROBLEM STATEMENT:
Develop a Python function to check hotel room availability based on a user-provided city name. The function takes city as the input parameter and returns the availability details in JSON format. A function schema is defined with the name, description, parameters, and required fields to enable LLM function calling. The LLM identifies the user's request, extracts the city parameter, invokes the function, and retrieves the hotel availability. This demonstrates the integration of Python functions with a chat completion system using LLM function calling.
### DESIGN STEPS:

#### STEP 1:
Create a Python function check_hotel(city) that stores hotel availability data for different cities and returns the result in JSON format.
#### STEP 2:
Define the function schema containing the function name, description, parameters, and required inputs so that the LLM understands when and how to call the function.
#### STEP 3:
Integrate the function with the chat completion API. When the user requests hotel availability, the LLM invokes the function, retrieves the result, and generates a natural-language response based on the returned JSON data.
### PROGRAM:
```python
Name:Dhivya Dharshini B
Reg No:212223240031
import json

def check_hotel(city):
    """Check hotel availability."""
    hotels = {
        "Chennai": "15 rooms available",
        "Mumbai": "8 rooms available",
        "Hyderabad": "12 rooms available"
    }

    return json.dumps({
        "city": city,
        "availability": hotels.get(city, "No hotels found")
    })

functions = [
    {
        "name": "check_hotel",
        "description": "Check hotel room availability in a given city",
        "parameters": {
            "type": "object",
            "properties": {
                "city": {
                    "type": "string",
                    "description": "The name of the city, e.g. Chennai, Mumbai, Hyderabad"
                }
            },
            "required": ["city"]
        }
    }
]

# Example
print(check_hotel("Chennai"))
response_message = response["choices"][0]["message"]
response_message
response_message["content"]
response_message["function_call"]
json.loads(response_message["function_call"]["arguments"])
```

### OUTPUT:
<img width="446" height="692" alt="image" src="https://github.com/user-attachments/assets/4ec340ef-b583-439c-8718-43e87de6272d" />





<img width="355" height="191" alt="image" src="https://github.com/user-attachments/assets/f19133c0-51b6-4365-89ba-6605dc155509" />







<img width="363" height="77" alt="image" src="https://github.com/user-attachments/assets/23f10b38-9f06-47f6-ae4e-f02a803e6669" />








<img width="501" height="26" alt="image" src="https://github.com/user-attachments/assets/b09c2116-c0bf-4628-a3c2-18c25b409850" />



### RESULT:
The Python function for checking hotel room availability was successfully implemented and integrated with the LLM function-calling mechanism. The system correctly identified the user's request, invoked the appropriate function, and returned the hotel availability information in JSON format, demonstrating successful integration between Python functions and the chat completion system.
