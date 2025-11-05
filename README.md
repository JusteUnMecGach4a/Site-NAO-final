# 🤖 Site de Ressources et d'Informations sur le Robot NAO

## Contexte du Projet

Ce site web a été développé par les étudiants de la section **BTS CIEL (Cybersécurité, Informatique et Réseaux, Électronique) du Lycée Raymond Poincaré de Bar-le-Duc** dans un but purement **pédagogique**.

L'objectif est de centraliser les informations, les ressources techniques, et les outils de développement (comme **Choregraphe** et **Python**) concernant le robot humanoïde **NAO** (Aldebaran/SoftBank Robotics). Le site est destiné à être mis à jour au fil de l'année scolaire en lien avec les activités d'enseignement.

> **Note Importante :** Le contenu de ce site n'est pas destiné à une publication publique sur Internet.

---

## ⚙️ Structure et Technologies

| Élément | Description | Technologies Clés |
| :--- | :--- | :--- |
| **Structure** | Pages HTML5 sémantiques. | HTML5 |
| **Style** | Thème sombre moderne, avec une navigation flexible et un style épuré. | **CSS** (fichier `style.css`), Font Inter (simulée). |
| **Formulaire** | Page de contact avec validation en temps réel (`onblur`/`oninput`) et validation finale (`onsubmit`). Le récapitulatif est affiché dans une nouvelle fenêtre. | **JavaScript** (fichier `formu.js`). |
| **Ressources** | Utilisation d'images, vidéos (`.mp4` local et `iframe` YouTube), et liens vers des documents PDF. | Fichiers locaux et intégration externe. |

---

## 🧭 Aperçu des Pages

### 1. Accueil (`index.html`)
Présente le projet de ressources du BTS CIEL. Contient un historique détaillé du robot NAO, de sa création à son adoption par la RoboCup et les laboratoires, ainsi que l'évolution de la société **Aldebaran** (devenue SoftBank Robotics Europe).

### 2. Présentation du Robot (`presentation.html`)
Décrit les caractéristiques physiques et techniques de NAO :
* **Composants :** 25 degrés de liberté (DDL), capteurs (caméras, micros, télémètre sonar), dispositifs de communication (synthétiseur vocal, LEDs).
* **Architecture :** Processeur Intel ATOM 1,6 GHz sous **Linux** et le middleware **NAOqi**.
* **Fonctionnalités :** Agilité des mouvements, capacité de préhension (mains), équilibre (centrale inertielle) et gestion autonome des chutes, évitement des obstacles (ultra-sons, capteurs aux pieds).

### 3. Moteurs (`moteur.html`)
Page dédiée aux actionneurs du robot. Elle fait référence à des systèmes comme le **DYNAMIXEL-Y** (haute performance, sécurité renforcée par freins électriques et encodeurs absolus) et le servomoteur **Dynamixel XC430-T150BB-T** (contrôle de position/vitesse/PWM, 360° de rotation).

### 4. Développement (`developpement.html`)
Liste les outils pour interagir avec NAO :
* **Chorégraphe :** L'environnement graphique de programmation fourni par Aldebaran.
* **Vidéos :** Intégration de contenu multimédia (MP4 et YouTube) montrant le robot en action.
* **Scripts Python :** Section dédiée aux exemples de code en Python pour le contrôle du robot.

### 5. Contact (`contact.html`)
Formulaire de contact complet et fonctionnel.

---

## 💻 Détails Techniques du Formulaire (`formu.js`)

Le script JavaScript implémente une validation de formulaire robuste :

1.  **Validation Temps Réel (`afficheOubli` / `onblur` / `oninput`)** :
    * Vérification immédiate des champs (Nom, Prénom, Téléphone, Code Postal, Email) à la sortie du champ (`blur`) et pendant la saisie (`input`).
    * Utilisation d'**expressions régulières** (`regExpAlpha`, `regExpTel`, `regExpEmail`, etc.) pour s'assurer du format correct des données.
    * Affichage d'un message d'erreur spécifique sous chaque champ invalide.
2.  **Validation Finale (`verification(event)`)** :
    * Lors de la soumission, tous les champs sont revalidés.
    * Si des erreurs existent (`isFormValid` est `false`), une **alerte native** (`alert()`) est affichée, listant toutes les erreurs et le focus est donné au premier champ invalide.
    * Le champ **Adresse Mail** est rendu **obligatoire uniquement si la case "Newsletter" est cochée**.
3.  **Affichage du Récapitulatif** :
    * Si le formulaire est valide, les données sont récupérées (champs simples, radio, checkbox).
    * Les données sont affichées dans une nouvelle fenêtre contextuelle (`window.open`), stylisée en HTML/CSS, plutôt que dans une simple boîte de dialogue.

---

## 🔗 Pour Commencer

1.  **Cloner le dépôt :**
    ```bash
    git clone [URL_DU_DÉPÔT]
    cd [NOM_DU_DÉPÔT]
    ```
2.  **Lancement :**
    Ouvrez `index.html` dans votre navigateur.
3.  **Tester la Validation :**
    Naviguez vers `contact.html` et testez la soumission du formulaire avec des données incomplètes ou mal formatées pour voir le script JavaScript en action.
