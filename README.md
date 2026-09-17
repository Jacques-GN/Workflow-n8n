# 🤖 LinkedIn AI Personal Branding Automation (n8n)

Un système d'automatisation complet bâti sur **n8n** et **OpenAI (GPT-4o)** qui veille sur l'actualité IA mondiale, génère des analyses stratégiques et gère la publication sur LinkedIn avec validation humaine.

---

### 🛠️ Architecture & Technologies

* **Orchestrateur :** n8n (Self-hosted / Cloud)
* **Ingestion :** 10 flux RSS FR/EN (OpenAI, Anthropic, MIT Tech Review, Hugging Face, etc.)
* **Traitement de données :** JavaScript ES6 (Filtering, Scoring & Deduplication)
* **Intelligence Artificielle :** OpenAI GPT-4o (Génération) + GPT-4o-mini (Formatting HTML)
* **Human-in-the-Loop :** Gmail API (Système d'approbation interactive "Send & Wait")
* **Stockage & Publication :** Google Sheets API & LinkedIn API

---

### 🔄 Fonctionnement du Workflow

1. **Déclenchement :** S'exécute automatiquement 2 fois par jour (8h00 et 18h00).
2. **Collecte & Scoring :** Récupère les articles des dernières 72h, applique un score de pertinence basé sur plus de 80 mots-clés techniques LLM/IA et élimine les doublons.
3. **Mode Fallback :** Si aucune actualité majeure n'est détectée, le système bascule automatiquement sur un sujet éducatif technique (RAG, Transformer, Embeddings).
4. **Génération d'analyse :** GPT-4o rédige un post structuré sans hype, adapté aux builders et développeurs IA.
5. **Validation Humaine :** Un e-mail HTML dynamique est envoyé via Gmail. La publication LinkedIn ne s'exécute que si l'utilisateur clique sur **"Approuver & Publier"**.
6. **Logging & Publication :** Traçabilité complète dans Google Sheets et publication automatique de l'image et du texte sur LinkedIn.

---

### 🚀 Comment importer le workflow ?

1. Téléchargez le fichier `workflow.json`.
2. Ouvrez votre instance **n8n**.
3. Cliquez sur **Workflows** > **Import from File** et sélectionnez `workflow.json`.
4. Configurez vos identifiants pour OpenAI, Google Sheets, Gmail et LinkedIn.
