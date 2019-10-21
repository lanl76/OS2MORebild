7. Konfiguration af Samba samt automatisk oprettelse af Home-dir
################################################################

Vi opsætter Homemappen på linux serveren samt opsætter Samba.
Samba skal kun bruges hvis man ønsker at kunne tilgå mapper på et Windows File Share.

Opsæt automatisk opsætning af Homedir
-------------------------------------

.. code-block:: bash

  sed -i -e '/pam_sss.so/a \#Inserted by Script - LLH\nsession required pam_mkhomedir.so skel=/etc/skel/ umask=0077\n#End Inserted by Script - NIR' /etc/pam.d/common-session

Opsæt SAMBA
-----------

.. code-block: bash

  cp /etc/samba/smb.conf /etc/samba/smb.conf.initial #Backup intial config
  sed -i '/\[global\]/a workgroup = REBILD\nclient signing = yes\nclient use spnego = yes\nkerberos method = secrets and keytab\nrealm = <JERES_DOMÆNE>\nsecurity = ads' /etc/samba/smb.conf
