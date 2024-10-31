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

![diagramme 1](https://github.com/user-attachments/assets/79e9e3f4-e012-4c28-8b7f-9b0b50454010)
![diagramme de sequence](https://github.com/user-attachments/assets/f22ac43f-55c5-4dbe-887f-7a618b282fdc)

