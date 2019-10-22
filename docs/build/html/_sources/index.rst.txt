.. OS2Mo Rebild Opsætning documentation master file, created by
   sphinx-quickstart on Thu Oct 17 18:06:57 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Velkommen til OS2MO Rebild's opsætning og dokumentation!
========================================================
    .. figure:: RUbuntu.png
        :width: 200
        :alt: Alternative text
        :figclass: align-right

.. toctree::
   :maxdepth: 2

   1_Hosts_File.rst
   2_Apt_Update.rst
   3_IPv6.rst
   4_NTP-synkronisering.rst
   5_Kinit_DomainJoin.rst
   6_Realm_For_Login.rst
   7_Samba_AutoHomeDir.rst
   8_Kerberos.rst
   9_Sudoers.rst
   10_OpdaterGenstart.rst

* :ref:`Search`

OS2MO Server
============
  .. figure:: OS2MO_Produktbanner.png
      :width: 200
      :alt: OS2MO OS2MO_Produktbanner
      :figclass: align-left

OS2MO Serveren ved Rebild Kommune er en Ubuntu 16.04.
Ubuntu Serveren har vi opsat så den er domainjoined, hvilket giver fordelen, at vores IT-folk og eksterne Magentakonsulenter kan bruge AD
Brugernavn og kode til at logge på serveren.

Rettigheder styres derved via AD, som tilfældet er med Windows servere.

**Ubuntuserveren trin for trin:**

Installer Ubuntu serveren via ISO (det anbefales at man som minimum har brugerkendskab til Linux og SSH for at udføre denne guide)
Under installationen skal der opsættes Fast IP på serveren.

Denne vejledning/dokumentation er blevet til efter hjælp af Nils Rimestad, Viborg og dennes meget grundige viden på området. Ligeledes er vejledningen
kopieret og tilrettet fra Viborgs, så den passer til det setup, vi har i Rebild Kommune.

**/Lars Lyngsøe Højberg**
