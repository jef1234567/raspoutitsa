# Raspoutitsa en réseau

Sans `firebase-config.js` rempli, les pages restent en copier-coller.

## Installation (une seule fois, par l'administrateur)
1. Sur console.firebase.google.com, créer un projet (Google Analytics inutile).
2. Build > Authentication > Commencer > activer « Adresse e-mail/Mot de passe ».
3. Onglet Users > créer ces trois comptes, chacun avec son mot de passe :
   - bleu@raspoutitsa.example
   - rouge@raspoutitsa.example
   - arbitre@raspoutitsa.example
4. Build > Realtime Database > Créer une base (Belgique, mode verrouillé).
5. Onglet Règles : coller tout le contenu de `database.rules.json`, puis Publier.
6. Paramètres du projet > Vos applications > icône Web `</>` > enregistrer l'application,
   puis recopier les valeurs dans `firebase-config.js`, y compris databaseURL.
7. Sur GitHub, créer un dépôt, y déposer tous les fichiers de ce dossier, puis
   Settings > Pages > branche main, dossier racine.

## Adresses
- Webapp : https://jef1234567.github.io/raspoutitsa/
- CMI : https://<compte>.github.io/<depot>/joueur.html
- Arbitre : https://<compte>.github.io/<depot>/arbitre.html

Le mot de passe de chaque camp ne se donne qu'à son CMI.

## Déroulé d'une partie
1. Arbitre : onglet Partie > « Préparer une nouvelle partie : tout vider ».
2. CMI : déploiement, puis « Valider et envoyer à l'arbitre ».
3. Arbitre : contrôle les fiches, renvoie avec un motif si besoin, puis « Commencer la partie ».
4. À chaque tour : les ordres arrivent, l'arbitre ajuste puis valide deux fois, chaque CMI lit
   son compte rendu puis met son plateau à jour.
5. Si un tour est annulé dans l'Historique : valider de nouveau le tour envoie un compte rendu rectificatif.

La connexion dure tant que l'onglet reste ouvert. Exporter la partie reste possible dans l'onglet Partie.
