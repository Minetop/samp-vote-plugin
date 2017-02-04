# Plugin de vote pour serveur SA:MP

Ce plugin est une création de Top-Serveurs : https://top-serveurs.net. Il permet de récompenser les joueurs de votre serveur lorsqu'ils votent sur notre site : https://gta.top-serveurs.net.



![Screen plugin de vote](https://top-serveurs.net/upload/57cb1c7e2686a-modal_vote_screen%20copie.png "Screen plugin de vote")

La récompense se fait via l'utilisation d'une simple callback dans votre GameMode/FilterScript : **OnPlayerVote(ip, playername, date)**

## Installation

Pour installer le plugin vous devez télécharger au préalable le plugin correspondant au système d'exploitation de votre serveur, soit :
- Plugin pour **Windows** : https://github.com/Minetop/samp-vote-plugin/raw/master/vote-plugin.dll
- Plugin pour **Linux** : https://github.com/Minetop/samp-vote-plugin/raw/master/vote-plugin.so

Placez ensuite le plugin dans le dossier "**plugins**" de votre serveur.

## Configuration

Pour fonctionner, le plugin utilise un port sur votre machine. Par défault, c'st le port 8192 qui est utilisé. Si vous souhaitez le changer, vous devez éditer le fichier "**config.cfg**" de votre serveur et y ajouter cette ligne :

```
vote_port XXXX 
```
XXXX est le port que vous souhaitez utiliser

## Utilisation

Quand votre plugin de vote est installé et configuré, vous pouvez l'utiliser ainsi dans votre script (GameMode ou FilterScript) :

```c++
public OnPlayerVote(ip, playername, date
{
    new string[64];
    format(string, sizeof string, "%s a voté pour le serveur !", playername);
    SendClientMessageToAll(0xFFFFFFAA, string);
}
```

Ceci est un simple exemple, si vous le souhaitez vous pouvez donc ainsi offrir des récompenses à vos joueurs grâce à cette callback !
