# Solution - Step01 - Personnalisation de Debian

## STEP02 - Personnaliser la machine virtuelle

### Mettre à jour les dépôts de Debian et valider l'accès au réseau

```
sudo apt update
```

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

### Configurer le bon layout du clavier

[Bitnami - Modify the keyboard layout](https://docs.bitnami.com/virtual-machine/faq/configuration/configure-keyboard/)

Choisir "other" puis "German - Switzerland" puis "German (Switzerland) - French (Switzerland)\


<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption><p>Sélection du bon "layout" pour la Romandie</p></figcaption></figure>

{% hint style="info" %}
Réaliser un snapshot "à froid". \
\
Le nom sera "CPNV-CFC-I431-DRUPAL-STEP01-DEBIAN-CUSTOMIZATION"
{% endhint %}

