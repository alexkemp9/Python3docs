# *Source Docs for Bug-Hunting*
## *(original: Documentation for Python v3)*

### *Warning!*
In Sept 2024 the simple act of loading [“3_new.odt”](/3_new.odt) into Libreoffice caused the entire desktop computer to lockup & become unresponsive to anything other than the OFF power button on the case. Without any further action from me towards the ODT that has now, in Nov 2024, moderated into a LibreOffice freeze when the ODT is loaded, but not a System Freeze. YMMV     

The above was all under LibreOffice v7.4.7.2.
  * On [Nov 06](#appimage-installation) an AppImage v24.8.2.1 install (updated to v24.8.3.2 on Nov 14) allowed temporary access to the ODT.
  * On [Nov 09](#09-nov-2024) the AppImage v7.2.3.2 finally gave error-free access to all ODTs.

***Dec 06 Update:*** Whilst attempting to compile the [tabulation of files + Chapter / Header Numbering](#2024-dec-06) my Devuan system locked up solid immediately after loading *4_paragraph-fix.odt*, and I had to use `Ctrl-Alt-F1` yet again to escape; this was under v7.2.3.2 Libreoffice. I cannot fathom this bug (or set of bugs, whatever it is). It's behaviour changes from day to day.

Note that my Devuan is currently Linux 5 daedalus, based on Debian stable, kernel 6.11.5+bpo-amd64 + fully updated each day.

It was still as buggy as can be under the 24.8.2 AppImage: the Status Bar Page-stats kept varying, as did the final page number. In addition, *Figure 15.1* kept intruding into the last pages, then was displayed within multiple other pages (the only action from me was to switch view to the last two pages). Fig 15.1 is shown on p563 of [“3_new.pdf”](/3_new.pdf), and that is completely wrong. It is not where it is supposed to be, nor where I placed it. Yet another bug.

**7 Nov update:** The 24.8.2 AppImage version of Libreoffice has proven to be almost identical to the 7.4.7 version. After about 2 minutes the whole of LibreOffice dies & goes stiff. The only thing that I can do is to force-close the window. Not good.

### Index:
| The Files (1<sup>st</sup> Attempt at Production) | Information Link |
| --- | --- |
|[0_ProgrammingInPython3.pdf](/0_ProgrammingInPython3.pdf)|[August 2024](#2024-august-00)|
|[ProgrammingInPython3.txt](Texts/ProgrammingInPython3.txt)|[August 2024 #1](#2024-august-01)|
|[1_Programming-In-Python3.odt](/1_Programming-In-Python3.odt)|[August 2024 #2](#2024-august-02)|
|[1_Programming-In-Python3.pdf](/1_Programming-In-Python3.pdf)|[August 2024 #2](#2024-august-02)|
|[2_scratch.odt](/2_scratch.odt)|[Oct 17 2024](#2024-oct-17)|
|[2_scratch.pdf](/2_scratch.pdf)|[Oct 17 2024](#2024-oct-17)|
|[3_new.odt](/3_new.odt)|[Oct 19 2024](#2024-oct-19)|
|[3_new.pdf](/3_new.pdf)|[Oct 19 2024](#2024-oct-19)|
|[4_paragraph-fix.odt](/4_paragraph-fix.odt)|[Nov 09 2024](#2024-nov-09)|
| (2<sup>nd</sup> Attempt) |   |
|[2_paragraph-fixes.odt](/2_paragraph-fixes.odt)|[Nov 20 2024](#2024-nov-20)|
| (3<sup>rd</sup> Attempt) |   |
|[chapter_00.odt](/chapter_00.odt) (etc. re: Master Documents)|[Nov 27 2024](#2024-nov-27)|
|Chapter / Heading Number Errors|[Dec 06 2024](#2024-dec-06)|
|Copy Errors|[Dec 07 2024](#2024-dec-07)|
|Frame Stats|[Dec 08 2024](#2024-dec-08)|

### *Intentions*
The original intention of these documents was to show off how wonderful my updates to the Python3 PDF were. What it has actually become is a reference for Bug Reports to Libreoffice (LO).

When it became impossible to load the ODTs it was not possible to document the bug(s). So, in that situation I thought that access to the raw documents would help others with better tools than me to find those bugs.

### *Versions*
These are my current LO + OS versions:
- LibreOffice 7.4.7.2 40(Build:2)
- `$ lsb_release -ds` => “Devuan GNU/Linux 5 (daedalus)”
- `$ uname -srm` => “Linux 6.1.0-27-amd64 x86_64”

Under AppImage (installed 6 November 2024):
- LibreOffice 24.8.2.1

### *AppImage Installation*
The installation was done in a Terminal. Thus, what is shown below is at a user command-line:
```
$ cd /usr/local/bin
$ sudo wget https://appimages.libreitalia.org/LibreOffice-fresh.standard-x86_64.AppImage
$ sudo mv LibreOffice-fresh.standard-x86_64.AppImage LibreOffice-24.8.AppImage
$ sudo chmod a+x LibreOffice-24.8.AppImage
$ LibreOffice-24.8.AppImage --help
  LibreOffice 24.8.2.1 0f794b6e29741098670a3b95d60478a65d05ef13
$ sudo cp /usr/share/applications/libreoffice-startcenter.desktop /usr/share/applications/loappimage-startcenter.desktop
$ sudo nano /usr/share/applications/loappimage-startcenter.desktop
  # I changed the .desktop name + all Exec lines to begin “/usr/local/bin/LibreOffice-24.8.AppImage”,
  # but pretty much everything else was left unchanged
```
The new launch link was immediately within `menu:Office | LO AppImage Start Centre` & showed the correct LO version.

On Nov 14 the 24.8 AppImage was updated + the dir re-organised, in part using hard-links (`cp -l`). This is how the relevant files looked afterwards:-
```
$ la /usr/local/bin
total 927764
-rwxr-xr-x 2 root  root  334357696 Nov 14 12:47 LibreOffice-24.8.3.2.standard-x86_64.AppImage
-rwxr-xr-x 2 root  root  334357696 Nov 14 12:47 lo-24.8.AppImage
-rwxr-xr-x 1 root  root  280609984 May 22  2024 lo-7.2.AppImage
```


## *Timeline*
Here is a timeline of production of each of these documents, and how they are linked to each other.
<a name="2024-august-00"></a>
### August 2024:
* [‘0_ProgrammingInPython3.pdf’](/0_ProgrammingInPython3.pdf) obtained at `https://cs.smu.ca/~porter/csc/227/ProgrammingInPython3.pdf`     
  (I wanted to learn Python 3)     
> Note:
<a name="2024-august-01"></a>
> The ProgrammingInPython3 PDF is chock-a-block with internal + external links, but none of those links are active. As I had a little time, I resolved to add those links into the PDF.
>
* [‘ProgrammingInPython3.txt’](Texts/ProgrammingInPython3.txt) obtained from [‘0_ProgrammingInPython3.pdf’](/0_ProgrammingInPython3.pdf) using `pdftotext`
>
<a name="2024-august-02"></a>
* Work began to convert [ProgrammingInPython3.txt](Texts/ProgrammingInPython3.txt) into [‘1_Programming-In-Python3.odt’](/1_Programming-In-Python3.odt) and thus into [‘1_Programming-In-Python3.pdf’](/1_Programming-In-Python3.pdf).
> It was during this work that most of the PNG files within [/Images](/Images) were obtained. It was also during this work that most of the TXT files within [/Texts](/Texts) were obtained using `tesseract` upon the PNG files.
### 17 Oct 2024:
* Conversion work crashed & burned *after* I saved [‘1_Programming-In-Python3.pdf’](/1_Programming-In-Python3.pdf) (see p586 (“Summary”, final chapter)).
>Note:
> I believe that I was in process of creating “Epilogue” + “Selected Bibliography” when the program just froze [NOT a system freeze] but made no notes & cannot now recall precise details
>
<a name="2024-oct-17"></a>
* Work then began to convert [‘1_Programming-In-Python3.odt’](/1_Programming-In-Python3.odt) into [‘2_scratch.odt’](/2_scratch.odt) and thus into [‘2_scratch.pdf’](2_scratch.pdf)
### 19 Oct 2024:
* Conversion work crashed & burned *after* completing all chapters (including “Epilogue” + “Selected Bibliography” but not the Index) and whilst preparing the Contents listing.
>Note:
> I was beginning to pull my hair out at this stage. Almost all work had been completed. I had zero idea why I should be experiencing problems & therefore no idea as to how to fix it.
>
> One feature of the work that I was inexperienced with was integration of drawing elements (eg arrows) with Tables (Figure 12.1 on p474 of [2_scratch.pdf](2_scratch.pdf) is an example; Figure 15.1 on p565 is another).
>
> I resolved to convert all these draw examples into PNG images & try one more time.
>
<a name="2024-oct-19"></a>
* Work began to convert [‘2_scratch.odt’](/2_scratch.odt) into [‘3_new.odt’](/3_new.odt) and thus into [‘3_new.pdf’](3_new.pdf)
>
> After changing all problematic draw-elements on each page into PNG images, I was then able to produce the “Contents at a Glance” (p3 of [‘0_ProgrammingInPython3.pdf’](/0_ProgrammingInPython3.pdf)) without any problems. It seemed to me that I should produce a “List of Tables, Sidebars + Figures” first, then a Contents listing, and finally add a “Contents at a Glance” page. The last act would be to correct the jump targets for all forward-jump boxes + correct all Chapter links in the text. The first part (Tables listing) went without problems. However, after completing that LO simply refused to produce any Contents, though without any error message.
### 25 Oct 2024:
* (the day before my 75th birthday) My entire computer crashed & burned as I loaded up [‘3_new.odt’](/3_new.odt) to try (yet again) to produce a Contents listing. In a state of disbelief I shut the computer down via the physical power button. Devuan successfully auto-restored the Journal on restart. In a state of some shock — I was used to this with Windows, but thought that I had left it all behind with Linux — I tried again with nothing else loaded. Just a second or two after loading up ‘3_new.odt’ the mouse stopped moving & everything froze. I got to the command line with `Ctrl-Alt-F1`, logged in & entered `startx` to get back to the desktop then shut down normally.
* My final act on this occasion  was to use `libreoffice --convert-to pdf:writer_pdf_Export 3_new.odt` in a terminal to get a PDF (which was successful).
 ### 09 Nov 2024:
Two significant steps forward on the same day:     
  1. A post by me within the  [dev1galaxy.org forum](https://dev1galaxy.org/viewtopic.php?id=6915) had produced responses that suggested that *ealier* versions of LO could run [“3_new.odt”](/3_new.odt) without freezing nor dying. After installing *"LibreOffice-7.2.3.2.basic-x86_64.AppImage"* from [AppImages listing](https://appimages.libreitalia.org/) I was able to prove that yes, those were accurate reports.
  2. A response to a post by me within [ask.lo.org](https://ask.libreoffice.org/t/re-my-odt-froze-my-computer-i-had-to-press-the-power-button/113458) had stated that my extensive use of *Direct Paragraph Formatting* (sic) rather than *Body Text* was responsible for the increased load, since *“Direct formatting puts stress on Writer because every occurrence must be handled individually whereas style effects can be cached and reused at will”*. Such a design feature appeared to me to be rather stupid but, sure enough, experimentation seemed to show it to be true.

Later Comment on ***“Direct Paragraph Formatting”*** within the [ask.lo.org answer](https://ask.libreoffice.org/t/re-my-odt-froze-my-computer-i-had-to-press-the-power-button/113458):     
    At the time I read *“Direct Paragraph Formatting”* as a mis-type for *“Default Paragraph Style”*. That writer is obsessed with *any* use of direct format by someone asking for help, and immediately uses it as a stick to beat the questioner with. Having re-read the answer, I am now unsure as to whether that writer was referring to *Default Paragraph Style* or not.

This is ***Libreoffice Writer Styles***:–

> * ***Stylesheets:*** LO makes use of *Stylesheets* (similar to html *CSS*), referred to in LO as *“Styles”*. Each is a collection of format settings that all apply within one particular scenario.
> * ***Writer Style Scenarios:*** Page, Paragraph, Character, Frame, List, Table.
> * ***Style Cascade:*** One style within each scenario is the default from which all others in the same scenario are directly or ultimately derived.
> * ***Style Values:*** Less work for the author + a more professional appearance.
> * ***Direct Format:*** It is still possible to directly change any format setting within the page, paragraph, etc..
    
*  [‘3_new.odt’](/3_new.odt) loaded up under 7.2.3.2 & allowed me to operate LO.     
`Ctrl-h` gave Search+Replace. Using "Paragraph Styles" I searched for "Default Paragraph Style" & replaced with "Text Body". (Note: in 24.8.2 "Text Body" style has been renamed to "Body Text").     
  <a name="2024-nov-09"></a>
I changed all 57 Introduction paragraphs in *3_new.odt* from *"Default Paragraph Style"* to *Body Text* and then saved the ODT as  [‘4_paragraph-fix.odt’](/4_paragraph-fix.odt). Opening *4_paragraph-fix.odt* again all the excess load was magically gone. Good Lord.
* The initial magic of *4_paragraph-fix.odt* evapourated almost immediately as I continued with the default-paragraph changes. In addition, the bugs in *3_new.odt* had caused various elements to change position, and all of those needed fixing as well. The excess load issue reappeared the next day & did not go away. This new document was now beginning to show all the same symptoms as the old ones, plus a few new ones of it's own. I resolved to abandon this line of documents and to try anew with one of the original documents.
 ### 20 Nov 2024:
  <a name="2024-nov-20"></a>
* Begininng again with [‘1_Programming-In-Python3.odt’](/1_Programming-In-Python3.odt) under 7.2.3.2 I saved it as [‘2_paragraph-fixes.odt’](/2_paragraph-fixes.odt), and using `Ctrl-h` replaced every instance of 'Default Paragraph Style' with 'Text Body' style + a host of other changes. That enabled me to open the document under 7.4.7 and, after 10 seconds, the load fell to a minimal level. (False dawn; the next day it was back to continual load). This continued though every Chapter, including Epilogue & Bibliography. Next was to create a *Table of Contents*. I went through all the motions to do that, but nothing happened.

## Interim Summary:

1. The first line of construction clearly had hit a brick wall (4 months: *[0_ProgrammingInPython3.pdf](/0_ProgrammingInPython3.pdf)* through to *[4_paragraph-fix.odt](/4_paragraph-fix.odt)*).     
2. The second line of construction had also hit yet another brick wall (11 days: *[‘1_Programming-In-Python3.odt’](/1_Programming-In-Python3.odt)* to *[2_paragraph-fixes.odt](/2_paragraph-fixes.odt)*).     
3. I don't like hitting brick walls. I needed to take another route, so decided to do this via a Master Document instead.
 ### 27 Nov 2024:
  <a name="2024-nov-27"></a>
* The first issue was to produce 18 chapters ([‘chapter_00.odt’](/chapter_00.odt) to  ([‘chapter_15.odt’](/chapter_15.odt) + ([‘Epilogue.odt’](/Epilogue.odt) + ([‘Bibliography.odt’](/Bibliography.odt)) and a Master Document ([‘Programming-In-Python3.odm’](/Programming-In-Python3.odm)). This time I hit the brick wall instantly with Chapter / Heading numbering, but at least I was able to find the fix after a short while. Though not yet (Dec 06) for the same issue in Master Documents.
### Chapter / Heading Numbering
***Bottom Line:***     
It is the order in which `Chapter Numbering…` and `Heading styles` are setup that will decide whether *Chapter Numbering* is switched on or not.
> * *Chapter Numbering…* needs to be setup first
> * *Heading styles* need to be used last
> * (the info above is not in any [documentation](https://help.libreoffice.org/7.4/en-US/text/swriter/01/06060000.html) that I have seen, nor known about by the [experts I consulted](https://ask.libreoffice.org/t/cannot-number-a-chapter-in-a-figure-table-caption-etc/114155/9))
> * Note: LO v7 & earlier call the menu item `menu:/Tools/Chapter Numbering…`.  Below is the dialog:
> * Later versions call the same menu item `menu:/Tools/Heading Numbering…`. Below is Tab#2 of the dialog:
> ![Chapter numbering](/Screenshot_Chapter-numbering.png)     
> ![Heading numbering](/Screenshot_Header-numbering.png)     

I setup all my Header 1, 2, 3 + 4 styles first in each document that I built, and then tried to setup Chapter Numbering (it failed every time, because that was the wrong order - see above). After a while I tried to use *“Drawing”* as a replacement field, but that is not an effective substitute.

Having discovered the undocumented ‘trick’ to be able to switch *Chapter / Heading Numbering* ON I also discovered that doing so inserted the Chapter Number into all Headings at that level when they were created. Why? !!! It may be reasonable as an option, but surely not as a requirement. The *“H1 Auto-number”* Character style that I created was my means to hide that number in the Headings; a 2pt number in DejaVu Sans Condensed with the same #95BFEC font colour as the Heading background does the job there, and does not affect the field use in other circumstances.

Once I had discovered the correct 2-stage order to switch on Chapter / Heading numbering, inserting *“x.y”* *Figure* + *Table* numbers became a breeze (in which x == current Chapter number auto-inserted, and y == *Figure + 1* or *Table + 1* in order to get auto-incrementing numbers. That works fine. Although not yet in Master documents.

Here is a tabulation of the documents re: Chapter numbering; unmentioned files are the same as their predecessor:–
<a name="2024-dec-06"></a>
| Document | Chapter / Heading Numbering |
|:---:|:---: |
| 1_Programming-In-Python3.odt | Inoperative |
| 2_paragraph-fixes.odt | *Drawing* as a substitute field |
| chapter_02.odt | Operative<br>(not operative is Master documents)     
(back-ported into chapter_00 + chapter_01) |
### 07 Dec 2024:
I was dealing with so many different bugs in Writer by this stage that my head was spinning. I was having difficulty both in spotting any common theme between the bugs, and also how on earth could I sensibly & simply report them to others? Then I had a bright thought.

One common theme between the original errors & the Master document errors was transfer from one document to another. The bright thought was that it should be possible to measure that, and measurement is something that everyone at every level can understand.

<a name="2024-dec-07"></a>
In the following tabulation I used the Status bar (bottom left) +  the Writer *Navigator* (switch it on/off with Function Key #5 (`F5`) or `menu:/View/Navigator`) to measure the stats of various components of [1_Programming-In-Python3.odt](/1_Programming-In-Python3.odt) under both LO 7.2.3.2 + 24.8.3.2. The entire document was then selected using both `Ctrl-A` & mechanical selection with mouse (word & character stats were identical in both cases) & copied using `Ctrl-C`. That was then pasted into a new, blank sheet using `Shift-Ctrl-V (select LO doc)` and measured again.
### Copying Errors
| 7.2.3.2 |Original | Copy | Diff | % |
|:---:|---: |---:|---:|---:|
| Pages | 666 | 556 | -110| -17% |
| Words | 232,206 | 226,263 | -5,943 | -2.6%  |
| Words (selection) | 223,631 |  | -2,632 | -1.2% |
| Characters | 1,392,176 | 1,356,358 | -35,818 | -2.6% |
| Chars (selection) | 1,340,553 |  | -15,805 | -1.2% |
| Headings | 241 | 241 |0 | |
| Tables | 105 | 68 | -37 | -35% |
| Frames | 77 | 33 | -44 | -57% |
| Images | 39 | 35 | -4 | -5.2% |
| OLE objects | 3 | 3 | 0 ||
| Bookmarks | 52 | 40 | -12 | -23% |
| Hyperlinks | 114 | 113 | -1 | -0.9% |
| References | 7 | 7 | 0 ||
| Drawing Objects | 689 | 634 | -5 | -0.7% |
| Fields | 262 | 253 | -9 | -3.4% |     
     
      
Almost one fifth of the pages are not transferred on copy/paste?     
     
      
| 24.8.3.2 |Original | Copy | Diff | % | cf v7 |
|:---:|---: |---:|---:|---:|:---:|
| Pages | 664 | 558 | -106| -16% | different |
| Words | 232,206 | 226,263 | -5,943 | -2.6%  | same |
| Words (selection) | 223,631 |  | -2,632 | -1.2% |  same |
| Characters | 1,392,176 | 1,356,358 | -35,818 | -2.6% | same |
| Chars (selection) | 1,340,553 |  | -15,805 | -1.2% | same |
| Headings | 241 | 241 |0 | | same |
| Tables | 105 | 68 | -37 | -35% | same |
| Frames | 77 | 33 | -44 |- 57% | same |
| Images | 39 | 35 | -4 | -5.2% | same |
| OLE objects | 3 | 3 | 0 || same |
| Bookmarks | 52 | 40 | -12 | -23% | same |
| Hyperlinks | 114 | 113 | -1 | -0.9% | same |
| References | 7 | 7 | 0 || same |
| Drawing Objects | 689 | 634 | -5 | -0.7% | same |
| Fields | 240 | 237 | -3 | -1.3% | different |
| Footnotes | 72 | 72 | 0 |  | no comparison |

***Bottom line:*** Both v7 + v24.8 are unable to copy then paste all components of an odt. That is a bad set of bugs.

<a name="2024-dec-08"></a>
Frames had the largest proportion of failures during transfer ( 57%). So, the obvious next step was to try to identify what was causing so many Frame errors during copying. The following stats were collected under 24.8.3.2:
> ✔ == yes, is copied fine     
> ✘ == no, is NOT transferred during copy/paste     
### Frame Stats
| Serial |Page | Name | Image | Table | Sidebar | Drawing Object |
|---:|:---: |:---:|:---:|:---:|:---:|:---:|
|1| p014 |figure 1.1 |✔| | | |
|2| p017 |figure 1.2 |✔| | | |
|3| p033 |figure 1.4 |✔| | | |
|4| p032 |figure 1.3 |✔| | | |
|5| p066 |Table 2.7 | | ✘| | |
|6| p069 |figure 2.1 |✔| | | |
|7| p071 |figure 2.3 |✔| | | |
|8| p070 |figure 2.2 |✔| | | |
|9| p071 |figure 2.4 |✔| | | |
|10| p099 |figure 2.7 |✔| | | |
|11| p116 |Deleting Items… || |✔| |
|12| p122 |figure 3.3 || | |✘|
|13| p123 |figure 3.4 |✔| | | |
|14| p128 |figure 3.5-d3 || | |✔|
|15| p128 |figure 3.5-d2 || | |✔|
|16| p128 |figure 3.5-d1 || | |✔|
|17| p128 |figure 3.5-d6 || | |✔|
|18| p128 |figure 3.5-d4 || | |✔|
|19| p128 |figure 3.5-d5 || | |✔|
|20| p128 |figure 3.5-d7 || | |✔|
|21| p130 |Table 3.3 | | ✘| | |
|22| p132 |Read Write… || |✘| |
|23| p142 |Table 3.4 | | ✘| | |
|24| p166 |figure 4.1 |✔| | | |
|25| p167 |figure 4.2 |✔| | | |
|26| p174 |Online Doc… || |✘| |
|27| p183 |print() Fun… || |✘| |
|28| p239 |figure 6.1 |✔| | | |
|29| p244 |Table 6.1 | | ✘| | |
|30| p251 |Figure 6.3 | | ✘| | |
|31| p252 |Table 6.2 | | ✘| | |
|32| p252 |del_() Spe… || |✔| |
|33| p255 |Table 6.3 | | ✘| | |
|34| p264 |figure 6.6 |✔| | | |
|35| p267 |Table 6.4 | | ✘| | |
|36| p280 |Generator Fun… || |✘| |
|37| p290 |Figure 7.1 | | ✘| | |
|38| p291 |Figure 7.2 | | ✘| | |
|39| p295 |Bytes and Byte… || |✘| |
|40| p298 |Struct Module… || |✘| |
|41| p349 |Table 8.1 | | ✘| | |
|42| p314 |Table 8.2 | | ✘| | |
|43| p379 |Table 8.3 | | ✘| | |
|44| p381 |Table 8.4 | | ✘| | |
|45| p398 |Figure 8.2 | | ✘| | |
|46| p421 |figure 9.2 |✔| | | |
|47| p420 |figure 9.1 |✔| | | |
|48| p437 |Figure 10.1 | | ✘| | |
|49| p440 |figure 10.2 |✔| | | |
|50| p442 |Figure 10.3 | | ✘| | |
|51| p475 |Table 12.1 | | ✘| | |
|52| p476 |Table 12.2 | | ✘| | |
|53| p486 |Table 13.1 | | ✘| | |
|54| p487 |Table 13.2 | | ✘| | |
|55| p492 |Table 13.3 | | ✘| | |
|56| p496 |Table 13.4 | | ✘| | |
|57| p496 |Table 13.5 | | ✘| | |
|58| p502 |Table 13.7 | | ✘| | |
|59| p510 |Figure 14.1 | | ✘| | |
|60| p511 |Figure 14.2 | | ✘| | |
|61| p512 |Figure 14.3 | | ✘| | |
|62| p514 |Figure 14.4 | | ✘| | |
|63| p514 |Figure 14.5 | | ✔| | |
|64| p517 |Figure 14.6 | | ✘| | |
|65| p517 |Figure 14.7 | | ✘| | |
|66| p520 |Figure 14.9 |✘| | | |
|67| p521 |Figure 14.12 | | ✘| | |
|68| p520 |Caption 14.9 |✔| | | |
|69| p520 |Caption 14.11 |✔| | | |
|70| p522 |Figure 14.13 |✘| | | |
|71| p522 |Figure 14.14 |✔| | | |
|72| p543 |Figure 14.15 | | ✘| | |
|73| p565 |Figure 15.1 || | |✔|
|74| p567 |Figure 15.2 |✔| | | |
|75| p573 |Figure 15.4 |✘| | | |
|76| p583 |Figure 15.6 |✔| | | |
|77| p584 |Figure 15.7 | | ✔| | |
|||Totals:| 25 (32%) : 22✔ 3✘ | 35 (45%) : 2✔ 33✘ | 8 (10%) : 2✔ 6✘ | 9 (12%) : 2✔ 7✘ |
### Frames
The [current Libreoffice Help on Frames](https://help.libreoffice.org/latest/en-US/text/swriter/guide/text_frame.html) states:
> A frame is a container for text and graphics that you can place anywhere on a page. You can also use a frame to apply a column layout to text.

A [vital LO Wiki page on Page-Anchoring](https://wiki.documentfoundation.org/Faq/Writer/AnchoringAndPositioning) unambiguously points out that *"(page-anchored) objects present in text documents will disappear from the master documents referencing those text documents”*. Whoops. Well, it would have been nice to have been warned at the point of trying to paste / transfer, rather than just posting a Notice attached to a wall on the other side of the County.

It is obvious from the name that a Frame was originally designed to encapsulate an Image (putting a *“Frame around a Picture”*). In fact, the Wiki linked above states: *“Every image that is inserted into Writer is associated or assigned to the ‘Graphics’ Frame style”*. Also, the act of adding a Caption auto-adds a Frame to the object, with the caption placed within the Frame, either above or below the object.

Checking the non-transfer Images above (all anchored to a Page) + the successfully-transferred Tables above (all anchored to a Paragraph, unlike other Tables) answers why those did / did not transfer.

The *Sidebars* are pure-Frame items that contain text. Once again, the couple that successfully transferred are anchored to a paragraph, whilst the others are all anchored to the page. There is a pattern emerging here.

I did not bother checking the Drawing Objects that were framed. I got disenchanted very early on with the way that they became hobos & wandered all over the pages, and thus converted all of them into PNG files to stop their vagrant manner.

## The Bugs
I wrote down some of the LO Bugs that I was experiencing, but only after the show-stopping bug. Here's my record:

1. Copy + Paste sometimes omits Tables. It seems that only Tables that are NOT encapsulated with a Frame will be copied.

All the bug-issues on Frames have now (Dec 2024) been answered above (see [Frames](#frames). In short, do not anchor a Frame to a page.

2. Selecting the whole of an image caption (eg for rename) also selects the image. If the caption is then deleted the image itself will also be deleted. The 1st letter needs to be de-selected to prevent that.
3. The bottom border of an image-in-frame-with-caption will coelesce with the top inline-border of a paragraph. In other words, the below-paragraph spacing of an image will be added to the internal top-spacing  of the next paragraph, rather than being placed between the two entity’s borders. This can be viewed within [bug3.odt](./bug3.odt).
4. The bottom border of a table-in-frame will coelesce with the top inline-border of a paragraph. In other words, the below-frame spacing of the table-in-frame will be added to the internal top-spacing  of the next paragraph, rather than being placed between the two entity’s borders. This can be viewed within [bug4.odt](./bug4.odt), and is almost certainly a Frame bug rather than a Table bug, and thus a dupe of bug#3.
5. The bottom border of a Sidebar (which is a frame that contains text) will coelesce with the top inline-border of a paragraph. In other words, the below-frame spacing of the frame will be added to the internal top-spacing  of the next paragraph, rather than being placed between the two entity’s borders.  This can be viewed within [bug5.odt](./bug5.odt), and is almost certainly a dupe of bug#3 + bug#4. An example can also be seen on p293 of [‘3_new.pdf’](3_new.pdf).
6. The bottom of an image-in-frame-with-caption will coelesce with the top of a table-in-frame. (I do not have an example of this to show as I went through the entire document re-arranging the text to prevent it occurring; attempting to make an example as with earlier bugs caused Libreoffice to freeze. It is a nightmare).
8. The Jump-Boxes (which are LO TextBoxes) will not allow some keyboard shortcuts, although the menu WILL work. An example is that `menu:Edit | Paste Special | Paste Unformatted Text` DOES work, but `Shift+Ctrl+Alt+V` does NOT work.
9. In contrast to #5, `Ctrl+-` (insert soft Hyphen) DOES work inside a Jump-Box / TextBox, and the word breaks as desired, but no hyphen is inserted at the break. Using the menu is an identical result. Within the document itself this action works as expected. An example can be seen in the jumpbox at #4 (on the LHS of the sidebar on p293 of [‘3_new.pdf’](3_new.pdf), where a soft hyphen has been inserted between 'trans' + 'late'. The word is broken as desired, but no hyphen is inserted (this is fixed in v24.8).

## *Contact*
Send feedback via the [dev1galaxy.org forum](https://dev1galaxy.org/viewtopic.php?id=6915).
