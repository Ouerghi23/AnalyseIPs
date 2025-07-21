# AnalyseIPs
# 🔎 Analyse IP Automatique avec n8n, OTX, VirusTotal et Telegram

Ce workflow `n8n` permet d’analyser automatiquement une adresse IP entrée par l'utilisateur en combinant les données de deux services :
- [AlienVault OTX](https://otx.alienvault.com)
- [VirusTotal](https://www.virustotal.com)

Il évalue le niveau de dangerosité de l’IP, attribue un score de risque, et envoie une **alerte Telegram** personnalisée.

---

## ⚙️ Fonctionnalités

- 🔗 Intégration avec les APIs OTX & VirusTotal
- 🔒 Détection d’IP suspectes ou malicieuses
- 🎯 Attribution d’un niveau de risque (safe, suspicious, malicious)
- 🚨 Notification Telegram automatique
- ✅ Personnalisable selon vos critères de scoring

---

## 🧱 Structure du Workflow n8n

1. `Manual Trigger` — Déclencheur manuel
2. `Set` — Saisie de l’adresse IP
3. `HTTP Request` — Appel API OTX
4. `HTTP Request` — Appel API VirusTotal
5. `Merge` — Fusion des résultats
6. `Function` — Calcul du risque et structuration des données
7. `Telegram` — Envoi d’un message Telegram avec le statut

---

## 🔐 Clés API nécessaires

Créer les comptes suivants pour obtenir vos clés :

- 🧪 **OTX** : [Créer un compte](https://otx.alienvault.com)
  - Clé API à ajouter dans l'en-tête : `X-OTX-API-KEY`
- 🧪 **VirusTotal** : [Créer un compte](https://www.virustotal.com/gui/join-us)
  - Clé API à ajouter dans l'en-tête : `x-apikey`
- 💬 **Telegram Bot** :
  - Créer un bot avec [@BotFather](https://t.me/botfather)
  - Obtenir le `Token` et `Chat ID`

---

## 📦 Importer le Workflow

1. Ouvrir votre instance n8n.
2. Cliquer sur "Import" > "Upload JSON".
3. Sélectionner le fichier `Analyse_IPs.json`.
4. Modifier les paramètres suivants :
   - Ajouter vos clés API dans les nœuds HTTP
   - Ajouter le `Bot Token` et `Chat ID` dans le nœud Telegram

---

## ✅ Exemple de message Telegram

🟠 Analyse IP :

Adresse IP : 185.234.247.225
Niveau : SUSPICIOUS
Score : 30

Analyse : 1 pulses OTX, 1 détection VT


---

## 💡 Personnalisation

Tu peux adapter :
- Les poids du score dans le nœud `Function`
- Le format du message Telegram
- L’entrée via Webhook au lieu de manuel (`Manual Trigger`)

---

## 👩‍💻 Auteur

- 👤 Chaima Ouerghi  
- 📅 Juillet 2025  

---

## 📁 Fichiers inclus

- `Analyse_IPs.json` : le workflow prêt à être importé
- `README.md` : ce fichier de documentation

