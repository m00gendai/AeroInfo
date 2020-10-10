0. Language
1. Description
2. Overview
3. Features
4. Techniques used
5. Remarks

+------------------------------------------------------------------------------------------------+
| 0. LANGUAGE                                                                                    |
+------------------------------------------------------------------------------------------------+

- Written in Python 3.8
- Only vanilla modules/libraries (user restrictions)
- Developed on IDLE

+------------------------------------------------------------------------------------------------+
| 1. DESCRIPTION                                                                                 |
+------------------------------------------------------------------------------------------------+

Tool used to get detail information of a navaid or airport. 

+------------------------------------------------------------------------------------------------+
| 2. OVERVIEW                                                                                    |
+------------------------------------------------------------------------------------------------+

GUI split into two main rows.

Row 1 fetches navaid information based on input of its designator. Information consists of:
- Navaid name          (eg. Trasadingen)
- Navaid ID            (eg. TRA)
- Navaid type          (eg. VOR/DME)
- Navaid frequency     (eg. 114.300)
- Navaid country       (eg. CH)
- Assosciated airport  (eg. none)

Row 2 fetches airport information based on input of its ICAO designator. Information consists of:
- Airport ICAO designator			  (eg. LSZH)
- Available runways                   (eg. 16/34)
- Available frequencies: Type         (eg. TCA)
- Available frequencies: Description  (eg. Terminal)
- Available frequencies: Frequency    (eg. 127.25)

+------------------------------------------------------------------------------------------------+
| 3. FEATURES                                                                                    |
+------------------------------------------------------------------------------------------------+

- GUI built with tkinter grid layout
- Execution of entry of navaid or airport via button or keyboard press
- Capable of displaying multiple entries
- Hint if no record has been found
- Clearing of text boxes before new query
- Data collection via multiple CSV files
- Source mention with timestamp of CSVs used

+------------------------------------------------------------------------------------------------+
| 4. TECHNIQUES USED                                                                             |
+------------------------------------------------------------------------------------------------+

- Modules used:
  - csv
  - tkinter
  - urllib
  - urllib.request
  - os.path, time
- Two functions handle getting of CSV data
- Rest are tkinter bindings
- Minor format rules to change CSV data (eg. CSV: VOR-DME > Tool: VOR/DME)

+------------------------------------------------------------------------------------------------+
| 5. REMARKS                                                                                     |
+------------------------------------------------------------------------------------------------+

Relies on availability of source files and the constant format thereof. 
Is not official and does not include 100% of all navaids, airports, frequencies etc. 
For the moment can only query by navaid ID/airport ICAO designator, not by name or anything else.

Developed 15 SEP 2020 by Marcel Weber
