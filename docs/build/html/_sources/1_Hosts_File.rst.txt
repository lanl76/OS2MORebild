1. Hosts-filen
==============
Opsætte hosts-fil, opsætning af Ubuntu pakkestruktur samt installation af alle nødvendige pakker for at kunne domainjoine.

Filen finder du under :bash:/etc/hosts

Her sætter vi Hostname i hosts-filen

|   Hostname = ADMOS2MOT.<JERES_DOMÆNE> #ADMOS2MOT - T for test, P for produktion osv.
|   Domain = <JERES_DOMÆNE>
|   AD Grupper = OS2MO_ADMOS2MOT_Administrators

Kør alle kommandoer med sudo -i (super-user)

.. code-block:: bash

  hostname=$(hostname -s) # hostname -s giver os systemets hostname
  echo "127.0.0.1 $hostname.<JERES_DOMÆNE> $hostname" >> /etc/hosts #Her benytter vi den netop definerede variabel $hostname
