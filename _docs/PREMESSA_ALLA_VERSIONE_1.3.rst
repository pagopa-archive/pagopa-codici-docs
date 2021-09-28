
|pagoPA_logo|
   
+---------------------------------------------------------------------------------------------------+
| **SPECIFICHE ATTUATIVE DEI CODICI IDENTIFICATIVI DI VERSAMENTO, RIVERSAMENTO E RENDICONTAZIONE**  |
|                                                                                                   |
|                                                                                                   |
| *Allegato A alle "Linee guida per l'effettuazione dei pagamenti elettronici a favore delle*       |
| *pubbliche amministrazioni e dei gestori di pubblici servizi"*                                    |
|                                                                                                   |
|                                                                                                   |
| **Versione 1.3.1 - gennaio 2018**                                                                 |
+---------------------------------------------------------------------------------------------------+

**Premessa alla Versione 1.3**

La diffusione del sistema pagoPA\ :sup:`®` con l'adesione di molteplici
soggetti che offrono servizi di interconnessione al Nodo dei
Pagamenti-SPC, i cosiddetti intermediari e partner tecnologici, ha dato
luogo alla possibilità che un Ente Creditore utilizzi soggetti diversi
per consentire ai cittadini di effettuare pagamenti elettronici.

È questo il caso, ad esempio, dei comuni che si servono di Unioncamere
per erogare i servizi SUAP e che parimenti utilizzano anche
l'intermediazione della Regione di appartenenza per consentire i
pagamenti elettronici previsti dalle Linee guida.

Altro caso cui fare riferimento è quello legato al nuovo servizio di
emissione della Carta di Identità Elettronica, per il quale il Ministero
degli Interni è intermediario tecnologico di tutti i comuni italiani.

Tutto ciò premesso, la presente versione delle Specifiche attuative dei
codici identificativi di versamento, riversamento e rendicontazione
contiene l'aggiornamento delle regole di generazione del codice IUV, già
anticipate con il documento monografico "*Utilizzo del codice IUV per
enti plurintermediati*".

Le presenti specifiche aggiornano le regole di generazione del codice
IUV definite al `paragrafo 7.4.1 <http://pagopa-specifichepagamenti.readthedocs.io/it/latest/_docs/Capitolo7.html#il-numero-avviso-e-larchivio-dei-pagamenti-in-attesa>`_ della versione 1.7.0 (marzo 2016)
delle "Specifiche Attuative del Nodo dei Pagamenti-SPC" Allegato B alle
Linee guida (di seguito SANP).

La presente versione tiene inoltre conto delle modifiche apportate
all'articolo 5 del Codice dell'Amministrazione Digitale dal decreto
legislativo 13 dicembre 2017, n. 217.

Per facilitare il compito del lettore, le variazioni rilevanti apportate
a capitoli, paragrafi, sotto paragrafi (nel seguito parte o parti di
testo) presenti nella precedente versione 1.2.1, sono segnalate
graficamente come segue:

+-----------------------------------+-----------------------------------+
| |image5|                          | Indica la nuova parte di testo    |
|                                   | inserita.                         |
|                                   |                                   |
|                                   | Si tenga presente che, se anche   |
|                                   | non contrassegnati, tutti i sotto |
|                                   | paragrafi facenti parte della     |
|                                   | nuova parte di testo sono da      |
|                                   | considerare innovazioni.          |
+-----------------------------------+-----------------------------------+
| |image6|                          | Indica che le nuove parti di      |
|                                   | testo hanno integralmente         |
|                                   | sostituito dal testo del nuovo    |
|                                   | paragrafo.                        |
|                                   |                                   |
|                                   | Si tenga presente che, se anche   |
|                                   | non contrassegnati, tutti i sotto |
|                                   | paragrafi facenti parte della     |
|                                   | parte di testo che innova sono da |
|                                   | considerare innovazioni.          |
+-----------------------------------+-----------------------------------+
| |image7|                          | Indica che la parte di testo      |
|                                   | contiene delle modifiche          |
|                                   | funzionali e/o tecniche.          |
+-----------------------------------+-----------------------------------+
|                                   | Si tenga presente che il testo    |
|                                   | impattato dalla modifica è        |
|                                   | evidenziato da una barra          |
|                                   | verticale come quella a fianco    |
|                                   | rappresentata.                    |
+-----------------------------------+-----------------------------------+
| |image8|                          | Indica che la parte di testo      |
|                                   | contiene delle precisazioni       |
|                                   | funzionali e/o tecniche.          |
+-----------------------------------+-----------------------------------+
|                                   | Si tenga presente che il testo    |
|                                   | impattato dalla precisazione è    |
|                                   | evidenziato da una barra          |
|                                   | verticale come quella a fianco    |
|                                   | rappresentata.                    |
+-----------------------------------+-----------------------------------+

.. |pagoPA_logo| image:: media/header.png
.. |image5| image:: media/image4.png
   :width: 0.7874in
   :height: 0.24059in
.. |image6| image:: media/image5.png
   :width: 0.7874in
   :height: 0.2428in
.. |image7| image:: media/image6.png
   :width: 0.7874in
   :height: 0.22651in
.. |image8| image:: media/image7.png
   :width: 0.7874in
   :height: 0.22905in
