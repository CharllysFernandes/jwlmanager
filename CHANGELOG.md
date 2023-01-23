# JWLManager Changelog

## [Unreleased]
### Added

- Status bar message when the data is being processed (tree structure is being constructed)

### Changed

- Significant **code rewrite to utilize Pandas** module for internal data handling
- Add Favorite only limits Bible editions available by the selected language (preventing adding a favorite for a publication that doesn't exist)

### Fixed

### Removed

- Removed options for Grouped and Detailed views
  - Replaced with additional Type grouping

____
## [2.0.2] - 2023-01-18
### Added

- Italian translation (mostly done)
  - Thank you to a couple of friends!
- **Automatic builds** (Windows and macOS packages)
  - Please report any issues ;-)

### Changed

- Multiple note tags are now separated by " | " instead of ","
- Updated README
- Updated French translations
- **Disabled Detailed View** option
  - It was very slow and causing problems with large data sets

### Fixed


### Removed

- Removed Detailed and Grouped options
  - Added a grouping option by Type instead

- Removed README.txt (text version of the README, which is in markdown format)

## [2.0.1] - 2023-01-04
### Added

- **Multi-language support** (internationalization/i18n)
  - Localization/L10n in English, French, Spanish
    - others in process of being translated on [Weblate](https://hosted.weblate.org/engage/jwlmanager/)
- Added alert box when change-over to Detailed view could take a long time (with many records to process)

### Changed

- **UI framework** transitioned from Qt5 to Qt6 (PySide2 to PySide6)
  - **NOTE**: Qt6 is not compatible with Windows 7/8, hence there is a separate [Qt5 branch](https://github.com/erykjj/jwlmanager/tree/Qt5) with bug-fix/maintenance releases for older operating systems
- Rearranged/cleaned up the folder structure
- Cosmetic/layout changes to GUI
- "Obscure" is now "Mask", which is a more appropriate term for this kind of data obfuscation
- Split off usage instructions from README to a separate HELP document

## [1.2.2] - 2022-12-20
### Added

- More precise manifest file included in saved archives

### Changed

- Link to Github repo in About box
- Links to Github in README
- Modified README to highlight multi-platform support

### Fixed

- Fixed some minor type-check warnings
- Fixed SQL for discarding unused records (trimming the DB)
- Blank/new archive had incomplete table structure

## [1.2.1] - 2022-04-25
### Fixed

- Fix for date not being set correctly on Note import

## [1.2.0] - 2022-04-24
### Added

- Last modification date field of notes can now be exported and imported (see README)

## [1.1.0] - 2022-04-12
### Changed

- More precise Note location for re-linking with highlights

### Fixed

- Fixed export/import of special Bible notes (in a book header, for example, instead of a regular verse)
- Fixed gray stickies not showing

## [1.0.1] - 2022-04-07
### Fixed

- Corrected slight mixup on Notes & Highlights color names

## [1.0.0] - 2022-03-27
### Changed

- Data Viewer
  - Modified formatting to include NoteId of each Note
  - Single instance with selection in title
  - Remember window size and position while app is open
- Help window
  - Only one instance
  - Remember window size and position while app is open

### Fixed

- Stop showing additional icon on taskbar when About dialog is opened

## [0.4.0] - 2022-03-20
### Added

- Added data view for Notes (with right-click)
- Added data view for Annotations (with right-click)
- Added drag-and-drop functionality to open archives
- Added drag-and-drop for importing

### Changed

- Independent notes (not related to any publication) are now listed as OTHER (instead of FREE)

### Fixed

- MAJOR FIX: backups made on iPhone/iPad devices have a different db name, which would make the app crash
- Fixed for icons/README not found when script executed from outside of directory
- Fixed opening URLs in default browser

## [0.3.2] - 2022-02-20
### Added

- Better exception handling and reporting

### Changed

- Adjusted About dialog box
- Adjusted Add Favorite dialog box
- Cosmetic/UI adjustments

### Fixed

- Working directory changed on save and export
- Export files weren't always UTF-8 encoded
- Fixed SQL rollback on aborted import
- Selected item count reset when new archive created

## [0.3.1] - 2022-02-10
### Added

- Better handling of export/import file encoding (UTF-8)
- App icon under Mac OS

### Changed

- Adjusted Annotation and Highlight import to accept more general CSV files

## [0.3.0] - 2022-02-04
### Added

- Added obscuring function
- Added general exception handling
- More status bar information on action being taken

### Changed

- Modified UserMark trimming SQL
- Readded reindexing function with progress bar
- Disabled detailed view on file open
- Disabled grouped view on file open
- Code clean-up

### Fixed

- Fixed Bookmark selection

## [0.2.4] - 2022-01-31
### Changed

- Slight adjustment in interface sizing and Help menu

### Fixed

- Fixed cases of unknown publications
- Fixed cases where issue is not a date
- Fixed some still-used UserMark records being trimmed

## [0.2.3] - 2022-01-29
### Added

- Handle unknown media items or publications in Favorites

### Changed

- Cleaned up resources (unnecessary icons, etc.)
- Specify encoding for export/import files

### Fixed

- Fixed SQL for untagged notes

## [0.2.2] - 2022-01-24
### Changed

- Highlights defined by BlockRange instead of UserMark
- Modified trim SQL to clean up unused UserMark records
- Slight adjustment to handle JW Broadcasting video segments in Favorites

## [0.2.1] - 2022-01-19
### Changed

- Re-added publication issue date to grouping by year
- Speeded up tree construction even more

## [0.2.0] - 2022-01-17
### Added

- Progress bar shown when a lot of elements need to be loaded and will slow down the app

### Changed

- Added Bible book number before name for better sorting
- Made Grouped and Detailed view mutually exclusive
- Code clean-up
- README updated
- Minor UI adjustment: slight increase in button height
- Speeded up tree construction

### Fixed

- Fix for tree being constructed twice under some conditions
- Fix for missing items in detailed view

## [0.1.0] - 2022-01-11
### Added

- App icon
- Implemented adding Favorites
- Added detailed view

### Fixed

- Corrected Bookmark count
- Speeded up reindexing

## [0.0.10] - 2022-01-08
### Added

- Changelog file
- Implemented importing Annotations
- Implemented importing Highlights
- Added some exception handling on failed imports

### Changed

- Enabled Save As as soon as an archive is opened
- Updated README with info on importing and adding
- Adjusted Annotations export to work better with importing
- Add current date to new archive manifest

### Fixed

- Line-breaks in Annotations

## [0.0.9] - 2022-01-02
### Added

- Implemented importing Notes
- Implemented creating a new/blank archive
- Added context-aware buttons to interface
  - Add - for Favorites only - process not implemented yet
  - Export - for Notes, Highlights, Annotations
  - Import - for Notes, Highlights, Annotations - process for the last two not implemente yet

### Changed

- Various cosmetic modifications and small bug fixes

## [0.0.8] - 2021-12-28
### Added

- Added option to group by publication type

### Changed

- Updated publications list
- Moved resources to SQLite db
- Improved About and Help dialogs

## [0.0.7] - 2021-12-24
### Added

- Implemented viewing, deleting, exporting, reindexing, saving

____
[Unreleased]: https://github.com/erykjj/jwlmanager
[2.0.1]:https://github.com/erykjj/jwlmanager/releases/tag/v2.0.1
[2.0.2]:https://github.com/erykjj/jwlmanager/releases/tag/v2.0.2
[1.2.2]:https://github.com/erykjj/jwlmanager/releases/tag/v1.2.2
[1.2.1]:https://github.com/erykjj/jwlmanager/releases/tag/v1.2.1
[1.2.0]:https://gitlab.com/erykj/jwlmanager/-/releases/v1.2.0
[1.1.0]:https://gitlab.com/erykj/jwlmanager/-/releases/v1.1.0
[1.0.1]:https://gitlab.com/erykj/jwlmanager/-/releases/v1.0.1
[1.0.0]:https://gitlab.com/erykj/jwlmanager/-/releases/v1.0.0
[0.4.0]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.4.0
[0.3.2]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.3.2
[0.3.1]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.3.1
[0.3.0]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.3.0
[0.2.4]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.2.4
[0.2.3]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.2.3
[0.2.2]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.2.2
[0.2.1]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.2.1
[0.2.0]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.2.0
[0.1.0]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.1.0
[0.0.10]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.0.10
[0.0.9]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.0.9
[0.0.8]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.0.8
[0.0.7]:https://gitlab.com/erykj/jwlmanager/-/releases/v0.0.7
