# Minecraft Server running on the Paper 1.21.4 engine for Kubernetes
## Other languages / Другие языки
- [Русский](docs/ru/README.md)


## Scheme
```
├── .helm
│   ├── charts
│   │   └── paper
│   │       ├── Chart.yaml
│   │       └── templates
│   │           └── ...
│   ├── Chart.yaml
│   ├── .helmignore
│   ├── requirements.lock
│   └── values.yaml
├── paper-1.21.4-232.jar #
├── README.md
└── werf.yaml  
```

## Description

This project is a Minecraft server based on the Paper engine version 1.21.4, prepared for deployment in a Kubernetes cluster using the werf tool for building and deploying.
**Made for reasons unknown.**

## About the project:

- **Engine:** Paper 1.21.4 — a high-performance fork of Minecraft Java Edition with improved optimization and additional features.

- **Containerization:** the server is packaged into a Docker image, ensuring ease of launch and updates.

- **Orchestration:** Kubernetes is used to manage pod lifecycle, networking, and data storage.

- **Management:** Helm charts allow easy installation, configuration, and updating of the server, as well as integration with other cluster services.

- **Data storage:** supports Persistent Volumes for saving worlds and configurations with scalability and fault tolerance.

- **Flexibility:** server configuration and startup parameters are set via environment variables and ConfigMap, simplifying adaptation to different scenarios.


## Attention
- **helm** uses subcharts; don’t forget to run the command ```werf helm dependency update .helm``` to add dependencies.
- **RCON password** is used as a secret and added via initContainers.