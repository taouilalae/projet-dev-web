classDiagram
    class Utilisateur {
        +int id
        +String nomUtilisateur
        +String email
        +String preferences
    }

    class Formulaire {
        +saisirReponse()
        +afficherResultats()
    }

    class Admin {
        +gererFormulaires()
        +visualiserDonnees()
    }

    class SystemeGoogleSheets {
        +envoyerDonnees()
        +recupererDonnees()
        +afficherDonnees()
    }

    Utilisateur "1" --> "*" Formulaire : utilise
    Formulaire "1" --> "1" SystemeGoogleSheets : enregistre
    Admin "1" --> "*" SystemeGoogleSheets : gère

    SystemeGoogleSheets <|-- Formulaire
    SystemeGoogleSheets <|-- Admin


sequenceDiagram

    participant Utilisateur
    participant Formulaire
    participant SystemeGoogleSheets as Google Sheets
    participant Admin

    %% Interactions Utilisateur
    Utilisateur->>+Formulaire: Saisir Réponse
    Formulaire->>+SystemeGoogleSheets: Enregistrer Réponse
    SystemeGoogleSheets-->>-Formulaire: Confirmation Enregistrement
    Formulaire-->>-Utilisateur: Confirmation

    %% Interactions Admin
    Admin->>+SystemeGoogleSheets: Consulter Données
    SystemeGoogleSheets-->>-Admin: Données des Réponses

    Admin->>+SystemeGoogleSheets: Gérer Formulaire
    SystemeGoogleSheets-->>-Admin: Confirmation Gestion

# Diagrammes de Flux et de Séquence

## Diagramme de Classe
Voici le diagramme de classe de notre projet :

![Diagramme de Classe](https://github.com/user-attachments/assets/79e9e3f4-e012-4c28-8b7f-9b0b50454010)

## Diagramme de Séquence
Voici le diagramme de séquence de notre projet :

![Diagramme de Séquence](https://github.com/user-attachments/assets/f22ac43f-55c5-4dbe-887f-7a618b282fdc)

## Description des Diagrammes
- **Diagramme de Classe** : Il représente les différentes classes et leurs relations dans le système.
- **Diagramme de Séquence** : Il montre l'interaction entre les différents acteurs (Utilisateur, Admin, Système) lors de l'enregistrement et de la consultation des données.

