2. sources.list, apt update og apt install
##########################################
Opdater pakkebiblioteker og installer pakker
----------------------------------------------
Her bruger vi sed til at erstatte 'main' med 'main restricted universe'

.. code-block:: bash

   sed -i 's/main/main restricted universe/g' /etc/apt/sources.list

   # opdater pakkelisterne med apt update
   apt update

   # installér herefter pakkerne med apt install
   apt install realmd sssd sssd-tools samba-common krb5-user packagekit samba-common-bin samba-libs adcli ntp ntpdate -y
