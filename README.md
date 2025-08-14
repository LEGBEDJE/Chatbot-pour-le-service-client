# Chatbot pour le Service Client

Ce projet est un chatbot conçu pour le service client d'un restaurant, développé avec Python et le framework Rasa. Il est destiné à être un exemple pour un portfolio, montrant comment construire un assistant conversationnel capable de gérer les demandes des clients.

## Technologies Utilisées

*   **Python**: Langage de programmation principal.
*   **Rasa**: Framework open-source pour la construction de chatbots.
    *   **Rasa NLU**: Pour la compréhension du langage naturel (Natural Language Understanding).
    *   **Rasa Core**: Pour la gestion du dialogue.
*   **NLTK**: (Natural Language Toolkit) Utilisé par Rasa pour le traitement du langage naturel.
*   **TensorFlow**: Utilisé par Rasa comme backend pour l'apprentissage automatique.

## Fonctionnalités

Ce chatbot de restaurant peut gérer les interactions suivantes :

*   **Salutations** : Accueillir l'utilisateur de manière amicale.
*   **Réservation de table** : Guider l'utilisateur dans le processus de réservation d'une table en demandant le nombre de personnes et l'heure.
*   **Consultation du menu** : Fournir des informations sur le menu du restaurant.
*   **Horaires d'ouverture** : Indiquer les heures d'ouverture et de fermeture du restaurant.
*   **Localisation** : Donner l'adresse du restaurant.
*   **Gestion de l'humeur** : Répondre de manière appropriée si l'utilisateur est content ou mécontent.
*   **Identification** : Se présenter comme un bot si l'utilisateur le demande.

## Exemples de Conversation

**Réserver une table :**

```
Utilisateur: Bonjour
Bot: Bonjour ! Bienvenue au restaurant 'Le Gemini'. Comment puis-je vous aider ?
Utilisateur: Je voudrais réserver une table pour 2 personnes à 20h
Bot: Pour combien de personnes souhaitez-vous réserver ?
Utilisateur: 2
Bot: À quelle heure souhaitez-vous réserver ?
Utilisateur: 20h
Bot: Parfait, j'ai réservé une table pour 2 personnes à 20h.
```

**Consulter le menu :**

```
Utilisateur: Quel est le menu ?
Bot: Voici notre menu : [Lien vers le menu en ligne ou description du menu].
```

## Architecture du Projet

Le projet suit la structure standard d'un projet Rasa :

```
.
├── actions
│   ├── __init__.py
│   └── actions.py
├── data
│   ├── nlu.yml
│   ├── rules.yml
│   └── stories.yml
├── models
│   └── <votre_modèle>.tar.gz
├── tests
│   └── test_stories.yml
├── venv/
├── config.yml
├── credentials.yml
├── domain.yml
└── endpoints.yml
```

*   **`actions/`**: Contient le code pour les actions personnalisées en Python.
*   **`data/`**: Contient toutes les données d'entraînement pour le chatbot.
*   **`models/`**: C'est ici que Rasa sauvegarde les modèles entraînés.
*   **`tests/`**: Contient les tests pour votre chatbot.
*   **`venv/`**: Le répertoire de l'environnement virtuel Python.
*   **`config.yml`**: Le fichier de configuration principal.
*   **`credentials.yml`**: Contient les informations d'identification pour les canaux externes.
*   **`domain.yml`**: Le "cerveau" du chatbot.
*   **`endpoints.yml`**: Configure les points de terminaison pour les actions personnalisées.

## Démarrage Rapide

1.  **Clonez le projet** :
    ```bash
    git clone git@github.com:LEGBEDJE/Chatbot-pour-le-service-client.git
    ```

2.  **Créez et activez l'environnement virtuel** :
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Installez les dépendances** :
    ```bash
    pip install -r requirements.txt
    ```

4.  **Entraînez le modèle Rasa** :
    ```bash
    ./venv/bin/rasa train
    ```

5.  **Lancez le chatbot** :
    ```bash
    ./venv/bin/rasa shell
    ```

## Pistes d'Amélioration

*   **Actions Personnalisées** : Implémenter des actions en Python (`actions.py`) pour interagir avec une véritable base de données de réservation.
*   **Extraction d'Entités Améliorée** : Utiliser des techniques plus avancées pour extraire des informations plus complexes comme des dates.
*   **Intégration de Canaux** : Connecter le chatbot à des plateformes comme Facebook Messenger ou WhatsApp.
*   **Tests et Validation** : Écrire des tests plus complets.
*   **Déploiement** : Déployer le chatbot sur un serveur.