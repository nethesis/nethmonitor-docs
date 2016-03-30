.. index::
   single: OCS Inventory

.. _ocs-section:

================
OCS Inventory NG
================


Introduzione
============

`OCS Inventory NG <http://www.ocsinventory-ng.org/en/>`_ è un software che consente un'agevole
raccolta dei dati di inventario degli asset presenti in una infrastruttura IT.
:index:`OCS Inventory NG` collezione le informazioni relative all'hardware ed al software delle
macchine interconnesse alla rete locale attraverso l'esecuzione di un agent software
(*OCS Inventory Agent*), visualizzandole in modo completo attraverso un'organizzata interfaccia
web based.
Inoltre, OCS Inventory NG è in grado di eseguire il deploy massivo di applicazioni e configurazioni
e di arrichire le sue funzionalità nella raccolta dati attraverso l'implementazione di numerosi
plugin.


**Caratteristiche principali:**

* raccolta caratteristiche hw e sw degli host inventariati
* potente modulo di deploy massivo per la distribuzione di software e script
* console di amministrazione web based
* autodiscovery di rete
* supporto multipiattaforma (Windows, Linux, BSD, Sun Solaris, IBM AIX, HP-UX, MacOSX)
* web service accessibile via interfaccia SOAP
* supporto a numerosi plugin
* backup dei dati di Adagios integrato nella procedura di backup di |product|


Accesso
=======

Per accedere all':dfn:`interfaccia web` di |ocs| è sufficiente utilizzare il link presente nella sezione *Applicazioni* 
della *Dashboard* di |parent_product|.
E' altrimenti possibile accedere direttamente all'applicativo senza passare per il *server-manager* digitando nella barra 
degli indirizzi ``https://a.b.c.d/ocsreports`` oppure ``https://server/ocsreports`` dove *a.b.c.d* e *server* sono 
rispettivamente l'indirizzo IP ed il nome del server impostati in fase di installazione.


Il Server Manager utilizza certificati SSL auto-firmati, sarà quindi necessario
accettare esplicitamente tali certificati la prima volta che si accede al server.
La connessione è comunque sicura e cifrata.

Login
-----

Per accedere all'interfaccia è necessario utilizzare le credenziali di ``admin`` che, di default, non sono attive.
Per attivare l'utente seguire le indicazioni riportate in `questa pagina <http://nethserver.docs.nethesis.it/it/latest/accounts.html#admin-user-section>`_ del manuale di |parent_product|.

.. _ocs-features:

Funzionalità
============


