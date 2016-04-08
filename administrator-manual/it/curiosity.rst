.. index::
   single: Sonde
   single: Curiosity

.. _probe-section:

========================
Sonde remote Curiosity
========================


Introduzione
============

Le :dfn:`sonde remote Curiosity` sono la soluzione ideale per gestire in modo semplice ed efficace il 
monitoraggio di host remoti localizzati in sedi periferiche.
Si tratta di veri e propri appliance autoconfiguranti che collegati ad una rete dotata di 
server DHCP sono in grado di recepire un indirizzo e mettersi in comunicazione con il |product| 
a cui vengono correlate, fungendo da veri e propri proxy di monitoraggio: una volta accese, le 
sonde possono scansionare la rete in cui vengono inserite, restituendo al |product| il 
risultato dell'attività di discovery.
Attraverso l'interfaccia :dfn:`Wizard` è possibile inviare alla sonda le configurazioni di monitoraggio 
predisposte centralmente per abilitare il controllo dei nodi della rete remota.

.. note:: Le sonde sono in grado di gestire **unicamente** controlli di tipo **attivo agentless**.


.. _probe-qualification:

Abilitazione sonde
==================

Per poter essere utilizzate, le :index:`sonde remote` :index:`Curiosity` necessitano di essere attivate e 
collegate ad una istanza di |product| attraverso una semplice procedura di abilitazione.

Ad ogni sonda è associato un :dfn:`hash`, un codice costituito da 16 alfanumerici - diviso in due gruppi
da 8 per facilitarne la leggibilità - (esempio: ``A1B2C3D4-5E6F7G8H``) che viene gerenrato in fase di 
assemblaggio della sonda e che la caratterizza :dfn:`univocamente`: non esisteono due sonde con il medesimo :index:`hash`.

L'*hash* è riportato in tre posti distinti:

* sull'imballaggio della :index:`sonda`;
* nel :dfn:`QRCode` visualizzabile collegando un monitor ad una sonda **non registrata**;
* in colore verde nel banner di login della console visulalizzabile collegando un monitor ad una sonda **registrata**

Il codice alfanumerico univoco è indispensabile per attivare la sonda e metterla in comunicazione con il
|product| che fungerà da :dfn:`parent` della sonda, cioè attraverso cui la sonda potrà essere controllata
e gestita.
Una volta entrati in possesso della sonda si dovrà accedere al :dfn:`Centro Servizi`, recarsi nel pannello
:dfn:`Amministrazione`, scheda :dfn:`Nethmonitor`.
Nella sezione :dfn:`Sonde Libere` sarà possibile inserire la nuova sonda inserendo:

* :dfn:`Etichetta`: una stinga descrittiva;
* :dfn:`Code`: il codice *hash*;
* :dfn:`Note`: un campo libero.

.. warning:: L'*hash* andrà indicato nel campo *Code* **senza** il carattere separatore, inserendo tutti e 16 gli
             alfanumerici uno di seguito all'altro.
             In caso contrario l'operazione **genererà un errore**!

Inseriti i dati della nuova sonda, questa apparirà nell'elenco delle :index:`sonde libere`.

Spostandosi nella :index:`sezione Nethmonitor` della stessa pagina verranno visualizzati tutti i |product|
attivati precedentemente con la procedura di :ref:`qualification_section`.
Ciascun |product| in elenco avrà una icona a forma di simbolo ``+``: cliccando sull'icona si aprirà
una finestra pop-up  attraverso cui sarà possibile :index:`associare la sonda` al |product| che fungerà
da *parent*.

Da quel momento la sonda potrà essere controllata direttamente dal |product| associato attraverso l'interfaccia :ref:`wizard-section`.
