# HubWork

Projet d'analyse système réalisé dans le cadre du cours d'analyse des systèmes à l'EPHEC (Bruxelles), 2025-2026.

## Contexte

HubWork est une plateforme fictive de réservation d'espaces de coworking (bureaux, salles de réunion, postes de travail). Le projet consiste en une analyse complète du système avant développement : identification des besoins, modélisation UML et documentation, avec une soutenance orale devant le professeur.

## Contenu de l'analyse

- 25 cas d'utilisation couvrant la réservation d'espaces, la gestion des membres et l'administration de la plateforme
- Diagramme de cas d'utilisation
- Diagramme de classes
- Diagrammes d'états
- Diagrammes de séquence

## Exemple : diagramme de classes (simplifié)

```mermaid
classDiagram
    class Membre {
        +String nom
        +String email
        +reserverEspace()
        +annulerReservation()
    }
    class Espace {
        +String type
        +int capacite
        +boolean disponible
    }
    class Reservation {
        +Date dateDebut
        +Date dateFin
        +String statut
        +confirmer()
        +annuler()
    }
    class Administrateur {
        +gererEspaces()
        +gererMembres()
    }
    Membre "1" --> "*" Reservation : effectue
    Reservation "*" --> "1" Espace : concerne
    Administrateur "1" --> "*" Espace : gere
```

## Exemple : cas d'utilisation principaux

```mermaid
graph TD
    Membre((Membre)) --> UC1[Rechercher un espace disponible]
    Membre --> UC2[Réserver un espace]
    Membre --> UC3[Annuler une réservation]
    Admin((Administrateur)) --> UC4[Gérer les espaces]
    Admin --> UC5[Gérer les membres]
```

## Méthodologie et outils

- Modélisation UML (cas d'utilisation, classes, états, séquences)
- Documentation générée en Word via python-docx
- Soutenance orale de l'analyse

## À venir

Ajout des diagrammes détaillés et du document d'analyse complet (25 cas d'utilisation).
