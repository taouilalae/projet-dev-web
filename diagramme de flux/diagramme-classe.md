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
