# Workflow - Image tagging
## Software
- [DigiKam](https://www.digikam.org/)
- [Total Commander](https://www.ghisler.com/)
- CamtrapR Package

## Import
 - Raw Data from Stick to
	-  ext. HDD/Raw Data as Backup
	 - int. HDD/Inbox as Work Directory

## Assess
### group frames  
- _grouping works as long filename is numerals only_
- group by timelapse/burst
- Reconyx writes EXIF-Data
> Would like to group all at once, but silent fail on my laptop, so per folder

### mark screened group frames
for post hoc review
 - in digiKam settings set write metadata for group = FALSE  
 - select all Group-Frames
 - label __yellow - pending__
 - in digiKam settings reset write metadata for group = TRUE

### adjust grouping
if you use camtraR you don't need to to this step
*start tagging "Rest" at this point*

- < 5 Min. difference = same event
> 	found no option in DigiKam for that, so do manually 	
- choose convenient group frames for tagging
- objects from different directions = different events

### view and tag
- in digiKam settings check or set write metadata for group = TRUE
- Tag structure:
	- Sichtung
        - *Auswahl*
        - Rest
        - Sonstiges
        - *unklar*
        - Stoerung
            - Fahrzeug
            - Hund
            - Mensch
        - Wildtier
            - Dachs
            - Fuchs
            - Hase
            - *Katze*
            - Marder
            - Pferd
            - Reh
            - Rotwild
            - Waschbaer
            - Wildschwein
            - *Wolf*

#### Scan | Glimpse Method
- Filter auf "Bilder ohne Stichwörter"  
- Metadaten schreiben für ganze Gruppe einstellen  
- Erster Durchlauf  
    - alle in den Gruppenbildern erkennbaren "Störungen" markieren  
- Zweiter Durchlauf  
    - *schnelle Option - alle in den Gruppenbildern erkennbaren Wildtiere auszeichnen*  
    - Gruppen aufklappen
	    - alle Bilder auswählen, mit *Fahne Gelb - betrachtet* markieren
	    - alle jetzt erkennbaren Störungen markieren
- Dritter Durchlauf  
	- unklare Bilder und speziell gesuchte Arten markieren
		- ggf. Einzelbildansicht
  - Vierter Durchlauf
	  - alle verbleibenden Bilder sind "Wildtiere" und werden gesammelt markiert
	  - Nebenbei die erkannten Arten und weitere Bemerkungen in die Tabelle schreiben

### note in spreadsheet
- alle Gruppen in den Ordnern schließen
- Filter setzen
	- Reiter "Filter" > Rechtsklick >Wildtiere > auswählen > *untergeordnete Stichwörter*

- Alle Bilder eines Ordners entweder ab- oder auswählen
- Unten links Zahl ablesen = Anzahl Events
	- In Tabelle eintragen
- Wiederholen für alle Filtergruppen

## Export
### new Method
- Menubar
	- "include Album Sub-Tree"
	- "separate Items => by Folder"
		- so werden alle Kameraordner einer Auslesung im selben Fenster angezeigt
- Set Filter to all for export
	- select all
- Export to Local Storage
	- Export to local Storage
		- export to "report"-Folder
			- copy files
			- activate => Use the album path of the items in the target
				- to keep folder structure
- Rename, and credit write via Batch Queue Manager
	- Naming:
	``` Namensschema
	LFU_[dir]_[db:TagsList]_[date:"ddMMyyyy"]{unique}{unique}
	# {unique}{unique} so first frame of Series is "_1" instead of "_"
	```
 - File images
	 - create folders for categories
		 - Katze
		 - Wolf
		 - Sonstiges
	 - file images accordingly

### Auswertung erstellen und teilen
- Verzeichnis in Nextcloud erstellen
	- Freigabelink für noch leeres Verzeichnis erstellen
		- in Mail kopieren
	- dann Daten in den Ordner kopieren
	-  aktuelle Kalenderwoche in **Tabelle** filtern und als **PDF** zu den Bildern Exportieren

> wenn ich das Verzeichnis direkt kopiere, synchronisiert Nextcloud unpraktisch

## Report
- export PDF 
- upload files
	- Output
	- Spreadsheet
- create folder share
- send mail/report
