# Q1.1.1
Aller Dans le server manager, dans le menu déroulant "Tools" séléctionner "Active directory Users and Computers.
<img width="721" alt="Capture d’écran 2024-09-06 à 09 18 01" src="https://github.com/user-attachments/assets/1050849e-3e5e-4d2e-9f98-409f9be6150a">

Dans l'O.U Direction des ressources humaines, faire un copy de Kelly Rhameur en Lionel.lemarchand, puisque KElly a les memes attributs.

<img width="288" alt="Capture d’écran 2024-09-06 à 09 28 03" src="https://github.com/user-attachments/assets/8b5261a3-e48f-4545-b275-6eaa7c188cfb">



Pour cet exercice et éviter tout problèmes, nous définissons que le mot de passe n'expire pas:

<img width="288" alt="Capture d’écran 2024-09-06 à 09 28 37" src="https://github.com/user-attachments/assets/1162d61b-a38e-44a5-a337-29f005c8de21">

Enfin, valider le tableau récapitulatif:

<img width="290" alt="Capture d’écran 2024-09-06 à 09 28 47" src="https://github.com/user-attachments/assets/366f9cd6-2e44-451d-97f8-6fbccad22e17">

<img width="636" alt="Capture d’écran 2024-09-06 à 09 28 58" src="https://github.com/user-attachments/assets/de949b70-d196-4151-afc0-65da829281a2">


# Q1.1.2

Faire un clic droit sur le TSSR.LAN, puis "New" "Organizational unit".

<img width="456" alt="Capture d’écran 2024-09-06 à 09 31 55" src="https://github.com/user-attachments/assets/c574f4ff-0fff-4277-9466-12a303dce8c2">

Définir le nom de l'OU:

<img width="288" alt="Capture d’écran 2024-09-06 à 09 32 24" src="https://github.com/user-attachments/assets/3b5c2bf7-5079-4bdc-af05-48d92be8b3f9">

Faire clic droit, "move..." sur l'utilisateur Kelly Rhameur, et séléctionner l'ou Deactivated users:


<img width="213" alt="Capture d’écran 2024-09-06 à 09 32 48" src="https://github.com/user-attachments/assets/760e1902-f35f-4ec8-b3b9-472bb1d7b58a">


<img width="613" alt="Capture d’écran 2024-09-06 à 09 32 58" src="https://github.com/user-attachments/assets/097c502f-dafc-489c-99fe-d6d1edbeb50b">

# Q1.1.3

Ayant fait un "Move...", Kelly Rhameur n'est plus dans son ou d'origine:

<img width="641" alt="Capture d’écran 2024-09-06 à 09 35 29" src="https://github.com/user-attachments/assets/95b03d53-b4d1-4bba-bbdb-48a9f2c53cff">

# Q1.1.4

Aller dans l'explorateur de fichier sur le volume "F:" appelé "DossiersIndividuels. Faire un clique-droit "New", "Folder":

<img width="762" alt="Capture d’écran 2024-09-06 à 09 41 19" src="https://github.com/user-attachments/assets/17cdc4e4-3b0f-4050-af6a-7e338acbb55f">

Nommer le fichier "Lionel LEmarchand" et ajouter le suffixe "-ARCHIVE" à celui de Kelly Rhameur:

<img width="740" alt="Capture d’écran 2024-09-06 à 09 43 23" src="https://github.com/user-attachments/assets/cfdaf220-d500-4e7e-b815-23994f8f789e">

# Q1.2.1

Toujours dans "Active Directory Users and Computers", aller dans l'O.U "DirectionFinancière"/"Finance":

<img width="767" alt="Capture d’écran 2024-09-06 à 09 49 48" src="https://github.com/user-attachments/assets/6bc747ae-f7f5-4f0a-81f1-a0a4bc1c7d06">

Faire un clique droit "Properties" "Account":

<img width="273" alt="Capture d’écran 2024-09-06 à 09 50 12" src="https://github.com/user-attachments/assets/c8e8dbeb-64ac-47ba-8a65-a5e60cc7d21c">


Dans l'onglet account, cliquer sur "Log on hours" et sélectionner la plage horaire de 7h à 17h:

<img width="334" alt="Capture d’écran 2024-09-06 à 09 51 25" src="https://github.com/user-attachments/assets/6499a22f-1116-45cf-90d2-70aadc3c47fc">


# Q1.2.2

Dans la même fenêtre "account" de "properties", aller dans "log on to".
Cocher "the following computers" et dans "add" écrire "client01":

<img width="305" alt="Capture d’écran 2024-09-06 à 09 55 41" src="https://github.com/user-attachments/assets/55042b5a-14ad-4d0b-b427-0dfdbaece2bb">

# Q1.2.3

Dans le Server Manager, aller dans "tools" et "Active Directory Administrative Center".
Puis naviguer dans "TSSR> SYSTEM> PASSWORD SETTINGS CONTAINER".
Ici, faire un clique droit "new", "Password settings":

<img width="949" alt="Capture d’écran 2024-09-06 à 10 02 56" src="https://github.com/user-attachments/assets/5b3d0718-c9e8-46fb-86ba-2dcb9363cea9">

Je le nomme "passwordPolicy1"
Precedence "1", pour qu'il soit prioritaire.
Une longueur minimum de 10 caractères pour renforcer le mot de passe.
Une mémoire de 5 mots de passes pour éviter qu'ils soient réutilisés.
Une durée de vie des mots de passes comprises entre 1 et 90 jours pour les renouveler régulièrement.
Et enfin, 5 essais toutes les 30 minutes.

<img width="586" alt="Capture d’écran 2024-09-06 à 10 07 47" src="https://github.com/user-attachments/assets/2738bfda-efb5-47dd-90c9-8372f2fb5a09">


# Q1.3.1

Dans le "Server Manager", "Tools" sélectionner "Group Policy Managment"
Sur "TSSR.LAN" faire un clic droit, "Create GPO in this domain and link it". Et la nommer "Drive§Mount":

<img width="685" alt="Capture d’écran 2024-09-06 à 10 17 09" src="https://github.com/user-attachments/assets/05d26102-ae73-4e37-9be1-e5d00949e11d">

<img width="258" alt="Capture d’écran 2024-09-06 à 10 17 37" src="https://github.com/user-attachments/assets/328230d0-fae0-4d3d-9006-be3d45aba182">

 Sur la GPO, faire un clic droit "Edit", et naviguer dans le menu "User Configuration > Preferences > Windows Settings > Drive Maps"

<img width="525" alt="Capture d’écran 2024-09-06 à 10 25 43" src="https://github.com/user-attachments/assets/0172c982-4e3c-4462-a365-7b0c4745e7a5">

Faire un clic droit "New" et dans la fenetre de dialogue entrer comme suit pour "E:" et "F:":



<img width="268" alt="Capture d’écran 2024-09-06 à 10 29 07" src="https://github.com/user-attachments/assets/7a61aff7-b0bb-4d94-a4a8-2df277a015af">

On obtient donc le menu drive maps suivant:

<img width="520" alt="Capture d’écran 2024-09-06 à 10 29 55" src="https://github.com/user-attachments/assets/b6779d4b-b927-4622-8d9f-c029dd054e2a">


Pour finir, activer la gpo dans l'invite de commande avec la commande **gpupdate /force**

<img width="649" alt="Capture d’écran 2024-09-06 à 10 30 34" src="https://github.com/user-attachments/assets/de6fe869-08c2-4f6f-850f-fd8f7e70de6d">
