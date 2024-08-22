# deploy-kafka-on-kubernetes

## Introduction

Le déploiement de Kafka sur Kubernetes améliore le streaming d'événements distribués avec des fonctionnalités d'orchestration de conteneurs telles que l'évolutivité et la tolérance aux pannes. L'intégration avec Kubernetes permet aux organisations de faire évoluer les clusters Kafka à la demande tout en maintenant une disponibilité et une fiabilité élevées.

## kafka

Kafka est une application avec état qui enregistre des messages en continu provenant de producerrs et les stocke pour que les consumers puissent les utiliser ultérieurement. Dans Kubernetes, la manière recommandée de déployer des applications avec état est d'utiliser des statefulsets, des objets de charge de travail qui garantissent l'unicité et l'ordre des pods d'application.

## Network Policy

Network policy ( politiques réseaux ) sont un mécanisme de contrôle du flux de trafic réseau dans les clusters Kubernetes. Elles  permettent de définir lesquels de nos Pods sont autorisés à échanger du trafic réseau. Nous devrions les utiliser dans nos clusters pour empêcher les apps de s'atteindre mutuellement sur le réseau, ce qui permettra de limiter les dégâts si l'une de nos apps est compromise.

Chaque Network policy que nous créons cible un groupe de pods et définit les points d'extrémité du réseau Ingress (entrant) et Egress (sortant) avec lesquels ces pods peuvent communiquer.

