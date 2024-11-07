# *Source Docs for Bug-Hunting*
## *(Documentation for Python v3)*

### *¡Warning!*
In Sept 2024 the simple act of loading [“3_new.odt”](/3_new.odt) into Libreoffice caused the entire desktop computer to lockup & become unresponsive to anything other than the OFF power button on the case. Without any further action from me towards the ODT that has now, in Nov 2024, moderated into a LibreOffice freeze when the ODT is loaded, but not a System Freeze. YMMV

The above was all under LibreOffice v7.4.7.2. In 6 Nov 2024 I installed a Fresh AppImage (v24.8.2.1 - see below) to be available together with the v7 installation, and that AppImage would successfully allow access to the ODT.

It was still as buggy as can be under the AppImage: the Status Bar Page-stats kept varying, as did the final page number. In addition, *Figure 15.1* kept intruding into the last pages, then was displayed within multiple other pages (the only action from me was to change to the last two pages). Fig 15.1 is shown on p563 of [“3_new.pdf”](/3_new.pdf), and that is completely wrong. It is not where it is supposed to be, nor where I placed it. Yet another bug.

On my first attempt I tried to save the ODT and LibreOffice froze, yet again. On try #2 I noticed that my 4-core machine had 1 core permanently occupied (the machine load was ~29%). After ~5 minutes the load dropped to normal. Now trying the *Save* once again it now completed normally & I was able to shutdown LibreOffice in normal fashion. Phew!

### *Intentions*
The intention of these documents is ultimately to act as a reference for a Bug Report to Libreoffice (LO). The point for me is that, whilst I have unearthed numerous bugs in LO whilst using it to produce these documents, I have zero idea as to why any of those bugs — both minor & show-stopping — exist. It is entirely possible that I've done something stupid whilst producing the PDFs that has caused those bugs, though I am unaware of what that could be if so. In addition, now that I cannot any longer load the ODT it is impossible for me to document the bug(s). So, here are the raw documents so that others with better tools than me can find them.

### *Versions*
These are my current LO + OS versions:
- LibreOffice 7.4.7.2 40(Build:2)
- `$ lsb_release -ds` => “Devuan GNU/Linux 5 (daedalus)”
- `$ uname -srm` => “Linux 6.1.0-27-amd64 x86_64”

### *Timeline*
Here is a timeline of production of each of these documents, and how they are linked to each other.

- August 2024: [‘0_ProgrammingInPython3.pdf’](/0_ProgrammingInPython3.pdf) obtained at `https://cs.smu.ca/~porter/csc/227/ProgrammingInPython3.pdf`
  (I wanted to learn Python 3)
>Note:
>>The ProgrammingInPython3 PDF is chock-a-block with internal + external links, but none of those links are active. As I had a little time, I resolved to add those links into the PDF.
>
>>[‘ProgrammingInPython3.txt’](Texts/ProgrammingInPython3.txt) obtained from [‘0_ProgrammingInPython3.pdf’](/0_ProgrammingInPython3.pdf) using `pdftotext`
>
>>Work began to convert [ProgrammingInPython3.txt](Texts/ProgrammingInPython3.txt) into [‘1_Programming-In-Python3.odt’](/1_Programming-In-Python3.odt) and thus into [‘1_Programming-In-Python3.pdf’](/1_Programming-In-Python3.pdf). It was during this work that most of the PNG files within [/Images](/Images) were obtained. It was also during this work that most of the TXT files within [/Texts](/Texts) were obtained using `tesseract` upon the PNG files.
- 17 Oct 2024: Conversion work crashed & burned *after* I saved [‘1_Programming-In-Python3.pdf’](/1_Programming-In-Python3.pdf) (see p586 (“Summary”, final chapter)).
>Note:
>>I believe that I was in process of creating “Epilogue” + “Selected Bibliography” when the program just froze [NOT a system freeze] but made no notes & cannot now recall precise details
>
>>Work then began to convert [‘1_Programming-In-Python3.odt’](/1_Programming-In-Python3.odt) into [‘2_scratch.odt’](/2_scratch.odt) and thus into [‘2_scratch.pdf’](2_scratch.pdf)
- 19 Oct 2024: Conversion work crashed & burned *after* completing all chapters (including “Epilogue” + “Selected Bibliography” but not the Index) and whilst preparing the Contents listing.
>Note:
>>I was beginning to pull my hair out at this stage. Almost all work had been completed. I had zero idea why I should be experiencing problems & therefore no idea as to how to fix it.
>
>>One feature of the work that I was inexperienced with was integration of drawing elements (eg arrows) with Tables (Figure 12.1 on p474 of [2_scratch.pdf](2_scratch.pdf) is an example; Figure 15.1 on p565 is another).
>
>>I resolved to convert all these draw examples into PNG images & try one more time.
>
>>Work began to convert [‘2_scratch.odt’](/2_scratch.odt) into [‘3_new.odt’](/3_new.odt) and thus into [‘3_new.pdf’](3_new.pdf)
>
>>After changing all problematic draw-elements on each page into PNG images, I was then able to produce the “Contents at a Glance” (p3 of [‘0_ProgrammingInPython3.pdf’](/0_ProgrammingInPython3.pdf)) without any problems. It seemed to me that I should produce a “List of Tables, Sidebars + Figures” first, then a Contents listing, and finally add a “Contents at a Glance” page. The last act would be to correct the jump targets for all forward-jump boxes + correct all Chapter links in the text. The first part (Tables listing) went without problems. However, after completing that LO simply refused to produce any Contents, though without any error message.
- 25 Oct 2024: (the day before my 75th birthday) My entire computer crashed & burned as I loaded up [‘3_new.odt’](/3_new.odt) to try (yet again) to produce a Contents listing. In a state of disbelief I shut the computer down via the physical power button. Devuan successfully auto-restored the Journal on restart. In a state of some shock — I was used to this with Windows, but thought that I had left it all behind with Linux — I tried again with nothing else loaded. Just a second or two after loading up ‘3_new.odt’ the mouse stopped moving & everything froze. I got to the command line with `Ctrl-Alt-F1`, logged in & entered `startx` to get back to the desktop then shut down normally. My final act was to use `libreoffice --convert-to pdf:writer_pdf_Export 3_new.odt` in a terminal to get a PDF (which was successful).

### *Feedback*
I can be contacted via the [dev1galaxy.org forum](https://dev1galaxy.org/viewtopic.php?id=6915).

### *The Bugs*
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
