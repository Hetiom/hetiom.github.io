> [!tip]+ Config
>- **OS :** openSUSE Tumbleweed 20240823 x86_64
>- **Kernel :** Linux 6.10.5-1-default
>- **Shell :** bash 5.2.32
# Installation :
***Premier boot sur clé d'installation*** :
- Sélection des dépôts de base
- installation de KDE Plasma
- Partitionnement : ![[Pasted image 20240826162219.png]]
- reboot (ok)
```bash
sudo zypper refresh (ok)
sudo zypper dub (ok)
```
- léger ricing de KDE 
- 🔗 installation de discord depuis **`Yast`**
- 🔗 installation de gearlever depuis **`Yast`** (permet de mieux gérer des .Appimage)
- 🔗 installation de Obsidian en appimage
```bash
# ajout des dépôts packman
sudo zypper addrepo -cfp 90 'https://ftp.gwdg.de/pub/linux/misc/packman/suse/openSUSE_Tumbleweed/' packman
```
- 🔗 installation de vscodium en flatpak depuis **`discover`**
- 🔗 installation de synology drive-client depuis **`github.com/EmixamPP/synology-drive`** :
```bash
cd ~/Software

sudo zypper in rpm-build rpmdevtools

git clone https://github.com/EmixamPP/synology-drive.git

cd synology-drive

# Optional: Spécifier la bonne version en éditant les deux premières lignes: nano synology-drive-noextra.spec (Gnome) ou nano synology-drive.spec (autre desktop env) #

mkdir -p /home/tiphyz/rpmbuild/SOURCES/ # créer un dossier pour le script

rpmdev-spectool -g -R synology-drive-noextra.spec

rpmdev-spectool -g -R synology-drive-noextra.spec

rpmbuild -ba synology-drive-noextra.spec

sudo zypper install ~/rpmbuild/RPMS/x86_64/synology-drive-noextra-3.5.1-16101.x86_64.rpm

rm -r ~/rpmbuild
```

# LVM

**LVM** permet une gestion flexible des partitions de disque. Contrairement aux partitions traditionnelles, LVM permet d'agrandir ou de réduire la taille des partitions à la volée, et de les répartir sur plusieurs disques physiques.

**Etat des volumes à la création :**
```bash
tiphyz@Titi-OpenSuse:~> sudo vgdisplay  
 --- Volume group ---  
 VG Name               system  
 System ID                
 Format                lvm2  
 Metadata Areas        1  
 Metadata Sequence No  3  
 VG Access             read/write  
 VG Status             resizable  
 MAX LV                0  
 Cur LV                2  
 Open LV               2  
 Max PV                0  
 Cur PV                1  
 Act PV                1  
 VG Size               953,37 GiB  
 PE Size               4,00 MiB  
 Total PE              244062  
 Alloc PE / Size       244062 / 953,37 GiB  
 Free  PE / Size       0 / 0      
 VG UUID               csDyIo-Wzqk-w2ML-VgDq-qeJn-pDWe-l5YwB3

---------------------------------------------------------------------------

tiphyz@Titi-OpenSuse:~> sudo lvdisplay  
 --- Logical volume ---  
 LV Path                /dev/system/swap  
 LV Name                swap  
 VG Name                system  
 LV UUID                epZUfD-8zaB-lxx8-VgcU-vWO3-69eP-14pVEB  
 LV Write Access        read/write  
 LV Creation host, time install, 2024-08-26 10:53:31 +0200  
 LV Status              available  
 # open                 1  
 LV Size                2,00 GiB  
 Current LE             512  
 Segments               1  
 Allocation             inherit  
 Read ahead sectors     auto  
 - currently set to     1024  
 Block device           254:0  
     
 --- Logical volume ---  
 LV Path                /dev/system/root  
 LV Name                root  
 VG Name                system  
 LV UUID                8ynh5d-oVVy-eFgo-tuLg-VSiM-pycP-BQJmw1  
 LV Write Access        read/write  
 LV Creation host, time install, 2024-08-26 10:53:32 +0200  
 LV Status              available  
 # open                 1  
 LV Size                951,37 GiB  
 Current LE             243550  
 Segments               1  
 Allocation             inherit  
 Read ahead sectors     auto  
 - currently set to     1024  
 Block device           254:1
```

# Btrfs
**snapshots de / excluant** :
- `/boot/grub2/i386-pc`, `/boot/grub2/x86_64-efi`, `/boot/grub2/powerpc-ieee1275`, `/boot/grub2/s390x-emu`
- `/home`
- `/opt`
- `/srv`
- `/tmp`
- `/usr/local`
- `/var`
**⚠️** les Snapshots btrfs ne sont pas des backups de données.

**modifications** : 
```bash
sudo snapper --config root set-config "TIMELINE_CREATE=no"
```

# Timeshift
- **Création de snapshots automatiques quotidienne sur `/` et `/home` (incluant les fichiers cachés pour /home) sur dm-1**.

#  Maintenance
## Zypper

[[Zypper]] ***<-- Cheat sheet**

## Yast
