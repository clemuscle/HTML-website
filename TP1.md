## Etape 2 : Ouvrir une connexion SSH

```powershell
Microsoft Windows [version 10.0.19045.2251]
(c) Microsoft Corporation. Tous droits réservés.

C:\Users\cleme>netsh int ipv4 show addr "OpenVPN TAP-Windows6"

Configuration pour l'interface « OpenVPN TAP-Windows6 »
    DHCP activé:                          Oui
    Adresse IP :                           172.16.196.74
    Préfixe de sous-réseau :               172.16.196.72/30 (masque 255.255.255.252)
    Métrique de l'interface :             25


C:\Users\cleme>netsh int ipv6 show addr "OpenVPN TAP-Windows6"

Paramètres de l'adresse 2a03:7220:8083:c4c4::1011
---------------------------------------------------------
LUID d'interface      : OpenVPN TAP-Windows6
ID d'étendue          : 0.0
Durée de vie valide   : infinite
Durée de vie préférée : infinite
État DAD              : Préféré
Type d'adresse        : Manuel
Ignorer comme source  : false

Paramètres de l'adresse fe80::cd4f:d068:d6ac:6600%14
---------------------------------------------------------
LUID d'interface      : OpenVPN TAP-Windows6
ID d'étendue          : 0.14
Durée de vie valide   : infinite
Durée de vie préférée : infinite
État DAD              : Préféré
Type d'adresse        : Autre
Ignorer comme source  : false


C:\Users\cleme>netsh int ipv4 show route

Publier  Type      Mét  Préfixe                   Idx  Nom passerelle/interface
-------  --------  ---  ------------------------  ---  ------------------------
Non      Manuel    0    0.0.0.0/0                  10  172.17.128.1
Non      Manuel    256  0.0.0.0/1                  14  172.16.196.73
Non      Manuel    256  10.0.0.0/8                 14  172.16.196.73
Non      Manuel    256  89.234.156.196/32          10  172.17.128.1
Non      Système   256  127.0.0.0/8                 1  Loopback Pseudo-Interface 1
Non      Système   256  127.0.0.1/32                1  Loopback Pseudo-Interface 1
Non      Système   256  127.255.255.255/32          1  Loopback Pseudo-Interface 1
Non      Manuel    256  128.0.0.0/1                14  172.16.196.73
Non      Manuel    256  172.16.0.0/12              14  172.16.196.73
Non      Manuel    256  172.16.196.1/32            14  172.16.196.73
Non      Système   256  172.16.196.72/30           14  OpenVPN TAP-Windows6
Non      Système   256  172.16.196.74/32           14  OpenVPN TAP-Windows6
Non      Système   256  172.16.196.75/32           14  OpenVPN TAP-Windows6
Non      Système   256  172.17.128.0/19            10  Wi-Fi
Non      Système   256  172.17.149.81/32           10  Wi-Fi
Non      Système   256  172.17.159.255/32          10  Wi-Fi
Non      Manuel    256  192.168.0.0/16             14  172.16.196.73
Non      Système   256  192.168.56.0/24             6  Ethernet
Non      Système   256  192.168.56.1/32             6  Ethernet
Non      Système   256  192.168.56.255/32           6  Ethernet
Non      Manuel    256  198.18.0.0/15              14  172.16.196.73
Non      Manuel    256  198.51.100.0/24            14  172.16.196.73
Non      Manuel    256  203.0.113.0/24             14  172.16.196.73
Non      Système   256  224.0.0.0/4                 1  Loopback Pseudo-Interface 1
Non      Système   256  224.0.0.0/4                 6  Ethernet
Non      Système   256  224.0.0.0/4                20  OpenVPN Wintun
Non      Système   256  224.0.0.0/4                14  OpenVPN TAP-Windows6
Non      Système   256  224.0.0.0/4                11  Connexion réseau Bluetooth
Non      Système   256  224.0.0.0/4                10  Wi-Fi
Non      Système   256  224.0.0.0/4                18  Connexion au réseau local* 1
Non      Système   256  224.0.0.0/4                19  Connexion au réseau local* 10
Non      Système   256  255.255.255.255/32          1  Loopback Pseudo-Interface 1
Non      Système   256  255.255.255.255/32          6  Ethernet
Non      Système   256  255.255.255.255/32         20  OpenVPN Wintun
Non      Système   256  255.255.255.255/32         14  OpenVPN TAP-Windows6
Non      Système   256  255.255.255.255/32         11  Connexion réseau Bluetooth
Non      Système   256  255.255.255.255/32         10  Wi-Fi
Non      Système   256  255.255.255.255/32         18  Connexion au réseau local* 1
Non      Système   256  255.255.255.255/32         19  Connexion au réseau local* 10


C:\Users\cleme>netsh int ipv6 show route

Publier  Type      Mét  Préfixe                   Idx  Nom passerelle/interface
-------  --------  ---  ------------------------  ---  ------------------------
Non      Manuel    256  ::/3                       14  fe80::8
Non      Système   256  ::1/128                     1  Loopback Pseudo-Interface 1
Non      Manuel    256  2000::/4                   14  fe80::8
Non      Manuel    0    2a03:7220:8083:c4c4::/64   14  fe80::8
Non      Système   256  2a03:7220:8083:c4c4::1011/128   14  OpenVPN TAP-Windows6
Non      Manuel    256  3000::/4                   14  fe80::8
Non      Manuel    256  fc00::/7                   14  fe80::8
Non      Système   256  fe80::/64                   6  Ethernet
Non      Système   256  fe80::/64                  20  OpenVPN Wintun
Non      Système   256  fe80::/64                  14  OpenVPN TAP-Windows6
Non      Système   256  fe80::/64                  11  Connexion réseau Bluetooth
Non      Système   256  fe80::/64                  10  Wi-Fi
Non      Système   256  fe80::/64                  18  Connexion au réseau local* 1
Non      Système   256  fe80::/64                  19  Connexion au réseau local* 10
Non      Système   256  fe80::46a7:6c9e:90ec:1f68/128   11  Connexion réseau Bluetooth
Non      Système   256  fe80::74e1:6bce:34f0:6fd/128    6  Ethernet
Non      Système   256  fe80::831f:10d4:c104:b274/128   20  OpenVPN Wintun
Non      Système   256  fe80::942d:6b41:3bc3:51be/128   10  Wi-Fi
Non      Système   256  fe80::9698:acf5:a07a:dc29/128   18  Connexion au réseau local* 1
Non      Système   256  fe80::cd4f:d068:d6ac:6600/128   14  OpenVPN TAP-Windows6
Non      Système   256  fe80::de22:fdec:f38b:97cb/128   19  Connexion au réseau local* 10
Non      Système   256  ff00::/8                    1  Loopback Pseudo-Interface 1
Non      Système   256  ff00::/8                    6  Ethernet
Non      Système   256  ff00::/8                   20  OpenVPN Wintun
Non      Système   256  ff00::/8                   14  OpenVPN TAP-Windows6
Non      Système   256  ff00::/8                   11  Connexion réseau Bluetooth
Non      Système   256  ff00::/8                   10  Wi-Fi
Non      Système   256  ff00::/8                   18  Connexion au réseau local* 1
Non      Système   256  ff00::/8                   19  Connexion au réseau local* 10


C:\Users\cleme>ping -n 2 9.9.9.9

Envoi d’une requête 'Ping'  9.9.9.9 avec 32 octets de données :
Réponse de 9.9.9.9 : octets=32 temps=212 ms TTL=60
Réponse de 9.9.9.9 : octets=32 temps=161 ms TTL=60

Statistiques Ping pour 9.9.9.9:
    Paquets : envoyés = 2, reçus = 2, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 161ms, Maximum = 212ms, Moyenne = 186ms

C:\Users\cleme>ping -n 2 2620:fe::fe

Envoi d’une requête 'Ping'  2620:fe::fe avec 32 octets de données :
Réponse de 2620:fe::fe : temps=258 ms
Réponse de 2620:fe::fe : temps=79 ms

Statistiques Ping pour 2620:fe::fe:
    Paquets : envoyés = 2, reçus = 2, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 79ms, Maximum = 258ms, Moyenne = 168ms

C:\Users\cleme>netsh int ipv4 show dnsservers

Configuration pour l'interface « OpenVPN Wintun »
    Serveurs DNS configurés statiquement : Aucun
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Ethernet »
    Serveurs DNS configurés statiquement : Aucun
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « OpenVPN TAP-Windows6 »
    Serveurs DNS configurés via DHCP :     172.16.0.2
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Connexion au réseau local* 1 »
    Serveurs DNS configurés via DHCP :     Aucun
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Connexion au réseau local* 10 »
    Serveurs DNS configurés via DHCP :     Aucun
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Wi-Fi »
    Serveurs DNS configurés via DHCP :     130.120.124.102
                                           195.220.43.67
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Connexion réseau Bluetooth »
    Serveurs DNS configurés via DHCP :     Aucun
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Loopback Pseudo-Interface 1 »
    Serveurs DNS configurés statiquement : Aucun
    Enregistrer avec le suffixe :           Principale uniquement


C:\Users\cleme>netsh int ipv6 show dnsservers

Configuration pour l'interface « OpenVPN Wintun »
    Serveurs DNS configurés statiquement : fec0:0:0:ffff::1%1
                                           fec0:0:0:ffff::2%1
                                           fec0:0:0:ffff::3%1
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Ethernet »
    Serveurs DNS configurés statiquement : fec0:0:0:ffff::1%1
                                           fec0:0:0:ffff::2%1
                                           fec0:0:0:ffff::3%1
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « OpenVPN TAP-Windows6 »
    Serveurs DNS configurés via DHCP :     2001:678:3fc::1
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Connexion au réseau local* 1 »
    Serveurs DNS configurés via DHCP :     fec0:0:0:ffff::1%1
                                           fec0:0:0:ffff::2%1
                                           fec0:0:0:ffff::3%1
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Connexion au réseau local* 10 »
    Serveurs DNS configurés via DHCP :     fec0:0:0:ffff::1%1
                                           fec0:0:0:ffff::2%1
                                           fec0:0:0:ffff::3%1
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Wi-Fi »
    Serveurs DNS configurés via DHCP :     Aucun
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Connexion réseau Bluetooth »
    Serveurs DNS configurés via DHCP :     fec0:0:0:ffff::1%1
                                           fec0:0:0:ffff::2%1
                                           fec0:0:0:ffff::3%1
    Enregistrer avec le suffixe :           Principale uniquement

Configuration pour l'interface « Loopback Pseudo-Interface 1 »
    Serveurs DNS configurés statiquement : fec0:0:0:ffff::1%1
                                           fec0:0:0:ffff::2%1
                                           fec0:0:0:ffff::3%1
    Enregistrer avec le suffixe :           Principale uniquement

C:\Users\cleme>nslookup google.com
Serveur :   UnKnown
Address:  2001:678:3fc::1

DNS request timed out.
    timeout was 2 seconds.
DNS request timed out.
    timeout was 2 seconds.
Nom :    google.com
Address:  2a00:1450:4007:805::200e

C:\Users\cleme>nslookup alice.infra.stri
Serveur :   UnKnown
Address:  2001:678:3fc::1

Nom :    alice.infra.stri
Addresses:  2001:678:3fc:3::1
          172.16.0.1


C:\Users\cleme>ssh -p 2222 clementbenedetti@bob.infra.stri
The authenticity of host '[bob.infra.stri]:2222 ([2001:678:3fc:3::5]:2222)' can't be established.
ECDSA key fingerprint is SHA256:QNZ+Vmbf2IpIldOEGohSAkt3Vj6rCEPVMTCrTDQE6Uw.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[bob.infra.stri]:2222,[2001:678:3fc:3::5]:2222' (ECDSA) to the list of known hosts.
clementbenedetti@bob.infra.stri's password:
Permission denied, please try again.
clementbenedetti@bob.infra.stri's password:
Creating directory '/home/clementbenedetti'.
Linux bob 6.0.0-4-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.0.8-1 (2022-11-11) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
clementbenedetti@bob:~$ ^C
clementbenedetti@bob:~$ exit
déconnexion
Connection to bob.infra.stri closed.

C:\Users\cleme>ssh -p 2222 etu@asw01-308.infra.stri
ssh: connect to host asw01-308.infra.stri port 2222: Connection timed out
```

## Etape 2 : Configurer son client SSH

```
PS C:\Users\cleme\.ssh> notepad.exe config


# Exemple : hyperviseur Bob avec IPv6 sans DNS
Host bob6
 HostName 2001:678:3fc:3::5
 User etudianttest
 Port 2222
 ForwardAgent yes

# Exemple : hyperviseur Bob avec VPN et DNS
Host bob
 HostName bob.infra.stri
 User etudianttest
 Port 2222
 ForwardAgent yes 



PS C:\Users\cleme\.ssh> ssh bob
clementbenedetti@bob.infra.stri's password:
Linux bob 6.0.0-4-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.0.8-1 (2022-11-11) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Mon Nov 21 17:15:22 2022 from 2a03:7220:8083:c4c4::1011
clementbenedetti@bob:~$
```

## Etape 2 : Connexion passwordless

```powershell
PS C:\Windows\System32> cd C:\Users\cleme\.ssh\
PS C:\Users\cleme\.ssh> ssh-keygen -t ed25519
Generating public/private ed25519 key pair.
Enter file in which to save the key (C:\Users\cleme/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in C:\Users\cleme/.ssh/id_ed25519.
Your public key has been saved in C:\Users\cleme/.ssh/id_ed25519.pub.
The key fingerprint is:
SHA256:6x9y1r3/paldrDO3FPTdcmjmkoN6gN7Q25R3+C7g5Yw cleme@DESKTOP-1SN89QL
The key's randomart image is:
+--[ED25519 256]--+
|                 |
|                 |
|               . |
|              ..+|
|       oS  . .=.=|
|      o o.+o+*.+.|
|     . oo*=B=oo.+|
|      ..o=E.++=*o|
|        oo. .+B*=|
+----[SHA256]-----+
PS C:\Users\cleme\.ssh> ssh bob mkdir -p .ssh && touch .ssh/authorized_keys
clementbenedetti@bob.infra.stri's password:
Connection closed by 2001:678:3fc:3::5 port 2222
PS C:\Users\cleme\.ssh> ssh bob chmod 600 .ssh/authorized_keys

PS C:\Users\cleme\.ssh> type id_ed25519.pub | ssh bob "cat >> .ssh/authorized_keys"
clementbenedetti@bob.infra.stri's password:

PS C:\Users\cleme\.ssh> ssh bob
Linux bob 6.0.0-4-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.0.8-1 (2022-11-11) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Mon Nov 28 14:20:23 2022 from 2a03:7220:8083:c4c4::1002
clementbenedetti@bob:~$ exit
déconnexion
Connection to bob.infra.stri closed.
```

## Etape 3 : Machine virtuelle

```powershell
PS C:\Users\cleme\.ssh> ssh bob6
Linux bob 6.0.0-4-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.0.8-1 (2022-11-11) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Mon Nov 28 14:32:57 2022 from 2a03:7220:8083:c4c4::1002
clementbenedetti@bob:~$ ls -la
total 28
drwxr-x--x  3 clementbenedetti 10288 4096 21 nov.  18:32 .
drwxr-x--x 56 root             root  4096 27 nov.  20:22 ..
-rw-------  1 clementbenedetti 10288  126 28 nov.  14:23 .bash_history
-rw-r--r--  1 clementbenedetti 10288  220 21 nov.  17:15 .bash_logout
-rw-r--r--  1 clementbenedetti 10288 3526 21 nov.  17:15 .bashrc
-rw-r--r--  1 clementbenedetti 10288  807 21 nov.  17:15 .profile
drwxr-xr-x  2 clementbenedetti 10288 4096 21 nov.  18:32 .ssh
clementbenedetti@bob:~$ ln -s /var/cache/kvm/masters
clementbenedetti@bob:~$ ls -la
total 28
drwxr-x--x  3 clementbenedetti 10288 4096 28 nov.  14:44 .
drwxr-x--x 56 root             root  4096 27 nov.  20:22 ..
-rw-------  1 clementbenedetti 10288  126 28 nov.  14:23 .bash_history
-rw-r--r--  1 clementbenedetti 10288  220 21 nov.  17:15 .bash_logout
-rw-r--r--  1 clementbenedetti 10288 3526 21 nov.  17:15 .bashrc
lrwxrwxrwx  1 clementbenedetti 10288   22 28 nov.  14:44 masters -> /var/cache/kvm/masters
-rw-r--r--  1 clementbenedetti 10288  807 21 nov.  17:15 .profile
drwxr-xr-x  2 clementbenedetti 10288 4096 21 nov.  18:32 .ssh
clementbenedetti@bob:~$ mkdir vm
clementbenedetti@bob:~$ cd ./vm/
clementbenedetti@bob:~/vm$ ln -s ../masters/scripts/
clementbenedetti@bob:~/vm$ cp ../masters/debian-testing-amd64.qcow2 .
clementbenedetti@bob:~/vm$ ./scripts/ovs-startup.sh  debian-testing-amd64.qcow2 1024 134
~> Virtual machine filename   : debian-testing-amd64.qcow2
~> RAM size                   : 1024MB
~> SPICE VDI port number      : 6034
~> telnet console port number : 2434
~> MAC address                : b8:ad:ca:fe:00:86
~> Switch port interface      : tap134, access mode
~> IPv6 LL address            : fe80::baad:caff:fefe:86%vlan28
clementbenedetti@bob:~/vm$ ssh etu@fe80::baad:caff:fefe:86%vlan28
The authenticity of host 'fe80::baad:caff:fefe:86%vlan28 (fe80::baad:caff:fefe:86%vlan28)' can't be established.
ED25519 key fingerprint is SHA256:4MfGF/brnSNV1OQonxnM2QKoaRTnV6wiNi2sr4OQsH4.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added 'fe80::baad:caff:fefe:86%vlan28' (ED25519) to the list of known hosts.
etu@fe80::baad:caff:fefe:86%vlan28's password:
Linux vm0 6.0.0-4-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.0.8-1 (2022-11-11) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
You have no mail.
Last login: Sun Nov 27 11:24:40 2022 from fe80::e467:18ff:fe30:7b1c%enp0s1
etu@vm0:~$ ls
Mail
etu@vm0:~$ ls -a
.  ..  .bash_history  .bash_logout  .bashrc  .byobu  .config  .lesshst  Mail  .profile  .sudo_as_admin_successful  .viminfo
etu@vm0:~$ nano .bashrc
etu@vm0:~$ etu@vm0:~$ ll
total 64K
-rw------- 1 etu etu  22K 27 nov.  11:25 .bash_history
-rw-r--r-- 1 etu etu  220 18 févr.  2022 .bash_logout
-rw-r--r-- 1 etu etu 3,5K 18 févr.  2022 .bashrc
drwxr-xr-x 3 etu etu 4,0K  7 nov.  10:55 .byobu/
drwx------ 3 etu etu 4,0K  2 avril  2022 .config/
-rw------- 1 etu etu   39 11 nov.  08:53 .lesshst
drwxr-xr-x 3 etu etu 4,0K 28 nov.  15:18 .local/
drwx------ 2 etu etu 4,0K 10 juil. 09:45 Mail/
-rw-r--r-- 1 etu etu  807 18 févr.  2022 .profile
-rw-r--r-- 1 etu etu    0 25 mars   2022 .sudo_as_admin_successful
-rw------- 1 etu etu 4,3K 19 févr.  2022 .viminfo
etu@vm0:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether b8:ad:ca:fe:00:86 brd ff:ff:ff:ff:ff:ff
    inet 198.18.29.134/23 brd 198.18.29.255 scope global dynamic enp0s1
       valid_lft 84886sec preferred_lft 84886sec
    inet6 2001:678:3fc:1c:baad:caff:fefe:86/64 scope global dynamic mngtmpaddr
       valid_lft 86063sec preferred_lft 14063sec
    inet6 fe80::baad:caff:fefe:86/64 scope link
       valid_lft forever preferred_lft forever
etu@vm0:~$ sudo lsof -i
[sudo] Mot de passe de etu :
COMMAND  PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
dhclient 535 root    7u  IPv4  15582      0t0  UDP *:bootpc
sshd     609 root    3u  IPv4  18981      0t0  TCP *:2222 (LISTEN)
sshd     609 root    4u  IPv6  18983      0t0  TCP *:2222 (LISTEN)
sshd     609 root    5u  IPv4  18985      0t0  TCP *:ssh (LISTEN)
sshd     609 root    6u  IPv6  18987      0t0  TCP *:ssh (LISTEN)
sshd     671 root    4u  IPv6  19009      0t0  TCP [fe80::baad:caff:fefe:86]:ssh->[fe80::801:42ff:feb7:13ba]:57618 (ESTABLISHED)
sshd     696  etu    4u  IPv6  19009      0t0  TCP [fe80::baad:caff:fefe:86]:ssh->[fe80::801:42ff:feb7:13ba]:57618 (ESTABLISHED)
etu@vm0:~$ exit
déconnexion
Connection to fe80::baad:caff:fefe:86%vlan28 closed.
clementbenedetti@bob:~/vm$
clementbenedetti@bob:~/vm$ exit
déconnexion
Connection to 2001:678:3fc:3::5 closed.
PS C:\Users\cleme\.ssh> nano .\authorized_keys
PS C:\Users\cleme\.ssh> ls

    Directory: C:\Users\cleme\.ssh

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---          28/11/2022    14:17            104 authorized_keys
-a---          21/11/2022    18:13            279 config
-a---          28/11/2022    14:03            411 id_ed25519
-a---          28/11/2022    14:03            104 id_ed25519.pub
-a---          21/11/2022    18:31            209 known_hosts

PS C:\Users\cleme\.ssh> nano .\config

# Exemple : VM
Host vm0
 HostName 2001:678:3fc:1c:baad:caff:fefe:86
 User etu
 Port 2222
 ForwardAgent yes

PS C:\Users\cleme\.ssh> ssh vm0
The authenticity of host '[2001:678:3fc:1c:baad:caff:fefe:86]:2222 ([2001:678:3fc:1c:baad:caff:fefe:86]:2222)' can't be established.
ECDSA key fingerprint is SHA256:PzS2MzuhPIc3kFN91aO09jUT/vUe7x0Vzkx22Hj3s9o.
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added '[2001:678:3fc:1c:baad:caff:fefe:86]:2222' (ECDSA) to the list of known hosts.
etu@2001:678:3fc:1c:baad:caff:fefe:86's password:
Linux vm0 6.0.0-4-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.0.8-1 (2022-11-11) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
You have no mail.
Last login: Mon Nov 28 15:18:24 2022 from fe80::801:42ff:feb7:13ba%enp0s1
etu@vm0:~$
```

## Etape 4 : VDI + SPICE

```powershell
clementbenedetti@bob:~/vm$ ls -l
total 9104132
-rw-r--r-- 1 clementbenedetti 10288 3605331968 28 nov.  17:32 debian-testing-amd64.qcow2
-rw-r--r-- 1 clementbenedetti 10288     131072 28 nov.  14:54 debian-testing-amd64.qcow2_OVMF_VARS.fd
drwxr-xr-x 2 clementbenedetti 10288       4096 28 nov.  17:24 debian-testing-amd64.qcow2_TPM
-rw-r--r-- 1 clementbenedetti 10288 6610944000 28 nov.  17:22 kali-linux.qcow2
-rw-r--r-- 1 clementbenedetti 10288     131072 28 nov.  16:45 kali-linux.qcow2_OVMF_VARS.fd
drwxr-xr-x 2 clementbenedetti 10288       4096 28 nov.  17:22 kali-linux.qcow2_TPM
lrwxrwxrwx 1 clementbenedetti 10288         28 28 nov.  14:54 OVMF_CODE.fd -> /usr/share/OVMF/OVMF_CODE.fd
lrwxrwxrwx 1 clementbenedetti 10288         19 28 nov.  14:45 scripts -> ../masters/scripts/
clementbenedetti@bob:~/vm$ ./scripts/ovs-startup.sh kali-linux.qcow2 8192 135
~> Virtual machine filename   : kali-linux.qcow2
~> RAM size                   : 8192MB
~> SPICE VDI port number      : 6035
~> telnet console port number : 2435
~> MAC address                : b8:ad:ca:fe:00:87
~> Switch port interface      : tap135, access mode
~> IPv6 LL address            : fe80::baad:caff:fefe:87%vlan28
clementbenedetti@bob:~/vm$ lsof -i
COMMAND      PID             USER   FD   TYPE  DEVICE SIZE/OFF NODE NAME
qemu-syst 371634 clementbenedetti   13u  IPv6 8506099      0t0  TCP localhost:6034 (LISTEN)
qemu-syst 371634 clementbenedetti   34u  IPv6 8506168      0t0  TCP localhost:2434 (LISTEN)
qemu-syst 371634 clementbenedetti   35u  IPv4 8506169      0t0  TCP localhost:2434 (LISTEN)
qemu-syst 372670 clementbenedetti   13u  IPv6 8486313      0t0  TCP localhost:6035 (LISTEN)
qemu-syst 372670 clementbenedetti   34u  IPv6 8486383      0t0  TCP localhost:2435 (LISTEN)
qemu-syst 372670 clementbenedetti   35u  IPv4 8486384      0t0  TCP localhost:2435 (LISTEN)
clementbenedetti@bob:~/vm$ exit
déconnexion
Connection to bob.infra.stri closed.
PS C:\Users\cleme\.ssh> ssh -L 6035:localhost:6035 bob6
Linux bob 6.0.0-4-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.0.8-1 (2022-11-11) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Mon Nov 28 17:23:42 2022 from 2a03:7220:8083:c4c4::1002
clementbenedetti@bob:~$ lsof -i
COMMAND      PID             USER   FD   TYPE  DEVICE SIZE/OFF NODE NAME
qemu-syst 371634 clementbenedetti   13u  IPv6 8506099      0t0  TCP localhost:6034 (LISTEN)
qemu-syst 371634 clementbenedetti   34u  IPv6 8506168      0t0  TCP localhost:2434 (LISTEN)
qemu-syst 371634 clementbenedetti   35u  IPv4 8506169      0t0  TCP localhost:2434 (LISTEN)
qemu-syst 372670 clementbenedetti   13u  IPv6 8486313      0t0  TCP localhost:6035 (LISTEN)
qemu-syst 372670 clementbenedetti   34u  IPv6 8486383      0t0  TCP localhost:2435 (LISTEN)
qemu-syst 372670 clementbenedetti   35u  IPv4 8486384      0t0  TCP localhost:2435 (LISTEN)
```

## Etape 5: Google Remote Desktop

A cette étape, pour permettre des facilité, nous allons travailler avec une machine virtuelle avec comme OS Windows 11.
Il faut donc se connecter à la VM via le serveur Bob. Il suffit par la suite de suivre les étapes sur `remotedesktop.google.com` dans l'onglet `Configurer via SSH`.
Une seule configuration s'effectue avec PowerShell:

```powershell
& "${Env:PROGRAMFILES(X86)}\Google\Chrome Remote Desktop\CurrentVersion\remoting_start_host.exe" --code="4/0AfgeXvs1FD-NkwgPXsSgwbE2mKVZHTJO8lGMEBjDx_nNH1eNX-jbeJRYcW9vKh9ZeJ6qcg" --redirect-url="https://remotedesktop.google.com/_/oauthredirect" --name=$Env:COMPUTERNAME
```

Par la suite un paramètre de sécurité est mis en place par un code PIN sur la VM.

Maintenant il suffit d'aller sur n'importe quel machine physique hôte et de se connecter avec le même compte google sur `remotedesktop.google.com` et d'accéder à l'onglet `Accès à distance`.
Normalement un nouvel appareil apparaîtra, qui correspond à la VM, et alors il suffit d'y se connecter avec le code PIN présaisi pour accéder à la VM.
