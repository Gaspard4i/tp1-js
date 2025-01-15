<img src="images/readme/header-small.jpg" >

# A. Préparatifs <!-- omit in toc -->

## Sommaire <!-- omit in toc -->
- [A.1. Installations](#a1-installations)
- [A.2. À propos de ce repo](#a2-à-propos-de-ce-repo)
- [A.3. Récupération des fichiers](#a3-récupération-des-fichiers)
- [A.4. VSCod\[e/ium\]](#a4-vscodeium)
- [A.5. Ouvrir le projet dans VSCodium](#a5-ouvrir-le-projet-dans-vscodium)


## A.1. Installations
**Avant de démarrer le TP il va vous falloir faire quelques installs et configurations.** Selon que vous utilisez une machine de l'Université ou votre propre ordinateur la situation n'est pas la même :

### Si vous êtes sur une machine des salles TP de l'IUT <!-- omit in toc -->
Dans ce cas, un certain nombre de logiciels sont déjà pré-installés (notamment Git et VSCode) mais vous aurez quand même besoin d'installer une version de **NodeJS** plus récente que celle fournie de base sur les machines.

Suivez donc [ce tuto spécifique aux machines des salles TP de l'IUT](A-preparatifs-linux.md) puis revenez suivre la suite du TP ici.

### Si vous utilisez votre propre machine <!-- omit in toc -->
Dans ce cas il vous faudra installer :
- **Git** : https://git-scm.com/
- **Node.js** (_version "Current" **23.x**_): https://nodejs.org/en/download/current

	> <details><summary>⚠️ <em><strong>ATTENTION</strong> : vous avez <strong>déjà Node</strong> sur votre machine ?</em></summary>
	>
	> _Pour être certain·e de ne pas avoir de soucis pendant les TPs il vous faudra la dernière version stable._
	>
	> _Si vous aviez déjà une version plus ancienne de Node (tapez `node -v` dans un terminal pour en avoir le coeur net) alors vous devez la **DÉSINSTALLER COMPLÈTEMENT** avant d'installer la nouvelle version._
	> </details>

	> <details><summary>⚠️ <em><strong>ATTENTION (bis)</strong> : vous êtes sous <strong>Windows</strong> ? Vous devez OBLIGATOIREMENT ...</em></summary>
	>
	> _... télécharger l'installer (partie "`Or get a prebuilt Node.js ...`" en bas de page) et pendant le processus d'installation de Node, **COCHER** la case "Automatically install the necessary tools. ..." sur l'écran **"Tools for native modules"**_
	>
	> <img src="images/readme/node-install.png" >
	>
	> _Cette case permettra d'installer des dépendances utiles pour la suite (notamment python et les visual c++ build tools)._
	>
	> _Si vous utilisez un autre moyen pour installer Node ([fnm](https://github.com/Schniz/fnm) par exemple), alors il faudra installer [chocolatey](https://chocolatey.org/install) puis les 2 paquets ci-dessous :_
	>
	> ```bash
	> choco install python visualstudio2019-workload-vctools
	> ```
	> </details>

- **VSCodium** https://vscodium.com ou **VSCode** https://code.visualstudio.com

	> ℹ️ _Si vous avez déjà VSCode, ça fera très bien l'affaire, VSCodium et VSCode sont quasi identiques (on y reviendra dans la partie [A.4. VSCod\[e/ium\]](#a4-vscodeium)) !_


## A.2. À propos de ce repo

**Ce repo contient un ensemble de fichiers qui vous seront utiles pour la réalisation de ce TP.**

Il contient notamment des fichiers html, css et des assets graphiques (images et vidéos) qui vous permettront de vous concentrer sur le JS sans trop vous soucier de l'apparence de ce que vous codez tout en ayant **quand même** quelque chose de présentable visuellement 😎

La première étape est donc de récupérer (_via git_) les fichiers du TP.<br>
_**Allons-y !**_

## A.3. Récupération des fichiers

**La solution la plus simple pour récupérer les fichiers du TP consiste à cloner ce repository à l'aide de git :**

1. **Commencez par faire un fork du TP :**
	- soit en cliquant sur le bouton `"Créer une divergence"` (_`"Fork"` sur la version anglaise de gitlab_)
	- soit en vous rendant directement sur https://gitlab.univ-lille.fr/js/tp1/-/forks/new

	**⚠️ ATTENTION :** Choisissez de placer votre fork **dans VOTRE profil utilisateur** (`namespace`) \
	et vérifiez que le repo est **bien en mode "private"** (`Visibility Level`)

2. **Ajoutez votre encadrant.e de TP en tant que "reporter" pour qu'il/elle ait accès à votre code :**
	- dans le menu de gauche, cliquez sur **`Manage`** &gt; **`Members`** (`Gestion` &gt; `Membres` _si vous êtes sur la VF de gitlab_)
	- cliquez sur le bouton en haut à droite **`"Invite members"`** (`Inviter des membres`)
	- entrez comme **nom d'utilisateur** celui de votre encadrant.e de TP (`@patricia.everaere-caillier`, `@catherine.verbrugge` ou `@thomas.fritsch`)
	- ... et `"reporter"` comme **rôle**.

3. **Ouvrez un terminal** *(si vous êtes sous Windows, utilisez **Git bash** installé automatiquement avec Git)*

4. **Récupérez ensuite les fichiers de ce TP grâce à Git : clonez votre fork dans un dossier de votre choix** (_dans mon exemple `chemin/vers/votre/workspace/tp1`_):
	```bash
	cd chemin/vers/votre/workspace
	git clone https://gitlab.univ-lille.fr/<votre-username>/tp1.git
	```
	> <details><summary>⚠️ <em>Si vous êtes sous <strong>Windows</strong> attention aux slashs...</em></summary>
	>
	> _ici je clone dans le dossier `chemin/vers/votre/workspace/tp1`. **Si vous êtes sous Windows faites attention aux slashs dans le chemin du dossier** : utilisez **Git bash** (qui comprend cette syntaxe) ou si vous tenez vraiment à utiliser **cmd** ou **powershell** pensez à adapter la commande en les remplaçant par des antislash `\` !_
	> </details>

	> <details><summary>ℹ️ <em>Si ce n'est pas déjà fait, il faut que vous renseigniez un mot de passe dans votre compte gitlab</em></summary>
	>
	> _Rendez-vous dans [`Preferences` > `Password`](https://gitlab.univ-lille.fr/-/profile/password/edit) pour pouvoir cloner en http._
	> </details>

	> <details><summary>ℹ️ <em>Si vous préférez <strong>cloner en SSH</strong>...</em></summary>
	>
	> _...pour ne pas avoir à taper votre mot de passe à chaque fois que vous clonerez un TP, renseignez votre clé SSH dans votre [compte utilisateur gitlab](https://gitlab.univ-lille.fr/-/profile/keys) et clonez à partir de cette URL : `git@gitlab-ssh.univ-lille.fr:votre-username/tp1.git`_
	> </details>

## A.4. VSCod\[e/ium\]

_**Pour développer en JS, je vous recommande d'utiliser un éditeur adapté au JS moderne. Si vous ne l'avez pas encore testé, je ne peux que vous recommander d'utiliser Visual Studio Code / VSCodium au moins pour la durée de ce cours.**_

<img src="images/readme/vscode-ium.jpg" />

[Visual Studio Code](https://code.visualstudio.com/) (vscode) est à l'heure actuelle l'un des éditeurs les plus **populaires** pour le développement web et en particulier dans l'écosystème JS. C'est un éditeur opensource et développé avec [Electron](https://electronjs.org/), c'est donc un outil qui est **lui-même développé en JS !**

Malheureusement des questions de licence liées à Microsoft [plus ou moins obscures](https://vscodium.com/#why) viennent ternir un peu le tableau. Je vous conseille donc d'utiliser **la distribution "vraiment opensource" du logiciel qu'est [VSCodium](https://vscodium.com/)** (_aucune différence de fonctionnalité, hormis le [store d'extensions](https://github.com/VSCodium/vscodium/blob/master/DOCS.md#extensions-marketplace)_).

> <details><summary>ℹ️ <em>Vous avez déjà VSCode ?</em></summary>
>
> _Si vous avez déjà VSCode et que vous ne souhaitez pas faire la bascule vers VSCodium, pas de soucis pour ce cours, comme les deux sont strictement identiques en terme de fonctionnalités (hormis le store d'extension qui diffère), les TP fonctionneront de la même manière avec vscode !_
> </details>


1. **Ouvrez le panneau des extensions de VSCod\[e/ium\]** à l'aide du raccourci <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>X</kbd>

2. **Installez l'extension `Prettier - Code formatter`** (_esbenp.prettier-vscode_)

	Prettier permet de formater automatiquement notre code en respectant de base un certain nombre de bonnes pratiques. Les possibilités de configuration sont volontairement limitées mais suffisantes pour avoir quand même l'impression d'avoir encore un peu la main sur son formatage 😄

	On configurera cette extension dans les prochains TP.

## A.5. Ouvrir le projet dans VSCodium

_**Pour travailler efficacement avec vscodium, je vous recommande d'ouvrir le DOSSIER de votre projet plutôt que d'ouvrir les fichiers un à un. Cela vous permettra notamment de passer plus rapidement de l'un à l'autre.**_

1. **Commencez donc par ouvrir le dossier du TP dans VSCodium :**
	- soit en lançant VSCodium **depuis un terminal** directement dans le dossier (*adaptez le chemin vers le projet*):
		```bash
		codium chemin/vers/votre/workspace/tp1
		```
		> ℹ️ _Si vous utilisez VSCode, la commande `codium` doit être remplacée par `code`_
	- soit en ouvrant VSCodium, et **en glissant le dossier** du TP (_celui dans lequel vous avez cloné_) depuis l'explorateur de fichier/finder directement sur la fenêtre de VSCodium
	- soit en **ouvrant le dossier du projet** avec le raccourci <kbd>CTRL</kbd>+<kbd>O</kbd> ou via le menu `File` > `Open Folder` (_Win_) / `Open` (_Mac_) de VSCodium

2. **Une fois le projet ouvert, profitez-en pour tester quelques raccourcis clavier :**
	- <kbd>CTRL</kbd>+<kbd>P</kbd> : Permet d'ouvrir un fichier à partir de son nom
	- <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> : Permet de lancer n'importe quelle commande de n'importe quel menu
	- <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>:</kbd> : commente/décommente une ligne de code

	- cheat sheet windows : https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf
	- cheat sheet mac : https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf
	- cheat sheet linux : https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf

## Étape suivante <!-- omit in toc -->
Si tout fonctionne, vous pouvez passer à l'étape suivante : [B. Intégration du JS](B-integration.md)