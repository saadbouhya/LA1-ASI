# LA1-ASI
School course

*Exclure les adresses ipv4*<br/>
"""
ip dhcp excluded-address low-address [high-address]
"""
*Définir un nom de pool DHCPv4*<br/>
"""
ip dhcp pool pool-name
"""
| tache											 | Commande IOS										|
| ------------------------------------------- 	 | ------------------------------------------------ |
| Définir le pool d'adresses					 | network network-number [mask  / prefix-length]   |
| Définir le routeur ou la passerelle par défaut | default-router address [ address2….address8]     |
| Définir un serveur DNS                         | dns-server address [ address2…address8]          |
| Définir le nom de domaine                      | domain-name domain                               |
| Définir la durée du bail DHCP                  | lease {days [hours [ minutes]] | infinite}       |
| Définir le serveur WINS NetBIOS                | netbios-name-server address [ address2…address8] |

*Exemple*<br/>
"""
R1(config)# ip dhcp excluded-address 192.168.10.1 192.168.10.9
R1(config)# ip dhcp excluded-address 192.168.10.254
R1(config)# ip dhcp pool LAN-POOL-1
R1(dhcp-config)# network 192.168.10.0 255.255.255.0
R1(dhcp-config)# default-router 192.168.10.1
R1(dhcp-config)# dns-server 192.168.11.5
R1(dhcp-config)# domain-name example.com
R1(dhcp-config)# end
R1#
"""
*Commandes de vérification DHCPv4*<br/>
"""
show running-config | section dhcp # Affiche les commandes DHCPv4 configurées sur le routeur.
show ip dhcp binding # Affiche une liste de toutes les liaisons d'adresses IPv4 vers MAC fournies par le service DHCPv4.
show ip dhcp server statistics # Cette commande permet d'afficher le nombre de messages DHCPv4 envoyés et reçus.
"""

