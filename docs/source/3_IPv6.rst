3. Disabling af IPv6-opslag
###########################

Vi har i Rebild Kommune valgt at disable IPv6 fra alle servere da vi har oplevet problemer med at tilgå disse fra visse lokationer grundet routing.
Snak med jeres interne netværksteam om dette også er noget i bør gøre i jeres opsætning.

Alle kommandoer skal afvikles med root privileger - sudo -i

.. code-block:: bash

   echo "net.ipv6.conf.all.disable_ipv6 = 1" >> /etc/sysctl.d/99-sysctl.conf
   echo "net.ipv6.conf.default.disable_ipv6 = 1" >> /etc/sysctl.d/99-sysctl.conf
   echo "net.ipv6.conf.lo.disable_ipv6 = 1" >> /etc/sysctl.d/99-sysctl.conf

   #genindlæs sysctl konfiguration
   sysctl -p
