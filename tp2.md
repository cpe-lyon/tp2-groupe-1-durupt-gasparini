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

```bash
#!/bin/bash
PASSWORD="TEST"
echo 'RENTRER LE MOT DE PASSE:'
read -s PSW
if [$PASSWORD = $PSW ] ;then
	echo "ok"
else
	echo "pas ok"
fi
```
**chmod u+x testpswd.sh** --> on peut exexuter ce script

<h2>Exexcice 3 - Expressions rationnelles  </h2>

```bash
#!/bin/bash
function is_number() { 
	re='^[+-]?[0-9]+([.][0-9]+)?$' 
if ! [[ $1 =~ $re ]] ; then 
	return 1 
else 
	return 0 
	fi 
}
is_number $1 
if [ $? = 0 ] ; then
	echo "nombre réel"
else
	echo "nombre non réel"
fi
```
<h2>Exexcice 4 - Contrôle d’utilisateur </h2>

```bash
#!/bin/bash

Verif_utilisateur(){
	Name_user=$1
	if [[ $Name-user == ""]];then
		echo 'Utilisation: '"$0 $USER"
	fi
	Resultat=$(grep "$Name_user" /etc/passwd)
	return $?
}
Verif_utilisateur $1
if [[ $? -eq 0 ]];then
	echo "utilisateur existant"
else
	echo "Utilisateur non existant"
fi
```
 <h2>Exexcice 5 - Factorielle</h2>
 
```bash
#!/bin/sh 
 
fact() { 
        INDICE=$1 
        if [ $INDICE -eq 0 ] 
        then 
                echo 1 
        else 
                echo $(( INDICE * `fact $(( INDICE - 1 ))` )) 
        fi 
} 
 
echo `fact $1`
```
<h2>Exexcice 6 - Le juste Prix</h2>
```bash
#!/bin/sh 
 
Prix() { 
	VAL=$RANDOM%1000
        REPONSE=$1 
        if [ $REPONSE -lt $VAL ] 
        then 
		echo "C'est plus!"
                echo 1 
        else 
            	if [ $REPONSE -gt $VAL ] 
		then 
			echo "C'est moins!"
			echo 1 
		else
			echo "Gagné!"
			echo 0
	    	fi
        fi 
} 
read -p 'Votre Prix' val
Prix $val
while [ $? -eq 1 ]
do
	read -p 'Votre Prix' val
	Prix $val
done
```




