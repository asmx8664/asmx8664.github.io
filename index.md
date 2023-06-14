L'assembleur est un langage de programmation qui permet de discuter directement avec le processeur. Lorsque vous utilisez un langage de haut niveau comme du **C** ou de très haut niveau comme du **Python**, vous codez à travers une couche d'abstraction plus ou moins épaisse. Ainsi, dans le cas des langages compilés, c'est le compilateur qui __traduit__ vos lignes de code compréhensibles par vous en langage machine compréhensible par le processeur.

# Pour qui? 

Cette formation est dédiée à la cybersécurité. La compréhension de l'assembleur x64 sera donc orientée dans cette direction. Toutes les subtilités liées à ce langage ne seront donc pas vues. 

Grosso modo, deux grandes familles sont retrouvées dans le monde de la cybersécurité:

* l'attaque (red team)
* la défense (blue team)

Que vous apparteniez à l'une ou à l'autre, cette formation est faite pour vous. Que vous soyez du côté **exécutif** ou **managérial** également. Aucune notion d'assembleur n'est requise pour suivre cette formation qui est principalement dédiée aux **débutants**.

Pour ceux qui appartiennent au côté défensif, il est intéressant de connaître l'assembleur car l'analyse de code malveillant est en grande partie effectué dans ce langage. En effet, lorsqu'une machine se fait compromettre, les binaires malveillants en sont extraits (soit directement, soit par capture de RAM) puis analysés. Le code source n'étant pas disponible, il est alors nécessaire de le désassembler afin d'en comprendre les fonctionnalités et d'en tirer des indices de compromission.

Concernant ceux qui sont du côté offensif, la modification de shellcodes existants ou la création de shellcodes optimisés pour une attaque en particulier est un avantage décisif. Effectivement, il n'est pas recommandé d'utiliser n'importe quel shellcode trouvé sur le net. D'autant que la plupart de ceux disponibles ont déjà été catégorisés comme malveillant par les solution d'antivirus.

Pour résumer, cette formation s'adresse à tous ceux curieux d'apprendre à utiliser l'assembleur pour analyser les attaques modernes, mais aussi pour contourner les signatures mises en place dans les antivirus.

# Objectifs de la formation

La formation est axée à 90% sur Windows. En effet, la plupart des entreprises ayant un Active Directory et des workstations fonctionnant sur Windows, il est fort à parier que lors d'une compromission, un PE ou une DLL soit en cause.

Les objectifs de la formation sont ci-dessous:

* Mise en place d'un environnement de développement pour de l'asm x86-64
* Méthode développement de PE / DLL / shellcode en asm x64
* Utiliser un debugger
* Analyse de shellcode existant
* Modification de shellcode existant pour contourner **Defender** (antivirus natif de Windows)

```
Il est à noter qu'aucun code malveillant ne sera codé dans cette formation. 
```

Les payloads utilisées (par exemple dans le cadre du développement d'un loader de shellcode), seront une suite de **NOP** (instruction qui incrémente le registre **rip**). En ce qui concerne les shellcodes à analyser/modifier, ceux générés par l'outil **msfvenom** seront utilisés. 

A la suite de cette formation, il sera notamment possible de:

* Coder son propre loader de shellcode
* Coder son propre shellcode
* Modifier les shellcodes générés par **msfvenom** pour contourner **Defender**
* Debugger un programme

```
Comme il ne s'agit pas d'une formation au format vidéo pré-enregistré, il est recommandé de poser un maximum de questions.
```

# Modalités

Cette formation est proposée en cours du soir comme suit:

* 2h par soir pendant 5 soirs (10h)
* Idéalement 20h-22h

Le tarif est fixé à:

* ?€/h soit ?€ pour l'ensemble de la formation

Il s'agit d'une formation en groupe (petit):

* 10-12 personnes maximum

La formation se fait en visio (Teams/Discord).

```
Le CPF n'est pas pris en charge.
```

```
Aucun certificat d'accomplissement ne sera délivré.
```

# Prérequis

Afin de pouvoir suivre la formation, il est nécessaire d'avoir un environnement adéquate. Cela nécessite:

* un processeur intel ou amd
* un OS Windows et un OS Linux (kali)
* 8-16 Go de RAM

## Installation des OS

L'idéal est d'avoir une machine virtuelle Windows et une machine virtuelle Linux. Cependant, si la RAM n'est pas suffisante pour faire tourner 2 VMs, il est possible d'utiliser l'hôte, soit pour Windows, soit pour Linux.

### Linux

Il est recommandé d'utiliser la distribution [Kali](https://www.kali.org/). 

Cette machine servira essentiellement à la génération de shellcode qui seront ensuite utilisés sur la machine Windows. Si une autre distribution est envisagée, il faut s'assurer que le [framework Metasploit](https://github.com/rapid7/metasploit-framework) est bien installé.

### Windows

Il est recommandé d'utiliser une version de développement fournie par [Microsoft](https://developer.microsoft.com/fr-fr/windows/downloads/virtual-machines/). En effet, tout les outils de compilation sont déjà pré-installés. **Attention**, la VM est plutôt lourde ...

Plutôt que d'installer une VM de développement, il est possible d'installer une ISO classique puis d'installer les outils à la main. Pour cela:

* Télécharger [Visual Studio Installer (Community)](https://visualstudio.microsoft.com/fr/downloads/)
* Et choisir la suite de **Développment Desktop en C++**. Consulter la figure ci-dessous pour choisir les composants à installer

![C++ components](/img/index/cpp_components.png)

Afin de débugger le code, il est nécessaire d'installer un debugger:

* **WinDbg Preview** depuis le Microsoft Store
* **x64dbg** depuis ce [lien](https://x64dbg.com/)

Il peut être utile d'installer un désassembleur comme [IDA Free](https://hex-rays.com/ida-free/)

Installer ensuite [Visual Studio Code](https://code.visualstudio.com/download) pour coder. Une fois installé, ajouter le plugins **ASM Code Lens** comme sur la figure ci-dessous:

![asm code lens](/img/index/asm_code_lens.png)

Un éditeur hexadécimal est également requis, utiliser [HxD](https://www.lesnumeriques.com/telecharger/hxd-hex-editor-20536) par exemple.

Et enfin, l'outil [CFF Explorer](https://ntcore.com/?page_id=388) afin de constater la structure d'un exécutable.

