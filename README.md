# Chatbot pour le Service Client

Ce projet est un chatbot conçu pour le service client, développé avec Python et le framework Rasa. 

## Technologies Utilisées

*   **Python**: Langage de programmation principal.
*   **Rasa**: Framework open-source pour la construction de chatbots.
    *   **Rasa NLU**: Pour la compréhension du langage naturel (Natural Language Understanding).
    *   **Rasa Core**: Pour la gestion du dialogue.
*   **NLTK**: (Natural Language Toolkit) Utilisé par Rasa pour le traitement du langage naturel.
*   **TensorFlow**: Utilisé par Rasa comme backend pour l'apprentissage automatique.

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

*   **`actions/`**: Contient le code pour les actions personnalisées en Python. Ces actions peuvent être utilisées pour exécuter du code, comme appeler une API externe ou se connecter à une base de données.
*   **`data/`**: Contient toutes les données d'entraînement pour le chatbot.
    *   **`nlu.yml`**: Définit les intentions (ce que l'utilisateur veut faire) and les entités (les informations à extraire du message de l'utilisateur).
    *   **`rules.yml`**: Contient des règles pour les conversations qui doivent suivre un chemin prédéfini.
    *   **`stories.yml`**: Contient des exemples de conversations (histoires) pour entraîner le modèle de dialogue du chatbot.
*   **`models/`**: C'est ici que Rasa sauvegarde les modèles entraînés.
*   **`tests/`**: Contient les tests pour votre chatbot.
*   **`venv/`**: Le répertoire de l'environnement virtuel Python, contenant les dépendances du projet.
*   **`config.yml`**: Le fichier de configuration principal. Il définit le pipeline NLU et les politiques de dialogue.
*   **`credentials.yml`**: Contient les informations d'identification pour connecter le chatbot à des canaux de messagerie externes (ex: Facebook Messenger, Slack).
*   **`domain.yml`**: Le "cerveau" du chatbot. Il définit toutes les intentions, entités, réponses, et actions que le chatbot connaît.
*   **`endpoints.yml`**: Utilisé pour configurer les points de terminaison (endpoints) pour les actions personnalisées et d'autres services.

## Démarrage Rapide

Pour faire fonctionner ce projet sur votre machine locale, suivez ces étapes :

1.  **Clonez le projet** git clone https://github.com/LEGBEDJE/Chatbot-pour-le-service-client.

2.  **Créez et activez l'environnement virtuel** (si ce n'est pas déjà fait) :
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Installez les dépendances** :
    ```bash
    pip install -r requirements.txt
    ```
    *(Note: Un fichier `requirements.txt` sera créé pour vous)*

4.  **Entraînez le modèle Rasa** :
    ```bash
    ./venv/bin/rasa train
    ```

5.  **Lancez le chatbot** :
    ```bash
    ./venv/bin/rasa shell
    ```

## Comment Utiliser

Une fois le chatbot lancé avec `rasa shell`, vous pouvez commencer à interagir avec lui directement dans votre terminal. Le chatbot initial est un simple assistant, mais vous pouvez l'étendre pour gérer des scénarios de service client plus complexes.
