.. index::
   single: installazione
   single: abilitazione

.. _installation-section:

Installazione
=============

Requisiti minimi
----------------

|product| è uno dei tanti moduli installabile su base |parent_product|, pertanto per implementarlo è necessario 
innazitutto installare e registare |parent_product|.
Per i requisiti minimi, la compatibilità hardware e le modalità di installazione e registrazione fare riferimento 
alla documentazione specifica (si veda `qui per l'installazione <http://nethservice.docs.nethesis.it/it/latest/installation.html>`_  e `qui per la registrazione <http://nethservice.docs.nethesis.it/it/latest/registration.html>`_).

.. warning:: NethMonitor NG è al momento disponibile **solo su piattaforma NethServer Enterprise 6.8**.

.. _qualification_section:

Abilitazione
------------

Terminate l'installazione e la registrazione della licenza di |parent_product|, prima di procedere all'installazione 
del pacchetto |product| si dovrà :index:`abilitare` il server ad ospitare il sistema di monitoraggio.
Tale operazione va eseguita tramite :dfn:`Centro Servizi`, accessibile con la coppia utente/password all'indirizzo |register_link|.

Una volta eseguito l'accesso al *Centro Servizi*, spostarsi nel menu :dfn:`Amministrazione` quindi scegliere la 
scheda :dfn:`Nethmonitor`.
L'interfaccia cui si accede consente aggiungere e gestire i le macchine abilitate ad ospitare |product|: cliccando 
sul pulsante *Aggiungi* sarà possibile scegliere uno dei |parent_product| con licenza attiva e, per portare correttamente
a termine la procedura, sarò necessario fornire tutti gli altri parametri richiesti:

* :dfn:`WAN Host`: è l'ip verso cui il |product| si aspetta di ricevere i risultati dei controlli passivi e dei quelli tramite sonda;
* :dfn:`NSCA Port`: è la porta su cui lavora il protocollo di monitoraggio passivo e tramite sonda, normalmente è la **5667**;
* :dfn:`HTTPS Port`: è la porta https sulla quale si può contattare il |product|, normalmente è la **443**;
* :dfn:`Note`: è un campo descrittivo a disposizione dell'amministratore.

Una volta salvata la configurazione il |parent_product| avrà tutti i prerequisiti necessari ad ospitare una istanza di |product|.

.. note:: E' indispensabile sincerarsi che il |parent_product| sia raggiungibile sulle porte HTTPS ed NSCA configurate!

.. warning:: Un NethServer Enterprise *deve essere definito una ed una sola volta come NethMonitor!* Applicare più
             configurazioni NethMonitor al medesimo NethServer Enterprise creerebbe delle inconsistenze che 
             provocherebbero dei problemi di comunicazione con eventuali :ref:`probe-section` o host configurati 
             per il :ref:`passivemonitoring-section`.

Terminate le operazioni preliminari, sarà possibile installare |product| attraverso l'apposita voce presente nel `Software Center <http://nethserver.docs.nethesis.it/it/latest/packages.html>`_.


