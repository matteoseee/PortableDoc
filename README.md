# PortableDOC (HTML singolo)



Un editor di testo contenuto in un solo file HTML: nessuna dipendenza, nessuna installazione, nessuna connessione a internet. Si apre con un doppio clic nel browser e i dati restano sempre sul tuo computer.



Interfaccia chiara su sfondo bianco, con icone SVG leggere.



Scrivi da zero oppure usa Apri per caricare un file .txt o .docx.



Non serve un server: funziona anche da file://.


## **Come funziona, in breve**

Editing: un elemento contenteditable con i comandi nativi del browser.

Impaginazione: dopo ogni modifica i paragrafi vengono misurati e spinti alla pagina successiva quando superano il margine inferiore. Intestazione, piè di pagina e numeri sono livelli sovrapposti.

Lettura DOCX: archivio ZIP decompresso con DecompressionStream, poi lettura dell'XML con DOMParser.

Scrittura DOCX: generazione dell'XML e archivio ZIP costruito a mano (senza compressione), senza librerie.

PDF: stampa del browser con @page impostato sul formato scelto.



## **Contribuire**



Segnalazioni e proposte sono benvenute tramite Issues e Pull Request. Per mantenere il progetto semplice, ogni modifica dovrebbe restare in un unico file e non introdurre dipendenze esterne.



## Funzioni

* Testo
* Stili paragrafo: Normale e Titolo 1-5
* Carattere e dimensione (pt)
* Grassetto, corsivo, sottolineato
* Colore del testo ed evidenziatore
* Allineamento: sinistra, centro, destra, giustificato
* Elenchi puntati e numerati
* Rimozione della formattazione, annulla e ripeti
* Paragrafo e pagina
* Margini superiore, inferiore, sinistro e destro in cm
* Interlinea e spazio dopo il paragrafo
* Rientro a sinistra e rientro della prima riga
* Formato pagina: A4, A3, A5, Letter, Legal, in verticale o orizzontale
* Impaginazione automatica: il testo passa alla pagina successiva al raggiungimento del margine inferiore
* Intestazione, piè di pagina e numeri di pagina
* Intestazione e piè di pagina modificabili e ripetuti su ogni pagina
* Numeri di pagina attivabili o disattivabili
* Scelta della pagina da cui far comparire i numeri
* Scelta del numero da cui partire
* Titoli e sommario
* Numerazione multilivello dei titoli (1, 1.1, 1.1.1, ...)
* Sommario automatico con titoli e numeri di pagina, aggiornato mentre si scrive
* Immagini
* Inserimento di una o più immagini (PNG, JPEG e altri formati, convertiti quando serve)
* Ridimensionamento trascinando il punto di controllo o impostando la larghezza in pixel
* Posizione: in linea con il testo, a sinistra, a destra o centrata
* Importazione ed esportazione file



## **Import ed export file supportati**

Formato	Importa	Esporta	Note

\- TXT	sì	sì	Solo testo. Disattivato se il documento contiene immagini

\- DOCX	sì	sì	Stili, colori, margini, formato pagina, intestazione, piè di pagina e immagini

\- PDF	no	sì	Tramite stampa del browser (Salva come PDF)



NB: Il PDF viene generato dalla finestra di stampa del browser, che riproduce le pagine così come le vedi nell'editor.





## **Limiti noti**

DOCX: gli elenchi sono esportati come testo con «•» o numeri. Le immagini sono sempre inserite in linea, anche se nell'editor sono affiancate al testo. Il sommario è esportato come testo statico, non come sommario automatico di Word.

Numerazione DOCX: se i numeri di pagina partono da una pagina diversa dalla prima, Word potrebbe aggiornare il campo solo dopo F9.

Impaginazione: Word calcola le pagine con i propri font, quindi le interruzioni di pagina nel DOCX possono cadere in punti leggermente diversi dall'editor.

Paragrafi lunghi: un paragrafo che non entra nello spazio rimasto passa intero alla pagina successiva, lasciando un po' di spazio vuoto.

Formati in ingresso: i file .doc (Word 97-2003) non sono supportati. Salvali prima come .docx.

File DOCX complessi: tabelle annidate, caselle di testo, forme, note e campi non sono importati.

Lettura DOCX: richiede un browser con supporto a DecompressionStream.



## **Compatibilità**

Browser	Versione minima

Chrome / Edge	80

Firefox	113

Safari	16.4



## **Privacy**

Tutto avviene nel browser. Il file non contiene richieste di rete e nessun contenuto viene inviato a server esterni.



## **Struttura del progetto**

\# l'intera applicazione (HTML + CSS + JavaScript)



Enjoy

