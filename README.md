# Final Report for Mesa LLM

## The Goal
The main objective of the project was to create a python library that would let users integrate LLM based agents into the Mesa ABM framework as an alternative to the currently hardcoded agents. Colin Frisch and I worked together on developing this library as a part of our GSoC projects.
You can find the link to the repository [here](https://github.com/wang-boyu/mesa-llm).

## Approach
- To do this we created a library that would provide all the tools necessary to create such agents in the original mesa environment. This included handling the agent's memory, reasoning frameworks, api calls and the agent's tools(functions the agents could call to do a task) etc.
- We started off by creating a reasoning module and a memory module for the agent. Both provide the user the freedom to implement their own framework, this is especially useful for research purposes. The memory module provides 3 basic memory frameworks that LLMs use: Long-term + Short-term memory, pure Long-term memory and pure Short-term memory. Similarly we provide 3 inbuilt paradigms for reasoning: ReWoo, ReAct and CoT.
- We proceeded to implement Module LLM (the file that handles all the LLM api calls) and the LLM Agent which orchestrates and compiles all the functionalities into a Mesa agent.
- These modules built the base for the library. For further functionalities, we implemented modules like recording(so that the runs of the simulation can be recorded and reproduced), Parallel Stepping ( for faster simulation speeds) and Tools (to manage the actions/functions that the llm could carry out).
- To properly test out our framework, we built two working examples: Epstein's Civil Violence Model and The Negotiation Model. The civil violence model is based on a research paper and the negotiation model was built as a toy model for beginners to get the hang of the framework.
- Here is a small snippet from solara that is running the visualization for The Civil Violence Model:
 ![Civil Violence Model](https://github.com/user-attachments/assets/9b6a5be7-5eeb-4f54-a2a9-4b7a9c62b15c)

- Towards the end, we shifted our attention to test and ensure proper coverage for all the functions.

## Brief Overview of the Architecture
![Architecture](https://github.com/user-attachments/assets/63bbeb9f-6774-427f-b8a1-da1408e55660)


## Challenges
There were a couple of challenges we faced along the way, the major one being the time it took to run the simulation. To combat this we incorporated the option of letting the user make the API calls asynchronous, furthermore, we also provided the user to enable multithreading by just toggling the value of an attribute.

Initially we had to do a lot of brainstorming to figure out the perfect way to design our architecture. But after a lot of ideation we were able to come up with a working architecture. Another challenge we faced was with the presentation of the output. Mesa primarily used Solara, but we designed to use the terminal as well so that the textual reasoning could be displayed to the user. We tried to structure it out and make it as presentable and comprehensive as possible.
Here is a snippet of a part of the terminal output from The Civil Violence Model and The Negotiation Model:
### Civil Violence Model
![Civil Violence Terminal Output](https://github.com/user-attachments/assets/1b7459ed-04ed-454f-ac9c-cd38fa4643c2) 

### The Negotiation Model
![Negotiation Model Terminal Output](https://github.com/user-attachments/assets/dafbdbff-76f6-40eb-8f5b-1266da030e8f)


## General Workflow
I really enjoyed collaborating on this project. Exchanging ideas and refining them together was really engaging and rewarding. Our workflow typically involved jointly brainstorming the architecture and then dividing the coding tasks. For instance, I worked on the reasoning module while Colin worked on the memory module . Over time, however, we both contributed new features and improvements to each other's code, making any clear distinction of responsibility difficult to draw. This collaborative approach ensured that we developed a strong understanding of every part of the library and its internal workings.

## Current Progress and Future Directions
We have developed a working framework capable of running basic LLM-based ABM models, providing a solid foundation for further growth. Our next priorities are to introduce new features that expand functionality, build more examples to showcase the library's full capabilities, and focus on performance optimization to support more complex simulations. In parallel, we plan to add tutorials and documentation to make the framework more accessible.

## Learning Outcomes
I gained a lot of experience through this project and am deeply grateful for the opportunity. It allowed me to strengthen my understanding of object-oriented programming in Python, parallel computing, systems design, Git, and the practices involved in maintaining large-scale projects. Overall, it provided me with a comprehensive overview of open-source development.
