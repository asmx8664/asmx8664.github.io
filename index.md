L'assembleur est un langage de programmation qui permet de discuter directement avec le processeur. Lorsque vous utilisez un langage de haut niveau comme du **C** ou de très haut niveau comme du **Python**, vous codez à travers une couche d'abstraction plus ou moins épaisse. Ainsi, dans le cas des langages compilés, c'est le compilateur qui _traduit_ vos lignes de code compréhensibles par vous en langage machine compréhensible par le processeur.

# Objectifs de la formation

La formation est axée à 90% sur Windows. En effet, la plupart des entreprises ayant un **Active Directory** et des _workstations_ fonctionnant sur Windows, il est fort à parier que lors d'une compromission, un **PE** ou une **DLL** soit en cause.

Les objectifs de la formation sont ci-dessous:

* Mise en place d'un environnement de développement pour de l'asm x86-64
* Méthode développement de **PE** / **DLL** / _shellcode_ en asm x64
* Utiliser un _debugger_
* Analyse de _shellcode_ existant
* Modification de _shellcode_ existant pour contourner **Defender** (antivirus natif de Windows)

```
Il est à noter qu'aucun code malveillant ne sera codé dans cette formation. 
```

Les _payloads_ utilisées (par exemple dans le cadre du développement d'un _loader_ de _shellcode_), seront une suite de **NOP** (instruction qui incrémente le registre **rip**). En ce qui concerne les _shellcodes_ à analyser/modifier, ceux générés par l'outil **msfvenom** seront utilisés. 

A la suite de cette formation, il sera notamment possible de:

* Coder son propre loader de _shellcode_
* Coder son propre _shellcode_
* Modifier les _shellcodes_ générés par **msfvenom** pour contourner **Defender**
* Debugger un programme

```
Comme il ne s'agit pas d'une formation au format vidéo pré-enregistré, il est recommandé de poser un maximum de questions.
```

# Pour qui? 

Cette formation est dédiée à la cybersécurité. La compréhension de l'assembleur x64 sera donc orientée en ce sens. Toutes les subtilités liées à ce langage ne seront donc pas vues. 

Grosso modo, deux grandes familles sont retrouvées dans le monde de la cybersécurité:

* l'attaque (_red team_)
* la défense (_blue team_)

Que vous apparteniez à l'une ou à l'autre, cette formation est faite pour vous. Que vous soyez du côté **exécutif** ou **managérial** également. Aucune notion d'assembleur n'est requise pour suivre cette formation qui est principalement dédiée aux **débutants**.

Pour ceux qui appartiennent au côté défensif, il est intéressant de connaître l'assembleur car l'analyse de code malveillant est en grande partie effectuée dans ce langage. En effet, lorsqu'une machine se fait compromettre, les binaires malveillants en sont extraits (soit directement, soit par capture de **RAM**) puis analysés. Le code source n'étant pas disponible, il est alors nécessaire de le désassembler afin d'en comprendre les fonctionnalités et d'en tirer des indices de compromissions.

Concernant ceux qui sont du côté offensif, la modification de shellcodes existants ou la création de shellcodes optimisés pour une attaque en particulier est un avantage décisif. Effectivement, il n'est pas recommandé d'utiliser n'importe quel shellcode trouvé sur le net. D'autant que la plupart de ceux disponibles ont déjà été catégorisés comme malveillant par les solution d'antivirus.

Pour résumer, cette formation s'adresse à tous ceux curieux d'apprendre à utiliser l'assembleur pour analyser les attaques modernes, mais aussi pour contourner les signatures mises en place dans les antivirus.

# Modalités

Cette formation est proposée en cours du soir comme suit:

* 2h par soir pendant 5 soirs (10h)
* Idéalement 20h-22h

Le tarif est fixé à:

* ?€/h soit ?€ pour l'ensemble de la formation

Il s'agit d'une formation en groupe restreint:

* 10-12 personnes maximum

La formation se fait en visio (**Teams/Discord**).

```
Le CPF n'est pas pris en charge.
```

```
Aucun certificat d'accomplissement ne sera délivré.
```

# Contact

...

# Prérequis

```
Merci de vérifier les prérequis suivants avant de souscrire à la formation.
```

Afin de pouvoir suivre la formation, il est nécessaire d'avoir un environnement adéquate:

* un processeur intel ou amd
* un OS Windows **ET** un OS Linux (kali)
* 8-16 Go de RAM

## Installation des OS

L'idéal est d'avoir une machine virtuelle Windows et une machine virtuelle Linux. Cependant, si la **RAM** n'est pas suffisante pour faire tourner 2 _VMs_, il est possible d'utiliser l'hôte, soit pour Windows, soit pour Linux.

### Linux

Il est recommandé d'utiliser la distribution [Kali](https://www.kali.org/). 

Cette machine servira essentiellement à la génération de _shellcodes_ qui seront ensuite utilisés sur la machine Windows. Si une autre distribution est envisagée, il faut s'assurer que le [framework Metasploit](https://github.com/rapid7/metasploit-framework) est bien installé et fonctionnel. Pour le tester, essayer la commande suivante dans un terminal:

```
msfvenom -p windows/x64/messagebox -a x64 --platform windows -f hex
```

### Windows

Il est recommandé d'utiliser une version de développement fournie par [Microsoft](https://developer.microsoft.com/fr-fr/windows/downloads/virtual-machines/). En effet, l'ensemble des outils de compilation sont déjà pré-installés. **Attention**, la _VM_ est plutôt lourde ...

Plutôt que d'installer la _VM_ de développement fournie par Microsoft, il est possible d'installer une **ISO** classique puis d'installer les outils à la main. Pour cela:

* Télécharger [Visual Studio Installer (Community)](https://visualstudio.microsoft.com/fr/downloads/)
* Et choisir la suite de **Développment Desktop en C++**. Consulter la figure ci-dessous pour choisir les composants à installer

![C++ components](/img/index/cpp_components.png)

Afin de débugger du code, il est nécessaire d'installer un debugger:

* **WinDbg Preview** depuis le Microsoft Store
* **x64dbg** depuis ce [lien](https://x64dbg.com/)

Il peut être utile d'installer un désassembleur comme [IDA Free](https://hex-rays.com/ida-free/)

Installer ensuite [Visual Studio Code](https://code.visualstudio.com/download) comme éditeur de code. Une fois installé, ajouter le _plugin_ **ASM Code Lens** (coloration syntaxique) comme sur la figure ci-dessous:

![asm code lens](/img/index/asm_code_lens.png)

Un éditeur hexadécimal est également requis, utiliser [HxD](https://www.lesnumeriques.com/telecharger/hxd-hex-editor-20536) par exemple.

Et enfin, télécharger et installer l'outil [CFF Explorer](https://ntcore.com/?page_id=388) afin de constater la structure de vos création :)

