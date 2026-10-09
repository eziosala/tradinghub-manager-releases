# TradingHub Manager

**Votre robot TradingHub sur MetaTrader 5, installé et surveillé pour vous.**

TradingHub Manager est une application Windows qui prend en charge toute l'installation : MetaTrader 5, la connexion
à votre compte PU Prime, le graphique, le robot de votre groupe et ses réglages. Vous saisissez votre UserID et vos
identifiants MT5, le Manager fait le reste, puis veille à ce que tout continue de tourner.

**[Télécharger TradingHub Manager pour Windows](https://github.com/eziosala/tradinghub-manager-releases/releases/latest/download/TradingHub-Manager-Setup.exe)**

## Ce que fait le Manager

- **Installe MetaTrader 5** depuis l'installateur officiel de PU Prime.
- **Connecte vos comptes**, un ou plusieurs, chacun dans son propre MetaTrader 5, sans interférence entre eux.
- **Place le robot** sur le graphique XAUUSD, avec votre UserID, le trading algorithmique et l'accès à notre serveur
  déjà autorisés.
- **Surveille vos comptes** et relance tout seul un MetaTrader 5 qui se serait fermé.
- **Redémarre vos robots** après un redémarrage du PC ou du VPS, sans que vous ayez à vous connecter.
- **Met le robot à jour** dès qu'une nouvelle version est publiée pour votre groupe.

## Avant de commencer

- Un PC ou un VPS sous **Windows 10, Windows 11 ou Windows Server**. Sur Mac, passez par un VPS.
- Votre **UserID** : il est sur votre profil du panel web, et dans la fenêtre « Appairer un robot ». C'est lui qui
  désigne le robot de votre groupe.
- Pour chaque compte : le **numéro de compte**, le **mot de passe** et le **serveur** indiqués dans l'e-mail de PU Prime.
- Environ **1 Go d'espace libre**, plus 500 Mo par compte.

## Installation

1. **Téléchargez** TradingHub Manager avec le lien ci-dessus, puis lancez `TradingHub-Manager-Setup.exe`.
   L'installation est immédiate et ne demande pas de droits administrateur.
   Si Windows affiche « Windows a protégé votre ordinateur », cliquez sur **Informations complémentaires**, puis
   **Exécuter quand même** : l'application n'est pas encore signée, et Windows avertit pour tout programme récent
   qu'il ne connaît pas. Vous pouvez d'abord [vérifier le fichier](#vérifier-le-téléchargement).
2. **Saisissez votre UserID.** Le Manager affiche le nom de votre groupe pour confirmer.
3. **Cliquez sur « Installer MetaTrader 5 ».** Comptez quelques minutes. Windows peut vous demander une autorisation
   pendant l'installation : acceptez-la.
4. **Choisissez le démarrage** :
   - *Démarrage automatique* (conseillé) : le Manager s'ouvre avec Windows et relance vos comptes.
   - *Ouverture de session automatique* : pour un VPS, voir plus bas.

## Ajouter un compte

Cliquez sur **« Ajouter un compte »** et remplissez :

| Champ | Ce qu'il faut mettre |
|---|---|
| Nom d'affichage | Facultatif, pour vous y retrouver (« Compte réel », « Démo »…) |
| Robot | Seulement si votre groupe propose plusieurs robots : celui à installer sur ce compte (modifiable ensuite) |
| Numéro de compte MT5 | Celui de l'e-mail PU Prime |
| Mot de passe MT5 | Le mot de passe principal du compte |
| Serveur | Celui de l'e-mail PU Prime : choisissez-le dans la liste ou saisissez-le |
| Symbole | `XAUUSD.sc` pour un compte cent (USC), `XAUUSD.s` pour un compte standard (USD) |
| Période du graphique | M15 par défaut |

Le Manager prépare MetaTrader 5, connecte le compte et lance le robot. Quand le statut passe à **Connectée**, ouvrez le
panel web : une **demande d'appairage** vous y attend, acceptez-la. Votre robot apparaît alors dans votre tableau de
bord.

Vous pouvez ajouter autant de comptes que votre machine le permet.

## Au quotidien

Chaque compte affiche son statut :

| Statut | Signification |
|---|---|
| **Connectée** | MetaTrader 5 tourne, le compte est connecté, le robot travaille. |
| **Démarrage** | Le Manager lance MetaTrader 5 et connecte le compte. |
| **Arrêtée** | Vous avez arrêté ce compte : il ne redémarre pas tout seul. |
| **Erreur** | Le compte n'a pas pu se connecter ; le message explique pourquoi. |

Pour chaque compte : **Démarrer** ou **Arrêter**, **Redémarrer**, **Afficher MT5** (ouvre sa fenêtre MetaTrader 5),
**Modifier** (mot de passe, serveur, symbole, période) et **Supprimer**.

Fermer la fenêtre du Manager ne l'arrête pas : il reste dans la zone de notification, à côté de l'horloge, et
continue de surveiller vos comptes. Même en le quittant, vos MetaTrader 5 continuent de tourner.

## Sur un VPS

Activez **« Ouverture de session automatique »** dans les paramètres. Après un redémarrage du VPS (mise à jour
Windows, maintenance de l'hébergeur…), Windows ouvre la session tout seul et vos robots repartent, sans connexion
Bureau à distance. Votre mot de passe Windows est confié à Windows lui-même, chiffré ; le Manager ne le garde pas.

L'option **« Verrouiller la session après le démarrage »** verrouille ensuite l'écran : vos robots continuent de
tourner.

> **Important** : pour quitter le Bureau à distance, fermez la fenêtre avec la **croix**. N'utilisez jamais
> « Déconnexion » ou « Se déconnecter » : cela ferme la session et arrête MetaTrader 5.

## Mises à jour

- **Le robot** se met à jour tout seul, vérifié au démarrage puis toutes les 6 heures. Vos comptes redémarrent
  quelques secondes avec la nouvelle version. Vous pouvez aussi vérifier tout de suite depuis les paramètres.
- **Le Manager** télécharge ses nouvelles versions en arrière-plan. Un bandeau vous le signale : cliquez sur
  « Mettre à jour ». Vos comptes continuent de tourner pendant la mise à jour.

## Vos données et votre sécurité

- **Vos mots de passe MT5 restent sur votre machine**, chiffrés par Windows. Ils ne sont jamais envoyés à TradingHub :
  seul MetaTrader 5 s'en sert pour se connecter à PU Prime.
- **Le robot est vérifié** avant d'être installé : un fichier qui ne porte pas la signature de TradingHub est refusé.
- **MetaTrader 5 vient de l'installateur officiel de PU Prime**, dont la signature est contrôlée avant de le lancer.
- **Chaque version publie l'empreinte de son installateur**, pour vérifier que le fichier n'a pas été modifié.

## Vérifier le téléchargement

Avant de lancer l'installateur, vous pouvez vous assurer que c'est bien le fichier publié ici et qu'aucun antivirus
ne le signale.

**Avec VirusTotal** (service gratuit qui fait analyser un fichier par plus de 60 antivirus) :

1. Ouvrez la [page des versions](https://github.com/eziosala/tradinghub-manager-releases/releases/latest) : sous
   « Vérifier le fichier », cliquez sur le lien VirusTotal.
2. Si la page affiche déjà une analyse, regardez le résultat en haut : **0** (ou un seul moteur peu connu) signifie
   que le fichier est sain.
3. Si VirusTotal ne connaît pas encore le fichier, allez sur [virustotal.com](https://www.virustotal.com), onglet
   **File**, et déposez `TradingHub-Manager-Setup.exe`. L'analyse prend une à deux minutes.

**Avec l'empreinte SHA-256** (pour vérifier que le fichier n'a pas été modifié) : dans le menu Démarrer, ouvrez
**Windows PowerShell**, puis tapez :

```powershell
Get-FileHash "$env:USERPROFILE\Downloads\TradingHub-Manager-Setup.exe"
```

La valeur affichée sous `Hash` doit être identique, à la casse près, à celle indiquée dans la page de la version.

## En cas de problème

| Message | Que faire |
|---|---|
| UserID inconnu | Recopiez-le depuis votre profil du panel web (il commence par `U`). |
| Identifiant, mot de passe ou serveur incorrect | Vérifiez les trois dans l'e-mail de PU Prime, puis « Modifier ». |
| Le serveur MT5 n'a pas répondu | Vérifiez le nom du serveur et votre connexion Internet, puis « Redémarrer ». |
| Arrêts répétés : la relance automatique est suspendue | Cliquez sur « Redémarrer ». Si cela se reproduit, contactez le support. |
| Espace disque insuffisant | Libérez de la place (500 Mo par compte), puis réessayez. |
| Alerte de sécurité | Ne forcez rien et contactez le support. |

Pour le support, **Paramètres → Exporter pour le support** crée une archive des journaux du Manager, sans aucun mot
de passe. Envoyez-la au support de votre groupe sur Telegram.

## Réparer ou mettre à jour

Téléchargez l'installateur avec le lien en haut de cette page et relancez-le : il remplace la version installée,
sans toucher à vos comptes ni à vos réglages. Cela met à jour le Manager, ou le répare s'il ne démarre plus
correctement. Vos MetaTrader 5 continuent de tourner pendant l'opération.

## Désinstaller

1. Dans le Manager, **arrêtez vos comptes**. Si l'*Ouverture de session automatique* est activée, désactivez-la
   dans les paramètres : c'est un réglage de Windows, que la désinstallation ne retire pas.
2. Désinstallez **TradingHub Manager** depuis *Paramètres Windows → Applications*. Le démarrage automatique est
   retiré avec lui.
3. Vos comptes MetaTrader 5 et leurs données restent sur le PC. Pour les effacer aussi, supprimez le dossier
   `%LOCALAPPDATA%\TradingHubManager`.


## À propos de ce dépôt

Ce dépôt ne contient que les versions publiées de TradingHub Manager, dans l'onglet
[Releases](https://github.com/eziosala/tradinghub-manager-releases/releases). Le code source de l'application n'y est
pas.

Chaque version publie :

- `TradingHub-Manager-Setup.exe`, l'installateur ;
- son empreinte SHA-256 et le lien de son analyse VirusTotal, dans les notes de la version ;
- `latest.yml` et `TradingHub-Manager-Setup.exe.blockmap`, que le Manager lit pour se mettre à jour tout seul.

Les questions et demandes d'aide passent par le support de votre groupe sur Telegram.
