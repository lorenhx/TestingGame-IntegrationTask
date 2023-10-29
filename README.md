# Testing Game - Integration Task
This is an Educational Game for "Man vs automated Testing Tools challenges", part of the ENACTEST project.<br>
It has been realized during the Software Architecture Design course at University of Naples Federico II: https://github.com/Testing-Game-SAD-2023

Team Components:
- Pasquale Riello - M63/1516
- Lorenzo Pannone - M63/1492

# What we have done
Our task was to integrate the other tasks and microservices - created by other teams - into the final
working product.
Others goals we have achieved are:
- Enhanced the security (authentication, authorization) and management of APIs by
implementing the API Gateway component
- Increased consistency by serving pages from the same domain and port by
implementing a reverse proxy (the UI Gateway component)

More specifically, we have integrated the following tasks:
- Task 1: https://github.com/Testing-Game-SAD-2023/T1-G11
- Task 2-3: https://github.com/Testing-Game-SAD-2023/T23-G1
- Task 4: https://github.com/Testing-Game-SAD-2023/T4-G18
- Task 5: https://github.com/Testing-Game-SAD-2023/T5-G2
- Task 6: https://github.com/Testing-Game-SAD-2023/T6-G12
- Task 7: https://github.com/Testing-Game-SAD-2023/T7-G31
- Task 9: https://github.com/Testing-Game-SAD-2023/T9-G19

![FinalComponentDiagram](https://github.com/Pask00/TestingGame-IntegrationTask/assets/25242319/bd93d348-5ab2-434d-a8d9-db095d7e6a2b)

# Installation Guide

## STEP 1
The script "installer.bat" should be started. The following operations will be performed:
1) creation of the "global-network" common to all containers
2) creation of the volume "VolumeT9" common to Tasks 1 and 9
3) installation of each individual container

NOTE: The container related to Task 9 ("Project-SAD-G19-master") will suspend itself after startup. It is only used to "populate" the "VolumeT9" volume shared with Task 1.

## STEP 2
You must configure the container "manvsclass-mongo_db-1" as also described in the Task 1 documentation.
To do this you must do the following:
1) stand inside the container terminal.
2) type the command "mongosh"
3) type the following commands:

        use manvsclass
        db.createCollection("ClassUT");
        db.createCollection("interaction");
        db.createCollection("Admin");
        db.createCollection("Operation");
        db.ClassUT.createIndex({ difficulty: 1 })
        db.Interaction.createIndex({ name: "text", type: 1 })
        db.interaction.createIndex({ name: "text" })
        db.Admin.createIndex({username: 1})

## STEP 3
The entire application is now fully configured and reachable on port :80.

# Demonstration Video
## Student


https://github.com/Testing-Game-SAD-2023/T10-G40/assets/33938788/c6cd06c7-5d3a-4988-a651-7e1dc5896909



## Admin

https://github.com/Testing-Game-SAD-2023/T10-G40/assets/33938788/da3e5d04-7106-40ae-a0f3-1b7d6923c0cd
