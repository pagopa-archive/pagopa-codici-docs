
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

.. _riversamento-agli-enti-creditori:

6. Riversamento agli enti creditori |image4|
-----------------------------------

Fermo restando quanto indicato :ref:`al paragrafo 4.1 <giornata-operativa-ed-invio-del-sepa-credit-transfer>`, 
in coerenza con gli articoli 15 e 20 del D. lgs n. 11/2010, per le operazioni di pagamento
disposte attraverso il Nodo dei Pagamenti-SPC di cui alle 
**“Specifiche attuative del Nodo dei Pagamenti-SPC”** (allegato B alle Linee guida),
il PSP del pagatore ha facoltà di effettuare il riversamento delle somme
incassate in modalità cumulativa per Ente Creditore beneficiario.

Il relativo accredito (SCT) deve riportare nel dato “*Unstructured
Remittance Information*” (attributo AT-05, cfr. *SEPA Credit Transfert
Scheme Rulebook*) le seguenti informazioni, articolate secondo la già
utilizzata strutturazione raccomandata dalla EACT:

**/PUR/<purpose>/URI/< identificativoFlusso >** 

Dove:

“**/PUR/**” e “**/URI/**” sono costanti (*tag*) definite dallo standard EACT,
<**purpose**> rappresenta la codifica dello ‘scopo’ (PURpose) del
SCT, e deve riportare il valore prefissato **LGPE-RIVERSAMENTO**

**< idFlusso >** specifica il dato relativo all’informazione
identificativoFlusso presente nel flusso di rendicontazione
descritto nel successivo :ref:`capitolo 7 <flusso-di-rendicontazione>`.

Qualora, al momento della predisposizione del flusso di rendicontazione,
il prestatore di servizi di pagamento non disponga del TRN (attributo
AT-43 Originator Bank’s reference number) del SEPA Credit Transfer
relativo al flusso di cui sopra, dovrà indicare nel dato
“*EndToEndId”* (attributo AT-41 Originator’s Reference), lo stesso
identico valore che è stato in precedenza indicato nel dato
identificativoUnivocoRiscossione del flusso di rendicontazione 
(vedi Tabella 4 a pagina 23).

Per quanto riguarda le modalità di gestione del rifiuto del SCT
(messaggio di REJECT) da parte della banca dell’Ente Creditore, 
:ref:`si faccia riferimento al § 4.3 <rifiuto-del-sepa-credit-transfer>`.

Per quanto riguarda il riversamento relativo ai pagamenti riguardanti la
Marca da bollo digitale, per i quali non è necessario effettuare alcun
riversamento, si rimanda a quanto :ref:`indicato al § 5.1 <specificità-per-il-pagamento-della-marca-da-bollo-digitale>`.


.. |pagoPA_logo| image:: media/header.png
.. |image4| image:: media/image7.png
   :width: 0.7874in
   :height: 0.22905in
