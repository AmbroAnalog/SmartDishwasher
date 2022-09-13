# Smart Dishwasher

The `SmartDishwasher` project is a mult-year educational project that aims to digitalize a dishwasher form the 1990s.
All aspects from hardware modifications to database design and fronted development are covered and documented in this and the linked sub repositorys.
The goal of the project is to learn new techniques and practice designing systems.

## project components
- **Hardware changes to the dishwasher** ([DIY CompactProjector](https://github.com/AmbroAnalog/CompactProjectorPCB), ...)
- **[DishwasherOS](https://github.com/AmbroAnalog/DishwasherOS):** Software that runs on the newly installed hardware of the dishwasher and records measurement data and sends it to the cloud.
- **[DishwasherBackend](https://github.com/AmbroAnalog/DishwasherBackend):** A RESTful API application for interacting with the database.
- **[DishwasherFrontend](https://github.com/AmbroAnalog/DishwasherFrontend):** Angular frontend application to show runtime history, a live-view and more in-depth data analysis

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

## used tech stack
- [Python](https://github.com/python) for the OS
- [Flask](https://github.com/pallets/flask) for Python to build the RESTful API for the backend
- [socket.io](https://github.com/socketio/socket.io) for realtime communication between backend and frontend application
- [MongoDB](https://github.com/mongodb/mongo) as document-oriented database program
- [Angular](https://angular.io/) as a web framework for the frontend application
- [Bootstrap 5](https://github.com/twbs/bootstrap) as CSS framework for the frontend application
- [Docker](https://www.docker.com/) as a platform to deploy frontend, backend as well as the database


