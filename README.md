# *Source Docs for Bug-Hunting*
## *(original: Documentation for Python v3)*

### *¡Warning!*
In Sept 2024 the simple act of loading [“3_new.odt”](/3_new.odt) into Libreoffice caused the entire desktop computer to lockup & become unresponsive to anything other than the OFF power button on the case. Without any further action from me towards the ODT that has now, in Nov 2024, moderated into a LibreOffice freeze when the ODT is loaded, but not a System Freeze. YMMV     

The above was all under LibreOffice v7.4.7.2.
  * On [Nov 06](#appimage-installation) an AppImage v24.8.2.1 install (updated to v24.8.3.2 on Nov 14) allowed temporary access to the ODT.
  * On [Nov 09](#09-nov-2024) the AppImage v7.2.3.2 finally gave error-free access to all ODTs.

### Internal Navigation:
| The Files | Information Link |
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

It was still as buggy as can be under the 24.8.2 AppImage: the Status Bar Page-stats kept varying, as did the final page number. In addition, *Figure 15.1* kept intruding into the last pages, then was displayed within multiple other pages (the only action from me was to change to the last two pages). Fig 15.1 is shown on p563 of [“3_new.pdf”](/3_new.pdf), and that is completely wrong. It is not where it is supposed to be, nor where I placed it. Yet another bug.

On my first attempt I tried to save the ODT and LibreOffice froze, yet again. On try #2 I noticed that my 4-core machine had 1 core permanently occupied (the machine load was ~29%). After ~5 minutes the load dropped to normal. Now trying the *Save* once again it now completed normally & I was able to shutdown LibreOffice in normal fashion. Phew!

**7 Nov update:** The 24.8.2 AppImage version of Libreoffice has proven to be almost identical to the 7.4.7 version. After about 2 minutes the whole of LibreOffice dies & goes stiff. The only thing that I can do is to force-close the window. Not good.

### *Intentions*
The original intention of these documents was to show off how wonderful my updates to the Python3 PDF were. What it has actually become is a reference for Bug Reports to Libreoffice (LO). The point for me is that, whilst I have unearthed numerous bugs in LO whilst using it to produce these documents, I have zero idea as to why any of those bugs — both minor & show-stopping — exist. It is entirely possible that I've done something stupid whilst producing the PDFs that has caused those bugs, though I am unaware of what that could be if so. In addition, now that I cannot any longer load the ODT it is impossible for me to document the bug(s). So, here are the raw documents so that others with better tools than me can find them.

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

On Nov 14 the 24.8 AppImage was updated + the dir re-organised, in part using hard-links (`cp -l`). This is how the relevant files looked after:-
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
1. [‘0_ProgrammingInPython3.pdf’](/0_ProgrammingInPython3.pdf) obtained at `https://cs.smu.ca/~porter/csc/227/ProgrammingInPython3.pdf`     
  (I wanted to learn Python 3)     
> Note:
<a name="2024-august-01"></a>
> The ProgrammingInPython3 PDF is chock-a-block with internal + external links, but none of those links are active. As I had a little time, I resolved to add those links into the PDF.
>
2. [‘ProgrammingInPython3.txt’](Texts/ProgrammingInPython3.txt) obtained from [‘0_ProgrammingInPython3.pdf’](/0_ProgrammingInPython3.pdf) using `pdftotext`
>
<a name="2024-august-02"></a>
3. Work began to convert [ProgrammingInPython3.txt](Texts/ProgrammingInPython3.txt) into [‘1_Programming-In-Python3.odt’](/1_Programming-In-Python3.odt) and thus into [‘1_Programming-In-Python3.pdf’](/1_Programming-In-Python3.pdf).
> It was during this work that most of the PNG files within [/Images](/Images) were obtained. It was also during this work that most of the TXT files within [/Texts](/Texts) were obtained using `tesseract` upon the PNG files.
### 17 Oct 2024:
4. Conversion work crashed & burned *after* I saved [‘1_Programming-In-Python3.pdf’](/1_Programming-In-Python3.pdf) (see p586 (“Summary”, final chapter)).
>Note:
> I believe that I was in process of creating “Epilogue” + “Selected Bibliography” when the program just froze [NOT a system freeze] but made no notes & cannot now recall precise details
>
<a name="2024-oct-17"></a>
5. Work then began to convert [‘1_Programming-In-Python3.odt’](/1_Programming-In-Python3.odt) into [‘2_scratch.odt’](/2_scratch.odt) and thus into [‘2_scratch.pdf’](2_scratch.pdf)
### 19 Oct 2024:
6. Conversion work crashed & burned *after* completing all chapters (including “Epilogue” + “Selected Bibliography” but not the Index) and whilst preparing the Contents listing.
>Note:
> I was beginning to pull my hair out at this stage. Almost all work had been completed. I had zero idea why I should be experiencing problems & therefore no idea as to how to fix it.
>
> One feature of the work that I was inexperienced with was integration of drawing elements (eg arrows) with Tables (Figure 12.1 on p474 of [2_scratch.pdf](2_scratch.pdf) is an example; Figure 15.1 on p565 is another).
>
> I resolved to convert all these draw examples into PNG images & try one more time.
>
<a name="2024-oct-19"></a>
7. Work began to convert [‘2_scratch.odt’](/2_scratch.odt) into [‘3_new.odt’](/3_new.odt) and thus into [‘3_new.pdf’](3_new.pdf)
>
> After changing all problematic draw-elements on each page into PNG images, I was then able to produce the “Contents at a Glance” (p3 of [‘0_ProgrammingInPython3.pdf’](/0_ProgrammingInPython3.pdf)) without any problems. It seemed to me that I should produce a “List of Tables, Sidebars + Figures” first, then a Contents listing, and finally add a “Contents at a Glance” page. The last act would be to correct the jump targets for all forward-jump boxes + correct all Chapter links in the text. The first part (Tables listing) went without problems. However, after completing that LO simply refused to produce any Contents, though without any error message.
### 25 Oct 2024:
8. (the day before my 75th birthday) My entire computer crashed & burned as I loaded up [‘3_new.odt’](/3_new.odt) to try (yet again) to produce a Contents listing. In a state of disbelief I shut the computer down via the physical power button. Devuan successfully auto-restored the Journal on restart. In a state of some shock — I was used to this with Windows, but thought that I had left it all behind with Linux — I tried again with nothing else loaded. Just a second or two after loading up ‘3_new.odt’ the mouse stopped moving & everything froze. I got to the command line with `Ctrl-Alt-F1`, logged in & entered `startx` to get back to the desktop then shut down normally.
9. My final act on this occasion  was to use `libreoffice --convert-to pdf:writer_pdf_Export 3_new.odt` in a terminal to get a PDF (which was successful).
 ### 09 Nov 2024:
Two significant steps forward on the same day:     
  * A post by me within the  [dev1galaxy.org forum](https://dev1galaxy.org/viewtopic.php?id=6915) had produced responses that suggested that *ealier* versions of LO could run [“3_new.odt”](/3_new.odt) without freezing nor dying. After installing *"LibreOffice-7.2.3.2.basic-x86_64.AppImage"* from [AppImages listing](https://appimages.libreitalia.org/) I was able to prove that yes, those were accurate reports.
  * A response to a post by me within [ask.lo.org](https://ask.libreoffice.org/t/re-my-odt-froze-my-computer-i-had-to-press-the-power-button/113458) had stated that my extensive use of *Direct Paragraph Formatting* (sic) rather than *Body Text* was responsible for the increased load, since *“Direct formatting puts stress on Writer because every occurrence must be handled individually whereas style effects can be cached and reused at will”*. Such a design feature appeared to me to be rather stupid but, sure enough, experimentation seemed to show it to be true.

    ***Later Comment on “Direct Paragraph Formatting”:***     
    At the time I read *“Direct Paragraph Formatting”* as a mis-type for *“Default Paragraph Style”*. However, that writer is obsessed with *any* use of direct format by someone asking for help, and uses that as a stick to beat the questioner with. Having re-read it, I am now unsure as to whether that writer was referring to the *Default Paragraph Style* or not.

    Here are a few paragraphs to try to set the record straight:–

    > * ***Stylesheets:*** Libreoffice makes use of *Stylesheets*, referred to in the program as *“Styles”*. Each is a collection of format settings that refer to one particular scenario.
    > * ***Writer Style Scenarios:*** Page, Paragraph, Character, Frame, List, Table.
    > * ***Style Cascade:*** One style within each scenario is the default from which all others in the same scenario are derived.
    > * ***Style Values:*** Less work for the author + a more professional appearance.
    > * ***Direct Format:*** It is still possible to directly change any format setting directly within the page (paragraph, etc.).
    
10.  [‘3_new.odt’](/3_new.odt) loaded up under 7.2.3.2 & allowed me to operate LO.     
`Ctrl-h` gave Search+Replace. Using "Paragraph Styles" I searched for "Default Paragraph Style" & replaced with "Text Body". (Note: in 24.8.2 "Text Body" style has been changed to "Body Text").     
  <a name="2024-nov-09"></a>
I changed all 57 Introduction paragraphs in *3_new.odt* from *"Default Paragraph Style"* to *Body Text* and then saved the ODT as  [‘4_paragraph-fix.odt’](/4_paragraph-fix.odt). Opening *4_paragraph-fix.odt* again all the excess load was magically gone. Good Lord.
1. The initial magic of *4_paragraph-fix.odt* evapourated almost immediately as I continued with the default-paragraph changes. In addition, the bugs in *3_new.odt* had caused various elements to change position, and all of those needed fixing as well. The excess load issue reappeared the next day & did not go away. This new document was now beginning to show all the same symptoms as the old ones, plus a few new ones of it's own. I resolved to abandon this line of documents  to try anew with one of the original documents.
 ### 20 Nov 2024:
Begininng again with [‘1_Programming-In-Python3.odt’](/1_Programming-In-Python3.odt) under 7.2.3.2 I saved it as [‘2_paragraph-fixes.odt’](/2_paragraph-fixes.odt), and using `Ctrl-h` replaced every instance of 'Default Paragraph Style' with 'Text Body' style + a host of other changes. That enabled me to open the document under 7.4.7 and, after 10 seconds, the load fell to a minimal level. (False dawn; the next day it was back to continual load). This continued though every Chapter, including Epilogue & Bibliography. Next was to create a *Table of Contents*. I went through all the motions, but nothing happened.

The first line of construction (4 months: *0_ProgrammingInPython3.pdf* through to *4_paragraph-fix.odt*) clearly had hit a brick wall.     
The second line of construction (11 days: *1_Programming-In-Python3.odt* to *2_paragraph-fixes.odt*) had also hit yet another brick wall.     
I don't like hitting brick walls. I needed to take another route, so decided to do this via a Master Document instead.

## *Feedback*
I can be contacted via the [dev1galaxy.org forum](https://dev1galaxy.org/viewtopic.php?id=6915).

## *The Bugs*
I wrote down some of the LO Bugs that I was experiencing, but only after the show-stopping bug. Here's my record:

1. Copy + Paste sometimes omits Tables. It seems that only Tables that are NOT encapsulated with a Frame will be copied.

>Example 1:
>> Chapter 13 Regular Expressions (begins p483 in [1_Programming-In-Python3.pdf](/1_Programming-In-Python3.pdf)) has 7 tables.
>
>> I placed my cursor on the last line of p481 in [1_Programming-In-Python3.odt](/1_Programming-In-Python3.odt), held down the \<Shift> key on the keyboard, and then moved my cursor to the last line of p505. That meant that the whole of Chapter 13 was selected. I then pressed \<Ctrl>+C (copy) and moved to a new LO document. Next was to press \<Ctrl>+V (paste).
>
>> Most of Chapter 13 was pasted into the new document, but that did NOT include 6 of the tables. The only Table that was pasted was Table 13.6 (p497). That Table is NOT encapsulated in a Frame, whilst all other Tables ARE encapsulated within a Frame.
>
>> That is a Bug.

The above seems nice & simple, but the truth is messier.

>Example 2:
>> Chapter 14 Introduction to Parsing (begins p507 in [1_Programming-In-Python3.pdf](/1_Programming-In-Python3.pdf)) has 11 tables + 4 images.
>
>> I went through a similar copy/paste as with Ch13 above: only 5 of the 15 successfully pasted after copy:
>
>> - Table 14.5 (p514) : This Table IS encapsulated in a Frame.
>> - Table 14.8 (p519) : This Table is NOT encapsulated in a Frame.
>> - Table 14.10 (p520) : This Table is NOT encapsulated in a Frame.
>> - Image 14.11 (p520) : This Image has a caption (and thus IS encapsulated in a Frame).
>> - Image 14.14 (p522) : This Image has a caption (and thus IS encapsulated in a Frame).
>
>> All other 10 tables+images are contained within a Frame & did NOT copy.

2. Selecting the whole of an image caption (eg for rename) also selects the image. The 1st letter needs to be de-selected to prevent that.
3. The bottom of an image-in-frame-with-caption will coelesce with the top of a table-in-frame. In other words, the image will pay no regard to it's below-paragraph spacing. (I do not have an example of this to show as I went through the entire document re-arranging the text to prevent it occurring; it is still a bug).
4. The “Sidebar” (which is identified as a `Frame` in the Navigator (F5), and I think is a TextBox) coelesces with the Border of a Paragraph. An example can be seen on p293 of [‘3_new.pdf’](3_new.pdf). Just as with #3, this is an example of an entity within a Frame paying no attention to it's below-paragraph spacing. Possibly an identical bug.
5. The Jump-Boxes (which are LO TextBoxes) will not allow some keyboard shortcuts, although the menu WILL work. An example is that `menu:Edit | Paste Special | Paste Unformatted Text` DOES work, but `Shift+Ctrl+Alt+V` does NOT work.
6. In contrast to #5, `Ctrl+-` (insert soft Hyphen) DOES work inside a Jump-Box / TextBox, and the word breaks as desired, but no hyphen is inserted at the break. Using the menu is an identical result. Within the document itself this action works as expected. An example can be seen in the jumpbox at #4 (on the LHS of the sidebar on p293 of [‘3_new.pdf’](3_new.pdf), where a soft hyphen has been inserted between 'trans' + 'late'. The word is broken as desired, but no hyphen is inserted.
