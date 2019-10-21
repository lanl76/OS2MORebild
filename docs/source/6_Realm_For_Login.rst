6. Realm og Login-rettigheder
=============================

Vi strammer nu sikkerheden så det kun er Domain Admins og en bestemt gruppe der kan tilgå serveren. Opret en AD gruppen som du ønsker at bruge til at styre hvilke AD konti de skal have.

Administratorrettigheder til OS2MO serverne
-------------------------------------------
I Rebild har vi kaldt gruppen: ”OS2MO_ADMOS2MOT_Administrators.<JERES_DOMÆNE>_Administrators”

Opsæt Realm til kun at tillade login af Domain Admins

.. code-block:: bash

  realm deny --all
  realm permit -g 'Domain Admins' 'SRV_OS2MO_<JERES_SERVERNAVN>_Administrators'
  systemctl restart sssd
