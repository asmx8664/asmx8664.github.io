# Prérequis

Afin de pouvoir suivre la formation, il est nécessaire d'avoir un environnement adéquate. Cela nécessite:

* un processeur intel ou amd
* un OS Windows et un OS Linux (kali)

## installation des OS

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

Installer [Visual Studio Code](https://code.visualstudio.com/download) pour coder. Une fois installé, ajouter le plugins **ASM Code Lens** comme sur la figure ci-dessous:

![asm code lens](/img/index/asm_code_lens.png)

Un éditeur hexadécimal est également requis, utiliser [HxD](https://www.lesnumeriques.com/telecharger/hxd-hex-editor-20536) par exemple.

Et enfin, l'outil [CFF Explorer](https://ntcore.com/?page_id=388) afin de constater la structure d'un exécutable.