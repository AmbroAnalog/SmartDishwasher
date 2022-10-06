# Smart Dishwasher

The `SmartDishwasher` project is a educational project that aims to digitalize a dishwasher form the 1990s.
All aspects from hardware modifications to database design and fronted development are covered and documented in this and the linked sub repositorys.
The goal of the project is to learn new techniques and practice designing systems.

## project components
- :pushpin: **Hardware changes to the dishwasher** ([DIY CompactProjector](https://github.com/AmbroAnalog/CompactProjectorPCB), ...)
- :pushpin: **[DishwasherOS](https://github.com/AmbroAnalog/DishwasherOS):** Software that runs on the newly installed hardware of the dishwasher and records measurement data and sends it to the cloud.
- :pushpin: **[DishwasherBackend](https://github.com/AmbroAnalog/DishwasherBackend):** A RESTful API application for interacting with the database.
- :pushpin: **[DishwasherFrontend](https://github.com/AmbroAnalog/DishwasherFrontend):** Angular frontend application to show runtime history, a live-view and more in-depth data analysis

```
 smart dishwasher project      ┌────────────────────────┐
                               │ Docker Container       │
┌──────────────┐               │  ┌───────┐             │
│  Dishwasher  │               │  │MongoDB│             │
└─────┬─▲──────┘               │  └──▲────┘             │
      │ │                      │     │                  │
┌─────▼─┴──────┐  REST-API     │  ┌──▼──────────────┐   │
│ DishwasherOS ├───────────────┼─►│DishwasherBackend│   │
└─────▲─┬──────┘               │  └────┬─▲──────────┘   │
      │ │                      │       │ │ REST-API     │
      │ │   ┌──────────┐       │       │ │ Socket.IO    │
      │ └──►│Projector │       │  ┌────▼─┴────────────┐ │
      │     └──────────┘       │  │DishwasherFrontend │ │
      │                        │  └───────────────────┘ │
      │     ┌──────────┐       │                        │
      └─────┤Shelly    │       └────────────────────────┘
            └──────────┘
```

## project description
The starting point for the modification is an original `Miele G 470 SC` dishwasher build in 1990. The program sequences of the dishwasher are controlled by a rotating disk with slide contacts. The disk is driven by a primitive clockwork. Due to the age of the device, not a single microcontroller is used in the entire dishwasher, the entire control system runs electromechanically.
This is where the `SmartDishwasher` project comes into play. In short, the project has the following goals:
- Create a digital twin of the dishwasher with current process data.
- A user interface that is available via the internet and displays live the process data of the dishwasher. 
- A database with all the wash cycles performed in the past.
- Accurate consumption evaluation of electricity and water consumption.
- A projector installed on the dishwasher that projects the remaining run time of the wash cycle into the floor of the kitchen.
- After all the modifications have been made, the outside of the dishwasher should still look like it was in its original condition. In addition, the control of the machine should still be done by the original electromechanical system.


## used tech stack
- [Python](https://github.com/python) for the OS
- [Flask](https://github.com/pallets/flask) for Python to build the RESTful API for the backend
- [socket.io](https://github.com/socketio/socket.io) for realtime communication between backend and frontend application
- [MongoDB](https://github.com/mongodb/mongo) as document-oriented database program
- [Angular](https://angular.io/) as a web framework for the frontend application
- [Bootstrap 5](https://github.com/twbs/bootstrap) as CSS framework for the frontend application
- [Docker](https://www.docker.com/) as a platform to deploy frontend, backend as well as the database

