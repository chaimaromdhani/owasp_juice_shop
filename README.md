# Pentest OWASP Juice Shop

Test d'intrusion de l'application web volontairement vulnérable OWASP Juice Shop, réalisé dans un environnement local isolé. Projet individuel (cycle ingénieur SSIR, TEK-UP).

## Objectif

Identifier des vulnérabilités applicatives, démontrer leur exploitation, mesurer leur impact et proposer des corrections.

## Environnement et outils
Attaquant : Kali Linux
Cible : OWASP Juice Shop (Node.js / Express) sur localhost:3000
Outils : Nmap, WhatWeb, Gobuster, Dirsearch, Burp Suite, DevTools Firefox, jwt_tool, JWT.io
## Démarche
Reconnaissance : découverte du service (Nmap, WhatWeb), énumération des répertoires (/ftp, /rest, /api) et des endpoints d'API.
Analyse de session : décodage du jeton JWT et lecture de son contenu (e-mail, rôle, identifiant).
Exploitation et recommandations pour chaque faille.
Vulnérabilités exploitées
Vulnérabilité	Résultat	Correction recommandée
Injection SQL (contournement d'authentification)	Accès au compte administrateur	Requêtes paramétrées, ORM
XSS dans la barre de recherche	Exécution de JavaScript dans le navigateur	Encodage des sorties, CSP
Exposition de fichiers sensibles (/ftp)	Lecture de documents internes	Restreindre l'accès aux répertoires
Broken Access Control (IDOR sur /rest/basket/{id})	Accès au panier d'un autre utilisateur	Contrôle d'accès côté serveur
JWT non signé (alg: none)	Usurpation d'un utilisateur	Vérification stricte de la signature
Ce que j'ai appris

Enchaîner reconnaissance, exploitation et rédaction de recommandations, et manipuler Burp Suite et les jetons JWT.

Usage pédagogique uniquement, sur une application conçue pour cela.
