## Operation

Open a *.jwlibrary* backup archive to see the Annotations (the editable text fields in some of the newer publications), Bookmarks, Favorites, Highlights, and Notes (**Category**) that are stored within it. These will be organized in a tree view, which you can group (**Grouping**) by either title, type, language, and (depending on what you are currently viewing) you may also have the option to group by year, color or tag. **Drag-and-drop to open** also works.

Notes that are not associated with any publication (created directly in the Personal Study space), are listed as *\* OTHER \** and with *\* NO LANGUAGE \**. Notes that aren't tagged will be listed as *\* UN-TAGGED \**.

The **status bar** shows the name of the currently opened archive. The **Count** column shows the number of items for each branch of the tree.

The items are initially **sorted** by decreasing count. Clicking on the column headers allows for sorting the tree as well; clicking the same header again reverses the sort.

#### View

The ***View*** menu has some additional options (also accessible directly via the key combination shortcut):

* **Expand All (Ctrl+E)** - expands the tree to make all levels visible
  * Note: **double-clicking** on an entry will expand (or collapse) all *its* sub-levels
* **Collapse All (Ctrl+C)** - collapse all levels
* **Select All (Ctrl+A)** - a quick way to select all entries
* **Unselect All (Ctrl+Z)** - unselect everything
* **Title View** - change how publication titles are displayed
  * **Code** - publication code
  * **Short** - abbreviated title
  * **Full** - complete title

**Right-clicking** on a line in the Notes or Annotations categories will bring up a window with a preview of the selected items, provided there aren't too many. The ID of each note is provided for reference.

If you modify an archive and intend to use the results to re-import into JW Library, make sure to **save** it (with a new name). **KEEP A BACKUP** of your original *.jwlibrary* archive in case you need to restore after messing up ;-)

#### Add

For Favorites only. Used for adding a Bible translation to your favorites, since there is no direct way of doing that in the JW Library app itself. Let me know if a required language is missing from the drop-down selection.

#### Delete

Select the Category and the item(s) you wish to eliminate from the database. For example, you may want to remove highlighting you made in some older magazines, or bookmarks you never knew you had, or clear your favorites completely, etc.

#### Export

This is most useful for Notes, as it exports notes from selected publications to a text file which you can edit directly (add, remove, modify) and later import into your archive (or share with someone else). If the note is attached to a highlight, the range data is also exported. Of course, if you just want to keep the note, you can edit the export file and remove the {RANGE=} attributes before importing (or delete the highlights within the app after).

Exporting of Annotations and Highlights is also possible - not so much with a view of direct editing, but sharing/merging into another archive.

#### Import

You need to provide a text file (UTF-8 encoded) with the Notes, Highlights or Annotations to import. You can use the file produced by exporting. Or you can create your own. The Higlights file is a CSV text file with a **{HIGHLIGHTS}** header. The Annotations file is also a CSV file, starting with **{ANNOTATIONS}**. You can simply **drag-and-drop the import file** into the app.

Editing or creating a Highlights or Annotations import file is *not* recommended. Rather, exported Highlights or Annotations can be merged into another archive. Any conflicting/duplicate entries will be replaced. In the case of Highlights, *overlapping highlights will be combined and the color changed to the one being imported* (this can affect the final number).

The accepted format for the Notes import file is like this:
    
    {TITLE=»}
    ==={CAT=BIBLE}{LANG=1}{ED=Rbi8}{BK=1}{CH=1}{VER=1}{COLOR=1}{RANGE=0,1}{TAGS=}{DATE=2021-10-19}===
    » Note Title
    Multi-line...
    ...note
    ==={CAT=PUBLICATION}{LANG=1}{PUB=rsg17}{ISSUE=0}{DOC=1204075}{BLOCK=517}{COLOR=0}{RANGE=0,1}{TAGS=research}{DATE=}===
    » Another Note Title
    Multi-line...
    ...
    ...note
    ==={CAT=INDEPENDENT}{TAGS=personal}{DATE=2021-10-19}===
    » Still Another Note Title
    Multi-line...
    ...note
    ==={END}===

The **{TITLE=}** attribute in the first line is *required* to identify a Notes export/import file, and provides a convenient way to delete any notes that have titles starting with this character (in this case "»"). This is to avoid creating duplicate notes if the title has changed. When set, all notes with titles starting with this character will be deleted before notes from the import file are imported. Otherwise, *notes with same title at same location will be over-written*, but those where the title was modified even slightly will create an almost duplicate note (this affects *all* notes - regardless of language or publication).

Each note definition starts with an attribute line. **{CAT=}** define the category. The **{LANG=}** attribute defines the language of the note (0 = English; 1 = Spanish; 2 = German; 3 = French; 4 = Italian; 5 = Brazilian Portuguese; 6 = Dutch; 7 = Japanese, etc.),  and **{ED=}** defines the Bible edition to associate the note with ("nwtsty" = Study Bible; "Rbi8" = Reference Bible) - **{PUB=}** for publications.

**Observations:**
  * Independent notes are compared by title and content. If two notes are imported that are equal in those two fields, only one will be imported. This helps eliminating duplicates.
  * Unless the corresponding colored highlights are also imported, the imported notes are placed at the *beginning* of the paragraph or verse that they are attached to.
  * If separated from their corresponding colored highlights, the note "stickies" appear in all Bibles *except* the Bible that is referenced at the bottom of the note in the "Personal Study" section, though the notes themselves are there in the reference pane (the default gray note icons do show correctly). The stickies *do* show in all the other Bibles. This may be a bug (or a feature?) in the app itself. For now, to have colored note icons (without any highlighting), I import my notes as for the Reference Bible (*Rbi8*); this way I can see the stickies in the Study Bible (*nwtsty*). This also applies between languages: a colored note without an associated highlight added to (for example) an English publication, will not have the note marker showing, but it *will* appear in the Spanish version of the same publication.
    * To sum up:
      - {COLOR=} 1-6 *and* {RANGE=} → colored stickie with highlight
      - {COLOR=} 1-6 and *NO* {RANGE=} → colored stickie in other language/version (at start of paragraph/verse and no highlight)
      - {COLOR=0} (with/without {RANGE=}) → grey stickie (at start of paragraph/verse and no highlight)

![notes](images/notes.png)

For Bible notes, **{BK=}{CH=}{VER=}** are all numeric and refer to the number of the book (1-66), the chapter and the verse, respectively. For books with just one chapter, use "1" for the chapter number. **{ISSUE=}{DOC=}{BLOCK=}** are the attributes associated with locations within a publication - they are, obviously, a bit more complicated to create, so it's best to simply modify the export file and re-import.

The **{COLOR=}** setting (0 = grey; 1 = yellow; 2 = green; 3 = blue; 4 = red; 5 = orange; 6 = purple) indicates the color of the note. The words themselves will not be highlighted; instead, there will be a colored sticky in the left margin next to the verse with the note.

The **{RANGE=}** attribute is optional and indicates the starting and ending word number (beginning with 0) of the associated highlight. So, {RANGE=0,1} indicates the first two words of the paragraph (indicated by {BLOCK=} in the case of publications, or {VER=} in the case of Bibles). If provided, a highlight of the indicated will be imported (created/replaced as may be the case), unless the color is 0 (grey). To have colored note markers (stickies), either provide a valid range *or* import the corresponding highlights *first*. Otherwise, only a grey marker will be added. Alternatively, use the "work-around" explained in the "Observations" (above).

**{TAGS=}** is used to add one or more tags to each note. If empty, no tag is added; if a note is replacing/updating another, its tags will be updated or removed.

**{DATE=}** is the date of last modification for each note in the format *yyyy-mm-dd*. If empty, and the note is new, the date of import is used; if the note is updated, the currently-set date is retained. Keep in mind that if you are using the option to first delete the notes with a special {TITLE=} character, the historical date will also need to be reimported.

Each note has to start with such a header. The very next line after the header is the note title. A multi-line body follows, terminated by the header of the next note or the file-terminating header =\=={END}===.

Here is an example blue note for Jude 21 (in  Spanish):

    ==={CAT=BIBLE}{LANG=1}{ED=Rbi8}{BK=65}{CH=1}{VER=21}{COLOR=3}{TAGS=}{DATE=}===
    » para mantenerse en el amor de Dios
    1. _edificándonos sobre nuestra santísima fe_ mediante el **estudio** diligente de la Palabra de Dios y la participación en la obra de predicar
    2. _**orando** con espíritu santo_, o en armonía con su influencia
    3. ejerciendo **fe** en el sacrificio redentor de Jesucristo, que hace posible la _vida eterna_

On a side-note, I format my notes with Markdown syntax (as above) for, even though JW Library doesn't allow rich-text formatting in the notes, that may change in the future and it should then be realtively easy to convert.

#### UTILITIES

#### Mask

If you need to share your complete archive but have some personal or confidential information, you can use this option to obfuscate the text fields in your archive. The length of the text remains the same, leaving all numbers and punctuation in place, but alphabetic characters are over-written with meaningless expressions such as 'obscured', 'yada', 'bla', 'gibberish' or 'børk'. To confirm: check the detailed view or right-click on a Notes item to see the preview. Only tags are not obscured.

#### Reindex

This function cleans up and re-orders the records in the archive database. It is not strictly required, though it *may* streamline and speed it up slightly. The process itself may take up to a minute, depending on the number of records the database contains. It does not need to be run more than once in a while.
