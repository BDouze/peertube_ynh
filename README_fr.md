# PeerTube pour YunoHost

[![Niveau d'intégration](https://dash.yunohost.org/integration/peertube.svg)](https://dash.yunohost.org/appci/app/peertube) ![](https://ci-apps.yunohost.org/ci/badges/peertube.status.svg) ![](https://ci-apps.yunohost.org/ci/badges/peertube.maintain.svg)  
[![Installer PeerTube avec YunoHost](https://install-app.yunohost.org/install-with-yunohost.svg)](https://install-app.yunohost.org/?app=peertube)

*[Read this readme in english.](./README.md)*
*[Lire ce readme en français.](./README_fr.md)*

> *Ce package vous permet d'installer PeerTube rapidement et simplement sur un serveur YunoHost.
Si vous n'avez pas YunoHost, regardez [ici](https://yunohost.org/#/install) pour savoir comment l'installer et en profiter.*

## Vue d'ensemble

Plateforme de diffusion vidéo par P2P directement dans le navigateur, et connectée à un réseau fédéralisé

**Version incluse :** 4.0.0~ynh1

**Démo :** http://peertube.cpy.re

## Captures d'écran

![](./doc/screenshots/screenshot1.png)

## Avertissements / informations importantes

## Vue d'ensemble

### Qu'est-ce que PeerTube ?
PeerTube est une plateforme de streaming vidéo fédérée (ActivityPub) utilisant P2P (BitTorrent) directement dans le navigateur Web, en utilisant <a href="https://github.com/feross/webtorrent"> WebTorrent </a>.

### Pourquoi PeerTube?

Nous ne pouvons pas créer d'alternatives de streaming vidéo FOSS à YouTube, Dailymotion, Vimeo... avec un logiciel centralisé. Une organisation seule ne peut pas avoir assez d'argent pour payer la bande passante et le stockage vidéo de son serveur.
Nous avons donc besoin d'un réseau décentralisé de serveurs « semant » des vidéos (comme [Hubzilla YunoHost](https://github.com/YunoHost-Apps/hubzilla_ynh), [Friendica YunoHost](https://github.com/YunoHost-Apps/friendica_ynh), [Mastodon YunoHost](https://github.com/YunoHost-Apps/mastodon_ynh)), [Diaspora](https://github.com/diaspora/diaspora) ([Diaspora YunoHost](https://github.com/YunoHost-Apps/diaspora_ynh)),[Funkwhale](https://funkwhale.audio) ([Funkwhale YunoHost](https://github.com/YunoHost-Apps/funkwhale_ynh)).
Mais ce n'est pas suffisant car une vidéo pourrait devenir célèbre et surcharger le serveur. C'est la raison pour laquelle nous devons utiliser un protocole P2P pour limiter la charge du serveur. Grâce à [WebTorrent](https://github.com/feross/webtorrent), nous pouvons faire du P2P (donc BitTorrent) dans le navigateur Web, dès aujourd'hui.

### Pourquoi est-ce cool ?

Les serveurs sont gérés indépendamment par différentes personnes et organisations. Ils peuvent appliquer des politiques de modération extrêmement différentes, afin que vous puissiez en trouver ou en créer une qui correspond parfaitement à vos goûts.

En regardant une vidéo, vous aidez l'hébergeur à la diffuser en devenant vous-même un diffuseur de la vidéo. Chaque instance n'a pas besoin de beaucoup d'argent pour diffuser les vidéos de ses utilisateurs.

## Points importants à lire avant l'installation

1. Nécessite un **domaine dédié** comme **peertube.domain.tld**.
1. Le nom d'utilisateur de l'administrateur est: **root**.
1. **Le mot de passe administrateur et la configuration LDAP** seront envoyés à l'adresse email indiquée au moment de l'installation.
1. L'URL ne peut pas être modifiée une fois sélectionnée. Choisissez judicieusement le domaine.
1. Vous avez besoin de plus de **1 Go** de RAM. Si vous ne l'avez pas, veuillez créer une **mémoire swap**.

 
        $ dd if=/dev/zero of=/swapfile bs=1024 count=1048576
        $ mkswap /swapfile
        $ swapon /swapfile
        $ echo "/swapfile swap swap defaults 0 0" >> /etc/fstab

1. Cette application est **multi-instance** (vous pouvez avoir plus d'une instance PeerTube en cours d'exécution sur un serveur YunoHost)
1. **Si vous êtes hébergé sur une machine virtuelle OVH ou rencontrez `gyp ERR! configure error`, veuillez passer à [ovh_fix](https://github.com/YunoHost-Apps/peertube_ynh/tree/ovh_fix)**

## Caractéristiques spécifiques YunoHost

#### Support multi-utilisateur

* L'authentification LDAP est prise en charge, les instructions de configuration sont envoyées à l'adresse email indiquée au moment de l'installation
* L'authentification HTTP n'est pas prise en charge

## Documentations et ressources

* Site officiel de l'app : https://joinpeertube.org/fr/
* Documentation officielle de l'admin : https://docs.joinpeertube.org/
* Dépôt de code officiel de l'app : https://github.com/Chocobozzz/PeerTube/
* Documentation YunoHost pour cette app : https://yunohost.org/app_peertube
* Signaler un bug : https://github.com/YunoHost-Apps/peertube_ynh/issues

## Informations pour les développeurs

Merci de faire vos pull request sur la [branche testing](https://github.com/YunoHost-Apps/peertube_ynh/tree/testing).

Pour essayer la branche testing, procédez comme suit.
```
sudo yunohost app install https://github.com/YunoHost-Apps/peertube_ynh/tree/testing --debug
ou
sudo yunohost app upgrade peertube -u https://github.com/YunoHost-Apps/peertube_ynh/tree/testing --debug
```

**Plus d'infos sur le packaging d'applications :** https://yunohost.org/packaging_apps