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
