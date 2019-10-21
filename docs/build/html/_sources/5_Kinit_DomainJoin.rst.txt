5. Kinit
########

Efter opsætningen af Realmd udføres selve Domainjoin. Brugeren, der benyttes til kommandoerne herunder skal have lov til at melde computeren (OS2MO serveren) ind i domænet.

DETTE SKAL KØRES MANUELT EN LINJE AF GANGEN

Initier Kinit og meld derefter ind i domænet. # Dette step skal køres en kommando af gangen, da den ellers ikke vil virke.

.. code-block:: bash

  kinit admra@<JERES_DOMÆNE>

# Vi bør nu have modtaget et kerberos ticket fra vores AD til vores Domain bruger. Vi kan, hvis vi ønsker at verificere dette, køre kommandoen herunder.

.. code-block::bash

  klist

.. code-block::bash

  ***Start - output fra succesfuld klist kommando ###

  Ticket cache: FILE:/tmp/krb5cc_790070301_wj44Ws
  Default principal: admra@REBILD:LAN

  Valid starting       Expires              Service principal
  05/03/2019 13:02:39  05/03/2019 23:02:39  krbtgt/JERES_DOMÆNE@JERES_DOMÆNE
  renew until 05/04/2019 13:02:39

  ### Slut - output fra succesfuld klist kommando ###

# Med et kerberos ticket på maskinen kan vi foretage domainjoin.

.. code-block::bash

  realm --verbose join -U admra <JERES_DOMÆNE>
  #Læg her mærke til at der er skrevet Brugernavn “mellemrum” domæne.
