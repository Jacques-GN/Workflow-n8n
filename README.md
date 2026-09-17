# ⚙️ Workflows n8n

Collection de workflows **n8n** pour automatiser des tâches liées à l'intelligence artificielle, à la prospection et à la création de contenu. Ce dépôt est conçu pour accueillir plusieurs automatisations indépendantes et pourra être enrichi au fil du temps.

## 📂 Workflows disponibles

### 🎯 Agent de prospection multi-LLM

**Fichier :** [`Agent-de-prospection.json`](./Agent-de-prospection.json)

Workflow de qualification et d'enrichissement de prospects à partir d'une liste Google Sheets.

- Parcours des prospects un par un
- Qualification avec **Claude**
- Filtrage selon un score de pertinence
- Génération d'un message LinkedIn personnalisé avec **GPT-4o**
- Enrichissement et structuration avec **Llama 3 via Ollama**
- Enregistrement des prospects qualifiés et des prospects ignorés dans **Supabase**

### 🤖 Automatisation LinkedIn IA

**Fichier :** [`LinkedIn-Automation.json`](./LinkedIn-Automation.json)

Workflow de veille et de création de contenu LinkedIn autour de l'IA.

- Collecte d'articles depuis plusieurs flux RSS
- Filtrage, scoring et déduplication des sujets
- Génération d'un contenu avec **OpenAI GPT-4o**
- Possibilité de basculer vers un sujet éducatif lorsqu'aucune actualité pertinente n'est détectée
- Validation humaine par e-mail avant publication
- Publication sur LinkedIn avec ou sans image
- Suivi des résultats dans Google Sheets

## 🧰 Technologies et services

Selon le workflow utilisé, ce dépôt peut s'appuyer sur :

- [n8n](https://n8n.io/) — orchestration des automatisations
- OpenAI — génération et traitement de contenu
- Anthropic Claude — analyse et qualification
- Ollama / Llama — traitement local
- Google Sheets — source ou stockage de données
- Supabase — stockage structuré
- Gmail — notifications et validation humaine
- LinkedIn — publication de contenu
- RSS — collecte de sources d'information

## 🚀 Importer un workflow dans n8n

1. Téléchargez le fichier JSON du workflow souhaité.
2. Ouvrez votre instance n8n, en local ou dans le cloud.
3. Accédez à **Workflows** puis choisissez **Import from File**.
4. Sélectionnez le fichier `.json`.
5. Recréez ou associez les identifiants nécessaires dans n8n.
6. Vérifiez les paramètres propres à votre environnement : feuilles, tables, modèles, adresses e-mail et comptes sociaux.
7. Exécutez un test manuel avant d'activer le workflow.

> Les workflows ne sont pas nécessairement prêts à l'emploi immédiatement : certains nécessitent la configuration de credentials, de bases de données ou de ressources externes.

## 🔐 Configuration et sécurité

- Ne commitez jamais de clés API, tokens, mots de passe ou données personnelles.
- Utilisez les **Credentials** de n8n pour stocker les secrets.
- Remplacez les valeurs d'exemple comme `YOUR_GOOGLE_SHEET_ID` et `YOUR_*_CREDENTIAL` par vos propres paramètres dans n8n.
- Vérifiez les destinataires d'e-mails, les comptes LinkedIn et les connexions aux bases de données avant toute activation.
- Si un secret a été publié par erreur, révoquez-le et régénérez-le immédiatement.

## 🗂️ Organisation du dépôt

```text
.
├── Agent-de-prospection.json
├── LinkedIn-Automation.json
├── LICENSE
└── README.md
```

Chaque nouveau workflow peut être ajouté dans un fichier JSON distinct à la racine du dépôt. Il est recommandé de documenter ici son objectif, ses dépendances et ses étapes principales.

## ➕ Ajouter un workflow

Pour intégrer une nouvelle automatisation :

1. Exportez le workflow depuis n8n au format JSON.
2. Donnez-lui un nom explicite, par exemple `nom-du-workflow.json`.
3. Ajoutez une entrée dans la section **Workflows disponibles**.
4. Documentez les services utilisés, les credentials requis et les éventuelles étapes de configuration.
5. Testez l'import et l'exécution dans une instance n8n propre.

## 📄 Licence

Ce projet est distribué sous licence [MIT](./LICENSE).
