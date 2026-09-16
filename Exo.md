# Question & action à réaliser



## Comment faire ingérer à votre LLM local le contenu d'un dossier avec quelques pdf ?
  Question & action à réaliser
 

Expliciter la procédure pas à pas pour installer un WebGUI sur votre LLM local (ubuntu)
Pour installer un WebUI , on a utiliser 2 methodes qui depends du besoin et de la configuration en face (si besoin faites les deux car dispo ).

Méthode 1 : Classique via Docker
Partie 1 :
Utilisation : 

Disponible sur tout les appareils qui sont sur le même réseaux que le serveurs WebUI.

Prérequis :

Les services Ollama et docker lancés.

Sinon plus bas pour les installer.

Installation de Docker ( Doc Officiel) : 

# Installationn des paquet requis (ca-certificates= permet à curl de vérifier que la connexion HTTPS/ curl = télécharger des fichiers ou des clés depuis Internet en CLI) + Mises a jour Completes du Systemes
sudo apt update && sudo apt full-upgrade -y
sudo apt install ca-certificates curl

# Sert à créer un dossier sécurisé pour stocker les clés cryptographiques de dépôts de paquets.
sudo install -m 0755 -d /etc/apt/keyrings

# Télécharge la Clef GPG DOCKER + droit a tout le monde de lire la KEY
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Ajoute la source dans APT :
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF
sudo apt update

# Installation maintenant de tout les composant de Dockers
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
Installation de Ollama (Doc Officiel) :

# Installationn des paquet requis (curl = télécharger des fichiers ou des clés depuis Internet en CLI)
sudo apt update && sudo apt full-upgrade -y
sudo apt install ca-certificates curl

# Telecharge un script et execute un script pour l'installation de Ollama
curl -fsSL https://ollama.com/install.sh | sh

## Optionel

# Télécharger une instance IA
ollama pull #nom de l'ia que vous vouluez

# Exécute une instance IA ( après l'avoir pull)
ollama run #nom de l'ia que vous vouluez
Partie 2 :
Installation du Web Ul: 

sudo docker run -d \
  --network=host \
  -v open-webui:/app/backend/data \
  -e OLLAMA_BASE_URL=http://127.0.0.1:11434 \
  --name open-webui \
  --restart always \
  ghcr.io/open-webui/open-webui:main
Partie 3 :

Accéder à l'interface
Ouvrez votre navigateur sur :

En local : http://localhost:8080 ( sur le serveur uniquement)
Depuis une autre machine du réseau : http://<IP_DE_VOTRE_SERVEUR>:8080
(Le premier compte créé sur l'interface sera automatiquement l'administrateur).

Méthode 2: Page Assist sur navigateur (seulement sur pc)
Prérequis:

sudo ss -tulpn | grep 11434
sudo mkdir -p /etc/systemd/system/ollama.service.d
sudo nano /etc/systemd/system/ollama.service.d/override.conf
[Service]

Environment="OLLAMA_HOST=0.0.0.0"

Environment="OLLAMA_ORIGINS=*"
sudo systemctl daemon-reload

sudo systemctl restart ollama
 

Page Assist est une extension open-source qui intègre vos modèles d’IA locaux (Ollama, LM Studio, etc.) directement dans votre navigateur via un volet latéral (sidebar) ou une interface dédiée.

Partie 1 .Télécharger l'extension : 
Lien Chrome web store : 

 
 

Lien Mozilla :

 
 

Lien Edge: 

 
 

Partie 2 : Configuration Page Assist

Apres a voir télécharger l'extension (dans mon cas sur un chromium), Lancez la pour acceder a la d'acces:

suite à venir : 


## Comment modifier le comportement général de notre LLM Local à l'aide d'un fichier ?

## Prouver que votre LLM local à pu ingérer correctement les données de fichiers PDF

## Comment forcer votre LLM local à aller chercher ce qu'il ne sait pas sur Internet, est-ce possible? et si oui comment?

---

# Lexique IA

- [ ] À faire

- Inférence
- RAG
- ChatBot : 
- Paramètre
- DataSet
- Agent IA
- Modèle
- Réseau de Neurones
- Machine Learning :les systèmes apprennent des motifs à partir des données plutôt que d'être programmés explicitement
- NLP
- Qwen
- Deep Learning : sous catégorie du ML utilisant des réseaux de neurones à plusieurs couches
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
