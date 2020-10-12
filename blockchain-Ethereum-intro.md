<p align="center">
<br>
<h3>Introduction à la Blockchain Etherum</h3>
<br>

</p>

<p align="center">
<br>
##Technologie de Registre Distribué (DLT)
<br>

</p>

Les technologies Blockchain résout 2 problèmes :
<br>
*Immutabilité : Les données ne peuvent être altérées
*Processus distribué : Il n’y a pas de point de défaillance unique dans le réseau. Tous les nœuds du réseau travaillant ensemble sont basés sur un méchanisme de concensus afin de se prémunir des acteurs malveillants.

###<p align="center">
<br>
Immutability
<br>

</p>

Dans une blockchain, toutes transactions sont stockées dans un block. Les autres block inclus un hash cryptographic sur le block précédent de la chaîne, liant ainsi 2 blocks entre eux et hashant également toutes les transactions stockées dans le block.
Le hash est généré par une fonction de hachage cryptographique.
Une fonction de hachage cryptographique est une fonction à sens unique (non reversible) qui mappe le contenu d’un block avec un numéro.
Avec ces 2 numéros, le hachage cryptographique du précédent block et le hachage cryptographique de toutes les transactions confirmées dans le block, sont stockées dans l’en-tête du block de block suivant.

<p align="center">
  <br>
  <img src="/img/imgblock1.jpeg">
</p>

<p align="center">
  <br>
Comment un tel processus peut être implémenté avec du code :
  <img src="/img/imgblock2.jpg">
</p>

<p align="center">
  <br>
Synoptique d’un en-tête de block :
  <img src="/img/imgblock3.png">
</p>

Ce processus garantit l’intégrité du block. Par exemple, pour changer une transaction en amont, il devra altérer le hash de toutes les transactions dans les block. Il devra donc reminer le block à falsifier mais il faudra aussi altérer les hash de tous les blocks précédents et suivants stockés dans les en-têtes. Un acteur malveillant devra donc miner tous les blocks qui suivent et qui doivent être basés sur le block falsifié.
L’autre protection avec laquelle on prévient ce genre de modification repose sur un mécanisme de consensus. Les attaquants auraient besoin de contrôler 51 % du réseau pour modifier des transactions qui se trouveraient déjà dans la blockchain. Cette attaque est appelée l’attaque des 51 %. Cette attaque est actuellement impossible à mener. En effet, des attaquants auraient besoin d’une énorme puissance de calcul. Même si ils y parviendraient, les utilisateurs quitteraient une blockchain falsifiée.

###<p align="center">
<br>
Synoptique d’nfrastructure Centralisée vs Décentralisée vs Distribuée

</p>

<p align="center">
  <br>
  <img src="/img/imgblock4.png">
</p>

Dans un réseau distribué, il n’y a pas de nœud central. L’objectif est d’éviter d’avoir un point de défaillance unique. Les mécanismes de consensus sont utilisés pour rendre les nœuds du réseau qui travaillent ensemble plus sûrs et éviter de devenir un système frauduleux.
Dans le cas d’un réseau blockchain, les mécanismes de concensus sont utilisés pour contrôler comment une transaction blockchain peut être validée, écrite dans le block et être fonctionnelle.

###<p align="center">
<br>
Les mécanismes de consensus

</p>

####<p align="center">
<br>
Problèmes des généraux byzantins

</p>

https://fr.wikipedia.org/wiki/Probl%C3%A8me_des_g%C3%A9n%C3%A9raux_byzantins

####<p align="center">
<br>
Preuve de travail (Proof of Work : POW)

</p>

Il s’agit du concensus de l’algorithme originale.
Avec la preuve de travail, les mineurs se concurrencent afin de valider les transactions sur le réseau et d’ajouter de nouveaux blocks dans la blockchain.
Les mineurs doivent résoudre un puzzle mathématique en utilisant la puissance de calcul de leur processeur.
Le puzzle mathématique à résoudre consiste à trouver un nombre haché de l’en-tête d’un bloc en manipulant le champ du nonce dans ce block.
Le nombre haché à trouver doit être inférieur au hash visé. La hash ciblé est défini par la difficulté.

<p align="center">
  <br>
  <img src="/img/imgblock5.jpg">
</p>

Le premier mineur à résoudre le puzzle obtient une récompense pour son travail.
Une preuve de travail est une partie des données avec laquelle (coût et temps) il est difficile de produire mais facile pour les autres de vérifier moyennant certaines exigences.

####<p align="center">
<br>
Preuve de participation (Proof of stake : PoS)

</p>

Il s’agit d’un type de concensus d’algorithm avec lequel un réseau blockchain de cryptomonnaie devient un concensus distribué.
Dans la preuve de participation basée sur des blockchains, le créateur du prochain block est choisi par des combinaisons aléatoires variables. Dans le cas de la blockchain Ethereum, il faut avoir un minimum de 32 ETH pour participer au « staking » et pour valider il est nécessaire de faire tourner un nœud de validateur. Il n’est pas nécessaire d’avoir une machine spéciale et cela peut-être fait sur un ordinateur grand public ou même un portable. Cependant, les validateurs doivent être constamment en ligne sous peine de recevoir des sanctions mineurs.
Dans le cas où une blockchain exécute un consensus de preuve de participation, les mineurs/validators/stakers peuvent miner ou valider des block de transactions en fonction des cryptomonnaies qu’ils détiennent.
Pour ajouter un block malveillant, un attaquant devra détenir 51 % de toute la cryptomonnaie du réseau.

<br>

Ethereum fonctionne historiquement sur la preuve de travail. Cependant, la preuve de participation est généralement considéré être moins énergivore que la preuve de travail.

###<p align="center">
<br>
Minage

</p>

Les nœuds de minage créés des blocks dans la chain.
Un block est une structure de donnée qui contient un ensemble de transactions. Quand un block est créé, le mineur sélectionne quelques transactions de son pool de transactions en attente d’être intégrées dans la chain et commence le minage du block.
La chose importante à savoir est que le minage est un processus qui coûte cher. Si un mineur n’obtient aucune récompense en retourn plus personne ne voudra miner. Dans Ethereum, quand un mineur mine un nouveau block, il reçoit un « salaire » et un blovk de récompense pour toutes les transactions qu’il intégre dans ce block (actuellement 2 ETH). Plus haut est le gasPrice dans les transactions, plus haut est la récompense que le mineur reçoit.

###<p align="center">
<br>
Fees/Gas

</p>

Le salaire dans la blockchain Bitcoin ou le système de gas dans la blockchain Ethereum, sont des sytèmes de protections et de récompenses pour les nœuds qui procèdent aux transactions.

L’informatique a un coût :
<br>
*héberger un service
*stocker les données
\*traitement des informations

Toute transaction qui modifie un état dans une blockchain, comme envoyer des cryptomonnaies, déployer un smart cioontract ou échanger une valeur dans un smart contract coûtera des frais d’expéditions pour l’expéditeur.

<br>

Un autre aspect de la facturation de l’utilisateur pour ses actions sur le réseau est de prévenir les abus. Si vous payer pour toute opération que vous faîtes, vous ferez de votre mieux pour coder de la manière la plus efficace. Le coût des frais empêche les mauvais acteurs d’innonder le système d’opérations inutiles (à moins qu’ils soient prêts à dépenser beaucoup d’argent pour exécuter du code inutile.
