# *Inadvertant Poison*
## *(Documentation for Python v3)*

### *¡Warning!*
On my computer, the simple act of loading [“3_new.odt”](/3_new.odt) into Libreoffice causes the entire desktop computer, after a couple of seconds to think about it, to lockup & become unresponsive to anything other than the OFF power button on the case. YMMV

The intention of these documents is ultimately to act as a reference for a Bug Report to Libreoffice (LO). The point for me is that, whilst I have unearthed numerous bugs in LO whilst using it to produce these documents, I have zero idea as to why any of those bugs — both minor & show-stopping — exist. It is entirely possible that I've done something stupid whilst producing the PDFs that has caused those bugs, though I am unaware of what that could be if so. In addition, now that I cannot any longer load the ODT it is impossible for me to document the bug(s). So, here are the raw documents so that others with better tools than me can find them.

Versions
These are my current LO + OS versions:
(indent)
LibreOffice 7.4.7.2 40(Build:2)
$ lsb_release -ds => "Devuan GNU/Linux 5 (daedalus)"
$ uname -srm => Linux 6.1.0-27-amd64 x86_64

Timeline
Here is a timeline of production of each of these documents, and how they are linked to each other.

August 2024: ‘0_ProgrammingInPython3.pdf’ obtained at https:// cs.smu.ca/~porter/csc/227/ProgrammingInPython3.pdf
             Note: The ProgrammingInPython3 PDF is chock-a-block with internal + external links, but none of those links are active. As I had a little time, I resolved to add those links into the PDF.
             ‘ProgrammingInPython3.txt’ obtained from ‘0_ProgrammingInPython3.pdf’ using ‘pdftotext’
             Work began to convert ProgrammingInPython3.txt into ‘1_Programming-In-Python3.odt’ and thus into ‘1_Programming-In-Python3.pdf’. It was during this work that most of the PNG files within /Images were obtained. It was also during this work that most of the TXT files within /Texts were obtained using tesseract upon the PNG files.
17 Oct 2024: Conversion work crashed & burned *after* I saved the document at p586 (“Summary”, final chapter).
             (I believe that I was in process of creating “Epilogue” + “Selected Bibliography” when the program just froze [NOT a system freeze] but made no notes & cannot now recall precise details)
             Work began to convert ‘1_Programming-In-Python3.odt’ into ‘2_scratch.odt’ and thus into ‘2_scratch.pdf’
19 Oct 2024: Conversion work crashed & burned *after* completing all chapters (including “Epilogue” + “Selected Bibliography” but not the Index) and whilst preparing the Contents listing.
             (I was beginning to pull my hair out at this stage. Almost all work had been completed. I had zero idea why I should be experiencing problems & therefore no idea as to how to fix it. One feature of the work that I was inexperienced with was integration of drawing elements (eg arrows) with Tables (Figure 12.1 on p474 of ‘2_scratch.pdf’ is an example; Figure 15.1 on p565 is another). I resolved to convert all these draw examples into PNG images & try one more time.
             Work began to convert ‘2_scratch.odt’ into ‘3_new.odt’ and thus into ‘3_new.pdf’
             (After changing all problematic draw-elements on each page into PNG images, I was then able to produce the “Contents at a Glance” (p3 of ‘0_ProgrammingInPython3.pdf’) without any problems. It seemed to me that I should produce a “List of Tables, Sidebars + Figures” first, then a Contents listing, and finally add a “Contents at a Glance” page. The last act would be to correct the jump targets for all forward-jump boxes + correct all Chapter links in the text. The first part (Tables listing) went without problems. However, after completing that LO simply refused to produce any Contents, though without any error message.
25 Oct 2024: (the day before my 75th birthday) My entire computer crashed & burned as I loaded up ‘3_new.odt’ to try (yet again) to produce a Contents listing. In a state of disbelief I shut the computer down via the physical power button. Devuan successfully restored the Journal on restart. In a state of some shock — I was used to this with Windows, but thought that I had left it all behind with Linux — I tried again with nothing else loaded. Just a second or two after loading up ‘3_new.odt’ the mouse stopped moving & everything froze. I got to the command line with Ctrl-Alt-F1, logged in & entered ‘startx’ to get back to the desktop then shut down normally. My final act was to use “libreoffice --convert-to pdf:writer_pdf_Export 3_new.odt” in a terminal to get a PDF (which was successful).
