
|pagoPA_logo|

+---------------------------------------------------------------------------------------------------+
| **SPECIFICHE ATTUATIVE DEI CODICI IDENTIFICATIVI DI VERSAMENTO, RIVERSAMENTO E RENDICONTAZIONE**  |
|                                                                                                   |
|                                                                                                   |
| *Allegato A alle "Linee guida per l'effettuazione dei pagamenti elettronici a favore delle*       |
| *pubbliche amministrazioni e dei gestori di pubblici servizi"*                                    |
|                                                                                                   |
|                                                                                                   |
| **Versione 1.4.0 - ottobre 2021**                                                                 |
+---------------------------------------------------------------------------------------------------+

.. _APPENDICE1:

**APPENDICE 1 - CREDITOR REFERENCE - STANDARD ISO 11649:2009**
==============================================================

Secondo lo standard ISO 11649:2009 il *Creditor Reference* è un
costrutto alfanumerico [10]_ lungo al massimo 25 caratteri, così
composto:

**< identifier > < check digits > < reference >**

All’inizio della struttura è posizionata la costante “**RF**”
(identifier), di seguito sono presenti due numeri (check digits), mentre
la parte rimanente (reference) può essere lunga sino ad un massimo di 21
caratteri, il cui contenuto può essere strutturato senza alcuna
restrizione nell’ambito del dominio alfanumerico.

Il componente check digits ha lo scopo di verificare che il componente
*reference* sia stata correttamente impostata e viene calcolata secondo
l’algoritmo ISO/IEC 7064.

Per una informativa più esaustiva possono essere consultati anche i
seguiti link:

`http://www.iso.org/iso/catalogue_detail.htm?csnumber=50649 <http://www.iso.org/iso/catalogue_detail.htm?csnumber=50649>`__

`http://www.jknc.eu <http://www.jknc.eu/>`__

Calcolo dei check digits del Creditor reference

.. csv-table:: 
   :header: Carattere,Val,ASCII,Carattere,Val,ASCII,Carattere,Val,ASCII,Carattere,Val,ASCII

	**0**,0,48,**G**,16,71,**W**,32,87,**m**,22,109
	**1**,1,49,**H**,17,72,**X**,33,88,**n**,23,110
	**2**,2,50,**I**,18,73,**Y**,34,89,**o**,24,111
	**3**,3,51,**J**,19,74,**Z**,35,90,**p**,25,112
	**4**,4,52,**K**,20,75,**a**,10,97,**q**,26,113
	**5**,5,53,**L**,21,76,**b**,11,98,**r**,27,114
	**6**,6,54,**M**,22,77,**c**,12,99,**s**,28,115
	**7**,7,55,**N**,23,78,**d**,13,100,**t**,29,116
	**8**,8,56,**O**,24,79,**e**,14,101,**u**,30,117
	**9**,9,57,**P**,25,80,**f**,15,102,**v**,31,118
	**A**,10,65,**Q**,26,81,**g**,16,103,**w**,32,119
	**B**,11,66,**R**,27,82,**h**,17,104,**x**,33,120
	**C**,12,67,**S**,28,83,**i**,18,105,**y**,34,121
	**D**,13,68,**T**,29,84,**j**,19,106,**z**,35,122
	**E**,14,69,**U**,30,85,**k**,20,107,,,
	**F**,15,70,**V**,31,86,**l**,21,108,,,

**Tabella** **5 - Valori per la conversione dei caratteri**

Tutti valori della stringa di caratteri reference sono convertiti
sequenzialmente, uno ad uno, in numeri applicando il valore presente
nell’omonima colonna con riferimento a quello presente nella colonna
“carattere” della **Tabella 5**.

Ad esempio, il carattere avente la lettera minuscola “w” viene
convertito con il valore 32, mentre il carattere numerico 9 viene
lasciato inalterato, pertanto la stringa **w9** viene convertita nella
stringa numerica **329**.

Una volta convertito tutto il dato reference si aggiunge alla stringa
numerica così ottenuta il valore **2715** (conversione di **RF**) ed il
valore fisso **00**; alla stringa risultante si applica l’algoritmo di
calcolo ISO/IEC 7064 (vedi paragrafo successivo).

Continuando l’esempio precedente, la stringa derivante sarà pertanto
**329271500**.

Di conseguenza, applicando l’algoritmo di calcolo sopra indicato alla
stringa **w9**, il risultato del calcolo del check digit è **45**.

Il *Creditor Reference* risultante è quindi **RF45w9**.

Algoritmo di Calcolo ISO/IEC 7064

L’algoritmo di calcolo è lo stesso usato per il determinare i check
digits del codice IBAN per quanto riguarda gli identificativi
strutturati dei conti correnti bancari.

L’algoritmo per il calcolo dei check digits che si applica alla stringa
numerica risultante dal processo di conversione è il seguente:

1. Calcolare il resto della divisione per 97 (modulo 97) di detto
   numero,

2. Sottrarre il risultato ottenuto da 98;

3. Se tale valore è maggiore o uguale a 10, il dato check digits è il
   valore ottenuto al punto 2, altrimenti anteporre uno zero
   (esempio: se il risultato è 4, il valore del check digits è 04).

FINE DOCUMENTO

.. [10]
   L'insieme delle lettere dell'alfabeto latino e dei numeri arabi. Appartengono a quest'insieme 
   le lettere minuscole dalla a alla z, le maiuscole dalla A alla Z e i numeri da 0 a 9


.. |pagoPA_logo| image:: media/header.png
   :width: 5.90551in
   :height: 1.30277in
   
