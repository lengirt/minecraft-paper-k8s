# Minecraft Server на движке Paper 1.21.4 для Kubernetes

## Схема
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

## Описание
Этот проект представляет собой сервер Minecraft на движке Paper версии 1.21.4, подготовленный для развёртывания в Kubernetes-кластере с использованием инструмента werf для сборки и деплоя.
**Сделано хрен знает зачем.**

## О проекте:
- **Движок:** Paper 1.21.4 — высокопроизводительный форк Minecraft Java Edition с улучшенной оптимизацией и дополнительными возможностями
- **Контейнеризация:** сервер упакован в Docker-образ, что обеспечивает простоту запуска и обновления
- **Оркестрация:** используется Kubernetes для управления жизненным циклом подов, сетевыми настройками и хранением данных.
- **Управление:** Helm-чарты позволяют легко устанавливать, настраивать и обновлять сервер, а также интегрировать с другими сервисами кластера
- **Хранение данных:** поддерживается использование Persistent Volume для сохранения миров и конфигураций с возможностью масштабирования и отказоустойчивости.
- **Гибкость:** конфигурация сервера и параметры запуска настраиваются через переменные окружения и ConfigMap, что упрощает адаптацию под разные сценарии.

## Внимание
- **helm** использует дочерние чарты, не забудьте выполнить команду ```werf helm dependency update .helm``` для добавления зависиомтей
- **Пароль для RCON** используется как секрет и добавляется через initContainers.