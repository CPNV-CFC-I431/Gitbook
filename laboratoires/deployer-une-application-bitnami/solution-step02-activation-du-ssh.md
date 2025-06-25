# Solution - Step02 - Activation du SSH

[Bitnami - Activate or deactivate the SSH Server](https://docs.bitnami.com/virtual-machine/faq/get-started/enable-ssh/)

La documentation officielle parle d'un fichier à supprimer qui ne semble pas être présent dans l'ova utilisé. Il s'agit donc de vérifier la présence de ce fichier.

Fichier à chercher : sshd\_sshd\_not\_to\_be\_run

```
ls -la /etc/ssh/
```

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption><p>Vérification de la présence du fichier à supprimer</p></figcaption></figure>

Vérifier l'état du service. Il doit aussi bien être "enabled" pour un démarrage automatique au lancement de la machine qu'actif.

```
sudo systemctl status ssh
```

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption><p>Vérification d'état du service ssh</p></figcaption></figure>

Vérifier que la clé publique de mon utilisateur bitnami est présente sur la machine virtuelle.

```
cat .ssh/authorized_keys
```

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption><p>Validation de la présence de la clé publique pour l'utilisateur bitnami</p></figcaption></figure>

Identifier l'adresse ip de notre serveur ssh

```
ip a
```

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption><p>Identification de l'adresse ip</p></figcaption></figure>



{% hint style="info" %}
A partir de cette étape, nous allons utiliser le client ssh de votre système d'exploitation de l'hôte (la vm était la "guest")
{% endhint %}

Tentative de connexion via ssh

```
ssh bitnami@<votreIp> -i <votreCléPrivée>
```

```
Warning: Identity file i431PrivateKey.pem not accessible: No such file or directory.
The authenticity of host '172.25.30.122 (172.25.30.122)' can't be established.
ED25519 key fingerprint is SHA256:5liG6ojs1aUv8U5jrNh5qUQNzXoXHqt6yuu6xf6WE0U.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
```

Valider que votre machine virtuelle a bien été intégrée dans les "known\_hosts"

```
cat "C:\Users\Glassey Nicolas\.ssh\known_hosts"
```

```
//Exemple de réponse
172.25.30.122 ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIH1LCuvFYKuWrUmZ7pS/9getfHdVq/YPPvgmqHCG+8hD
```

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption><p>Voici le résultat à obtenir. On voir que l'on a pu atteindre notre serveur ssh et s'authentifier grâce à la clé.</p></figcaption></figure>



{% hint style="info" %}
Pour vérifier le nombre de session actuellement actives sur votre serveur ssh, essayer la commande "who"
{% endhint %}

```
who
bitnami  tty1         2024-11-21 13:01    //session vmWare
bitnami  pts/0        2024-11-21 13:25 (172.25.16.1) //session distante
```

