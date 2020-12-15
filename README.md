# talkToSalesforce
Salesforce &lt;> MuleSoft &lt;> Slack

# Description
Flow MuleSoft permettant de communiquer avec Salesforce pour lister les groupes publics Salesforce et mettre a jour les utilisateurs associés a ces groupes.

![talkToSalesforce3](https://user-images.githubusercontent.com/16212644/102120559-0276c080-3e43-11eb-9a80-5bac7bc78353.gif)



# Environnement
Le projet nécessite un compte Slack et MuleSoft pour importer et déployer le Flow. 

<img width="599" alt="Capture" src="https://user-images.githubusercontent.com/16212644/102120451-dbb88a00-3e42-11eb-96de-3d1f6d2aa911.PNG">

# Installation
Importer dans anypoint Studio.

Mettre a jour le fichier de configuration avec vos identifiant Salesforce talkToSalesforce/src/main/resources/config.yaml 

A ce stade, vous êtes capable de lancer le projet depuis Anypoint studio.
Cette requête vous permet récupérer la liste des groupe dans votre environnement Salesforce

curl - location - request POST 'http://localhost:8081/group' \
 - header 'Content-Type: application/json' \
 - data-raw '{
 "text": "list"
}'

Déployer le flow sur Cloud hub et recuperer l'URL généré pour votre Flow. 


Creer une application Slack.Dans votre application Slack, activez les commandes Slack et creez une commande /group, ajoutez le point de terminaison de votre Flow MuleSoft suivi /group.
Activez votre application pour votre workspace :)

# commandes Slack

/group : liste des commandes.

/group list : liste des groupes dans Salesforce.

/group list [GROUP NAME] : liste des utilisateurs dans le groupe.

/group add [GROUP NAME] [Username] : ajoute l'utilisateur au groupe.

/group remove [GROUP NAME] [Username] : supprime l'utilisateur du groupe.
