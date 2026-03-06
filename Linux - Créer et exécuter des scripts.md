## 1. Qu'est-ce qu'un script ?  
  
Un **script** est simplement un fichier texte contenant une suite de commandes (bash) que le terminal peut exécuter automatiquement.  
  
Au lieu de taper plusieurs commandes manuellement, on les écrit dans un fichier et on les exécute d'un seul coup.  
  
Exemple de situation utile :  
  
- automatiser une compilation  
- lancer plusieurs programmes  
- sauvegarder des fichiers  
- configurer un environnement  
  
Dans Linux, les scripts sont souvent écrits en **bash**.  
  
---  
  
## 2. Créer un script  
  
On commence par créer un fichier.  
  
Convention courante : utiliser l’extension `.sh`.  
  
```
touch mon_script.sh
nano mon_script.sh
```
## 3. Le shebang (ligne obligatoire)

La première ligne d'un script indique **quel interpréteur doit exécuter le script**.

```
 <--On appelle cela le **shebang**.-->

`#!/bin/bash`

<--ou plus portable :-->

`#!/usr/bin/env bash`

<--Exemple de script minimal :-->

`#!/usr/bin/env bash`  
  
`echo "Bonjour"`

```

## 4. Rendre le script exécutable

Par défaut, un fichier n'est **pas exécutable**.

Il faut modifier ses permissions.


```
chmod +x mon_script.sh
```


## 5. Exemple concret 

```
nano compileRestartDwm.`sh` //creation du script
#!/usr/bin/env bash // shebang
cd ~/dotfiles/suckless/dwm // on ce deplace vers un dossier
sudo make clean install // on compile un code (ici c'est un code C)
sleep 3 // on attend 3 seconde avec la commande sleep
pkill dwm // 'process kill' DWM (dynamic windows manager)

```

```
chmod +x compileRestartDwm.sh
```

