<h1>TP 2 -  Bash
<h2>Exexcice 1 - Variables d'environnement  </h2>

1. Les commandes tapées par l’utilisateur sont dans la variable **PATH** 
2. La variable **HOME** contient le chemin vers le répertoire personnel. Donc la commande **cd $HOME** permet de revenir à notre répertoire personnel.
3. Rôle des variables:
-   La variable d'environnement **LANG** contient le paramètre linguistique de base utilisé par les applications du système pour communiquer avec l'utilisateur ex: fr_FR.UTF-8.
- La variable d'environnement **PWD** contient le chemin du répertoire de travail courant de l'interpréteur de commande.
4.  MY_VAR="admin Syst";
5. bash --> changer de session , elle n'existe pas
6. export MY_VAR="admin Syst";  --> la variable existe
7. On crée la variable d'environnement avec la commande **export NOMS="GASPARINI DURUPT"**. Pour vérifier son contenue on fait la commande **printenv NOMS**.
8. On écrit la commande **echo** Bonjour à vous deux **$NOMS !** afin d'afficher le message souhaité.
9. La commande **unset** sert à supprimer une variable. La variable n'existe plus, contrairement à une variable vide qui, elle, existe. **printenv** ne renvoie rien.
10.
 ```bash 
echo '$HOME ='"$HOME"

```
<h2>Exexcice 2 - Contrôle de mot de passe  </h2>

 
