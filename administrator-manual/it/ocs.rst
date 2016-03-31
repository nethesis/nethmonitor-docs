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
* backup dei dati integrato nella procedura di backup di |parent_product|


Accesso
=======

Per accedere all':dfn:`interfaccia web` di OCS Inventory è sufficiente utilizzare il link presente nella sezione *Applicazioni* 
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

Inventario
----------

La feature principale di OCS Inventory è quella di raccogliere i dati relativi alle caratteristiche *hardware* e
*software* del parco IT in cui viene inserito.
La raccolta dei dati avviene tramite l'adozione di un :dfn:`agent` software che va installato direttamente sul nodo
da inventariare.
OCS Inventory mette a disposizione degli :index:`agent` per tutte le piattaforma software più diffuse, i pacchetti di
installazione sono scaricabili direttamente `dal sito del prodotto <http://www.ocsinventory-ng.org/en/download/download-agent.html>`_
e sono disponibili negli store delle piattaforme mobile.
OCS Inventory mette anche disposizione alcuni tool che consentono il depoly massivo da remoto degli agent sugli host 
apparteneneti alla rete oggetto di inventario:

* `OCS Inventory NG Agent Deployement tool <http://wiki.ocsinventory-ng.org/index.php/Documentation:DeployTool>`_
* `OCSPackager <http://wiki.ocsinventory-ng.org/index.php/Documentation:Packager>`_
* `OCSLogon <http://wiki.ocsinventory-ng.org/index.php/Documentation:WindowsAgent#Deploying_Agent_using_launcher_OcsLogon.exe_through_Login_Script_or_Active_Directory_GPO.>`_

.. note:: Per utilizzare il deploy massivo degli agent è necessario avere delle credenziali amministrative dei computer remoti!


IpDiscover
----------

OCS Inventory mette a disposizione una funzionalità di :dfn:`autodiscovery` utile per esplorare gli host presenti in rete.
Il principio di funzionamento è particolare: richiede che il server abbia inventariato almeno un host della rete che verrà 
successivamente utilizzato da vero e proprio :dfn:`proxy` per la raccolta delle informazioni relative agli altri host della 
rete.
In normali condizioni di funzionamento sarà il server stesso ad eleggere uno degli host inventariati :dfn:`Gateway IP` attraverso 
cui mappare tutti gli altri host della rete.
Il meccanismo di elezione che determina quale macchina fungerà da :index:`Gateway IP` prevede la valutazione di specifici
criteri basati su tipo e verisone del sistema opertivo dell'hoste e sulla qualità della comunicazione con OCS Inventory, è però
possibile forzare il sistema ad usare uno specifico host (si veda `la documentazione ufficiale <http://wiki.ocsinventory-ng.org/index.php/Documentation:Ipdiscover#Election_mechanism.>`_).


Plugins
-------

OCS Inventory contempla un nutrito numero di :dfn:`plugins`, dei veri e propri moduli aggiuntivi che è possibile implementare 
sul core di inventorying per ampliarne le capacità.
Tutti i riferimenti sono disponibile nella `documentazione ufficiale <http://wiki.ocsinventory-ng.org/index.php/Plugins:version2>`_.


