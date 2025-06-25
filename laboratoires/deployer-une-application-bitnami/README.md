# Déployer une application Bitnami

## Intentions pédagogiques

Dans ce laboratoire, il s'agit de  déployer en local une première application livrée par Bitnami.

Il s'agira aussi de configurer correctement le réseau afin de pouvoir accéder aussi bien à la console web de l'application, qu'à la console d'administration du système d'exploitation virtualisé en ssh.

Etudier la "stack" LAMP de votre application.

## Objectifs opérationnels

* [ ] Déployer une application web préconfigurée de type LAMP sur un hyperviseur local.
* [ ] Configurer un réseau virtuel afin de permettre:
  * [ ] &#x20;un accès en http à la console web de l'application hébergée
  * [ ] un accès en ssh au système d'exploitation virtualisé
* [ ] Prendre en main la documentation technique de Bitnami
* [ ] Tester les opérations de bases pour manipuler les services de votre application.

## Bibliographie

{% embed url="https://aws.amazon.com/what-is/lamp-stack/" %}

## Déployer une application Bitnami

* Via le site de Bitnami, identifier l'application Drupal.

{% embed url="https://bitnami.com/stacks" %}

{% hint style="info" %}
Pour récupérer plus simplement le fichier ova depuis le CPNV, une copie a été livrée sur le commun de la classe.\
\
//TODO\
\
Pour récupérer plus simplement le fichier ova depuis votre domicile, une copie a été livrée ici:

[https://eduvaud-my.sharepoint.com/:u:/r/personal/pw53rcl\_eduvaud\_ch/Documents/CPNV\_CFC/I431/bitnami-drupal-11.0.5-r3-debian-12-amd64.ova?csf=1\&web=1\&e=ligy9Q](https://eduvaud-my.sharepoint.com/:u:/r/personal/pw53rcl_eduvaud_ch/Documents/CPNV_CFC/I431/bitnami-drupal-11.0.5-r3-debian-12-amd64.ova?csf=1\&web=1\&e=ligy9Q)
{% endhint %}

## Critères de validation

Pour vous aider à atteindre ces critères, vous trouverez la plus grande partie des informations techinques dans la documentation officielles Bitnami livrée avec l'image Drupal.

{% embed url="https://docs.bitnami.com/general/apps/drupal/" %}

* [ ] Votre machine virtuelle Bitnami a pu être déployé et on peut exploiter la console via l'interface de VMWare Workstation.
  * [ ] Le nom de la machine doit être : CPNV-CFC-I431-DRUPAL
* [ ] Les VmWare tools doivent être installés.
* [ ] Accès via un client ssh.
  * [ ] Vous pouvez soit utiliser le setup initial pour ajouter une clé, soit le faire dans un second temps-
* [ ] Accès web à la console d'administration de Drupal.
* [ ] Mise à jour du système d'exploitation.
* [ ] Réalisation d'un premier "snaphost".
* [ ] Commandes de bases pour gérer (start/restart/stop) les services de la Stack LAMP
  * [ ] le service Apache.
  * [ ] le service MySql.
* [ ] Identifier versions installées dans Stack Lamp livrée par Bitnami ?
  * [ ] Version d'Apache.
  * [ ] Version de Php.
  * [ ] Version de MySql.
  * [ ] Version de Debian.
* [ ] Ouvrir un accès SSH pour un de vos collègues.
* [ ] Ouvrir l'accès web pour toute la classe.

## Questions à étudier

* [ ] Quelle est l'architecture de la machine virtuelle et correspond-t-elle aux minimums requis pour Drupal ?
* [ ] A quoi servent les vmWare Tools ?
* [ ] Qu'est-ce que sudo ?
* [ ] Est une bonne idée de connecter notre machine virtuel de manière "bridge" avec notre hyperviseur ?
* [ ] Et si on déployait cette image (ova) directement en production. Est-ce une bonne idée ?

## Livrable

Voici le document à compléter pour valider ce laboratoire.

{% file src="../../.gitbook/assets/DeployBitnamiAppOnVmWareWorkstation.md" %}

