# Question & action à réaliser

Procèdure pas à pas de la mise en place du WebGui pour le LLM.

Près-requis :  
- Curl
- ollama (avec le choix de son IA, nous avons choisi Mistral)
- Docker

Installation des certificats :
-sudo apt update sudo apt install -y curl apt-transport-https ca-certificates gnupg lsb-release

Lancement du docker :

sudo docker run -d   --network=host   -v open-webui:/app/backend/data   -e OLLAMA_BASE_URL=http://127.0.0.1:11434   --name open-webui   --restart always   ghcr.io/open-webui/open-webui:main 

## Comment faire ingérer à votre LLM local le contenu d'un dossier avec quelques pdf ?
  
## Comment modifier le comportement général de notre LLM Local à l'aide d'un fichier ?

## Prouver que votre LLM local à pu ingérer correctement les données de fichiers PDF

## Comment forcer votre LLM local à aller chercher ce qu'il ne sait pas sur Internet, est-ce possible? et si oui comment?

---

# Lexique IA

- [ ] À faire

- Inférence
- RAG
- ChatBot
- Paramètre
- DataSet
- Agent IA
- Modèle
- Réseau de Neurones
- Machine Learning
- NLP
- Qwen
- Deep Learning
- GPT
- IA Adpatative
- IA Générale
- Ollama
- IA Générative
- Singularité Technologique
- LLM
- Hallucination
- Embedding
- Token
- European AI Act
- Prompt
- Algorithme
- Test de Turing
- Big Data
- Biais
- ModelFile
- SystemPrompt
- Deep Learning
- Données

---

### THM

![IAStart](img/thm.png)

---

### VMWARE

![Pacquets Installés](img/deb.png)

---

### WSL

![Distri wsl](img/wsl.png)
