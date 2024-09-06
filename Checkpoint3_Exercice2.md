# Q2.1.1

Une fois connecté en root, Faire un **userdadd brice** pour créer le nouvel utilisateur et suivre les instructions:

<img width="691" alt="Capture d’écran 2024-09-06 à 10 45 40" src="https://github.com/user-attachments/assets/87fb3192-09b1-4cbc-9e6c-f124a902c3de">

# Q2.1.2

Je préconise que l'utilisateur personnel n'aie pas de droits sudo puisqu'il n'est pas administrateur.


# Q2.2.1

Editer le fichier de configuration SSH:

<img width="421" alt="Capture d’écran 2024-09-06 à 10 50 04" src="https://github.com/user-attachments/assets/2b0d7e67-498f-4440-add6-76fe0698a982">

Puis chercher la ligne **PermitRootLogin**, la décommenter et ajouter "No":

<img width="680" alt="Capture d’écran 2024-09-06 à 10 51 25" src="https://github.com/user-attachments/assets/9402543e-b9dd-4d5e-9e55-089337b00dfc">

Enregistrer le fichier et redémarrer SSH:

<img width="385" alt="Capture d’écran 2024-09-06 à 10 51 50" src="https://github.com/user-attachments/assets/80d03f0e-ea91-41be-97db-221913a560fc">


# Q2.2.2

Toujours dans le même fichier de configuration, ajouter la ligne **AllowUsers brice**

<img width="192" alt="Capture d’écran 2024-09-06 à 10 54 53" src="https://github.com/user-attachments/assets/f9aa9429-d8cb-4ab2-945e-a1c401e43b80">

Enregistrer et redémarrer SSH:

<img width="385" alt="Capture d’écran 2024-09-06 à 10 51 50" src="https://github.com/user-attachments/assets/fe50ddc1-ba9a-4571-984c-3c4b705f2ad7">

# Q2.2.3

Faire un **ssh§keygen**

<img width="629" alt="Capture d’écran 2024-09-06 à 10 57 54" src="https://github.com/user-attachments/assets/3a7bead7-fca0-4de7-a106-0d3fb668d4f6">

Puis copier la clé publique sur lme serveur debian **ssh-copy-id brice@192.168.1.200**:

<img width="997" alt="Capture d’écran 2024-09-06 à 11 00 07" src="https://github.com/user-attachments/assets/4bc7f404-afa9-4f07-b065-bb8ea2677ade">


Dans le fichier de configuration, le modifier pour obtenir les 2 lignes suivantes permettant l'authentification par clés:

<img width="654" alt="Capture d’écran 2024-09-06 à 11 00 52" src="https://github.com/user-attachments/assets/d05377d8-d9a5-4783-9fb0-a9db61aa7929">

<img width="277" alt="Capture d’écran 2024-09-06 à 11 01 16" src="https://github.com/user-attachments/assets/226260b6-004c-496e-9e24-c07af6f9408d">

sauvegarder le fichier et redémarrer ssh:

<img width="385" alt="Capture d’écran 2024-09-06 à 10 51 50" src="https://github.com/user-attachments/assets/8551def2-c688-4a8b-9036-8984873fbbf6">

# Q2.3.1

Taper la commande **df -h**

<img width="672" alt="Capture d’écran 2024-09-06 à 11 07 49" src="https://github.com/user-attachments/assets/c9ab6732-725b-4fda-a731-b98987111a57">

Nous avons des systèmes: **tmpfs**

# Q2.3.2

il faut taper les commandes **lsblk** et **mdadm --detail --scan**
Nous aurons au les supports en RAID de cette manières.

<img width="665" alt="Capture d’écran 2024-09-06 à 11 07 58" src="https://github.com/user-attachments/assets/718cca4e-316a-48cb-a3de-a8650980ca20">

<img width="839" alt="Capture d’écran 2024-09-06 à 11 08 28" src="https://github.com/user-attachments/assets/9886fb0b-00db-4000-bbfa-bc146c2289ed">

# Q2.3.3

Créer et ajouter le disque de 8GO dans virtualbox:

<img width="768" alt="Capture d’écran 2024-09-06 à 11 12 31" src="https://github.com/user-attachments/assets/65c23695-2453-4e92-bbfe-7e3c05887d3c">

<img width="870" alt="Capture d’écran 2024-09-06 à 11 12 47" src="https://github.com/user-attachments/assets/ecfbf5e8-8335-4945-a758-f40de338923d">

<img width="853" alt="Capture d’écran 2024-09-06 à 11 13 03" src="https://github.com/user-attachments/assets/7dbf5e9c-01be-4e92-ae18-3d9421de3da9">

Faire un **reboot** du serveur debian pour faire apparaitre le disque.
Faire un **lsblk** pour identifier le disque (ici "sdb"):

<img width="634" alt="Capture d’écran 2024-09-06 à 11 14 11" src="https://github.com/user-attachments/assets/f9b394a7-2e82-4b0b-a5f0-a3482e8c7c09">

Faire ** mdadm --add /dev/md0 /dev/sdb**
**mdadm --grow /dev/md0 --raid-devices=2**

<img width="512" alt="Capture d’écran 2024-09-06 à 11 16 08" src="https://github.com/user-attachments/assets/fa1e8477-2d6b-4f50-b420-eb6a999465bc">

<img width="571" alt="Capture d’écran 2024-09-06 à 11 16 17" src="https://github.com/user-attachments/assets/2f21b464-018f-4d23-8bdc-e70bad369b6e">

Enfin, verifier la manipulation avec la commande **mdadm --detail --scan**

<img width="673" alt="Capture d’écran 2024-09-06 à 11 17 37" src="https://github.com/user-attachments/assets/ddae6874-1cae-4fb7-9b47-db06bf1a98fc">


# Q2.4.1

Les 3 fichiers jouent un roles différent et complémentaires:

- Bareosdir: Il est le **directeur**, qui coordonne les différentes opérations et permet de planifier les sauvegardes.
- Bareos-sd: est le **Storage deamon**, il gère les supports de stockage où les données sont sauvegardées (lecture, écriture, récupération).
- Bareos§fd: il est le **File deamon**, il se trouve sur le client, et permet de communiquer les données au **bareos-sd**.

# Q2.5.1

Il faut taper la commande **nft list ruleset**:

<img width="636" alt="Capture d’écran 2024-09-06 à 11 52 44" src="https://github.com/user-attachments/assets/7955828b-aa66-4b8f-a0c2-1f58f4e294ba">



# Q2.5.2

Nous voyons que sont accepter les ping en ip4 (icmp accept) et ip6 (ipv6-icmp accept), ainsi que les communications ssh (tcp port 22 accept).
De même, tous les paquets provenants d'une connexion déjà établie sont acceptés (ct state established,related accept)


# Q2.5.3

Sont refusés, les paquets provenants de connexions non préétablis (ct state invalid drop)

