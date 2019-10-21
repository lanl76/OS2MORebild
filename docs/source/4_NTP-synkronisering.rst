3. Opsætning af NTP-synkronisering samt realmd
##############################################

Opsætning af NTP
----------------
Opsæt timezone og npt client – ”rebild.lan” anvendes som ntp server i Rebild, da det er et DNS navn, som returnerer ip på vores domænecontrollerservere, som har NTP service kørende.

.. code-block:: bash

    timedatectl set-timezone Europe/Copenhagen

    #Herunder indsætter vi NTP-serveren på listen
    sed -i '/# Specify one or more NTP servers./a \server <JERES_DOMÆNE>' /etc/ntp.conf

    #Her maskerer vi Ubuntupool fra listen - vi benytter regexp for at finde 'pool *.ubuntu' og rette det til et med en maskeret version
    sed -i -r 's/pool (.*).ubuntu/#pool \1.ubuntu/g' /etc/ntp.conf

    systemctl restart ntp

# Husk at rette jeres domain navne og os-version så den passer til jeres miljø.
# Det vi opsættter i realmd.conf er hvor vi ønsker at bruger ”home” biblioteker skal placeres samt nødvendige domæne oplysninger og specificering af AD klient type.
# Yderligere info kan findes på http://manpages.ubuntu.com/manpages/bionic/man5/realmd.conf.5.html

Opsætning af realmd
-------------------
Filen /etc/realmd.conf

.. code-block:: bash

  [users]
  default-home = /home/%D/%U
  default-shell = /bin/bash

  [active-directory]
  default-client = sssd
  os-name = Ubuntu Server
  os-version = 16.04

  [service]
  automatic-install = no

  [rebild.lan]
  fully-qualified-names = no
  automatic-id-mapping = yes
  user-principal = yes
  manage-system = no

  [rebild.dk]
  fully-qualified-names = no
  automatic-id-mapping = yes
  user-principal = yes
  manage-system = no
