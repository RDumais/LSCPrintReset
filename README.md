# LSCPrintReset
![alt text](https://github.com/RDumais/LSCPrintReset/blob/master/img/zebralogo2.png)
An Electron based printer count resetter for Zebra printers within Linemaster Switch Corporation.

**The Issue:**

Due to standards at Linemaster, Zebra printers need to be serviced and cleaned by an IT member every x amount of inches printed. After the set amount of inches has been printed our monitoring system, What's Up Gold 2017, will use SNMP to create a helpdesk ticket requiring the printer to be serviced. Within the helpdesk ticket we include all the information of the printer configuration including the print count, from the printer's web page. After the printer is serviced, we reset the print count to 0.

The issue itself is not a big deal, but the way we handled the issue was suboptimal.
The typical process went as so:

1) Printer count reaches 6,000 inches.
2) What's Up Gold detects the printer reached the limit and submits a helpdesk ticket.
3) IT member picks up the ticket and services the printer
4) IT member grabs the configuration text from the printer's web page and records the configuration text in the helpdesk ticket.
5) IT member runs a batch file to reset the printer count
6) IT member, again, grabs the new configuration text from the printer's web page and records new configuration text in the helpdesk ticket. This time it should read zero.
7) IT member provides the basic 'Cleaned Zebra Printer per Manufacturer's Manual' ticket solution text.
8) IT member closes the ticket.

**The solution:**

The solution was created to reduce the amount of time navigating to the printer's webpage, copying the configuration text, and typing solution text into the helpdesk ticket. The traditional method of running the batch files also caused confusion due to bad naming conventions. This program will provide a GUI interface that will allow the user to grab the configuration text from the webpage and copy the text to the clipboard with a push of the button. The GUI also allows the user to run the batch file and navigate to the printer's webpage (if needed) with other controls.

**Screenshots:**
The program's main screen:
![alt text](https://github.com/RDumais/LSCPrintReset/blob/master/img/Screenshot.png)

The program's instruction modal:
![alt text](https://github.com/RDumais/LSCPrintReset/blob/master/img/Screenshot2.png)