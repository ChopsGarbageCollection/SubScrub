<div align="center">

# SubScrub ✨

**The easiest way to keep your media library subtitle-clean.**
```
  ____        _     ____                  _     
 / ___| _   _| |__ / ___|  ___ _ __ _   _| |__  
 \___ \| | | | '_ \\___ \ / __| '__| | | | '_ \ 
  ___) | |_| | |_) |___) | (__| |  | |_| | |_) |
 |____/ \__,_|_.__/|____/ \___|_|   \__,_|_.__/ 

    Subtitle Management Utility v1.1
```

*Made by Chops Garbage Collection*

</div>

---

SubScrub helps you organize subtitle files in your media library by automatically archiving non-English (or non-preferred language) subtitles while keeping your preferred language files in place.

Perfect for **Plex**, **Jellyfin**, **Emby**, or any media server!

---

## ✨ Features

- 🌍 **Hybrid Language Selection** - Command line or interactive prompts
- 🗂️ **23+ Built-in Languages** - Automatic variant detection (spa → spanish, spa, es, es-mx)
- 🔍 **Duplicate Detection** - Finds and removes duplicate subtitle files
- 📦 **Smart Archiving** - Preserves folder structure in backup
- 🎯 **Multi-format Support** - .srt, .vtt, .ass, .sub, .ssa
- 🧪 **Dry Run Mode** - Preview changes before committing
- 📊 **Detailed Logging** - TXT and CSV reports
- 🧹 **Empty Folder Cleanup** - Removes folders left behind
- 💚 **Network Drive Compatible** - Works with NAS/SMB shares

---

## 🚀 Quick Start

### Option 1: Simple (Double-Click)
1. Download the latest release
2. Extract the ZIP file
3. Double-click `SubScrub-v1.1`
4. Answer the prompts
5. Choose **Dry Run** for your first time

### Option 2: Command Line (Power Users)
```batch
# Spanish subtitles
SubScrub.bat spa

# French subtitles
SubScrub.bat fre

# German subtitles
SubScrub.bat ger
```

```powershell
# PowerShell
.\SubScrub-v1.1.ps1 -Language spa
```

---

## 📥 Installation

### Download Options

**Beginner-Friendly (Recommended):**
- Download `SubScrub-v1.1` from [Releases](https://github.com/SaaS-Hole-Solutions/SubScrub/releases)
- No installation required - just run it!

**Power Users:**
- Clone this repository
- Run `SubScrub-v1.1` directly with PowerShell
- Or use `SubScrub-v1.1` for easy launching

### Requirements
- Windows 7/8/10/11
- PowerShell 5.1+ (built into Windows)
- No admin rights required

---

## 🌍 Supported Languages

SubScrub includes built-in mappings for 23+ languages:

| Code | Language | Code | Language | Code | Language |
|------|----------|------|----------|------|----------|
| eng | English | spa | Spanish | fre | French |
| ger | German | ita | Italian | por | Portuguese |
| jpn | Japanese | chi | Chinese | kor | Korean |
| rus | Russian | ara | Arabic | pol | Polish |
| dut | Dutch | swe | Swedish | nor | Norwegian |
| dan | Danish | fin | Finnish | gre | Greek |
| tur | Turkish | heb | Hebrew | hin | Hindi |
| tha | Thai | vie | Vietnamese |

**Don't see your language?** No problem! Enter any language code during interactive mode.

---

## 📖 Usage Examples

### Scenario 1: Spanish Media Library
You have a library with Spanish content and want to keep Spanish subs:

**Interactive Mode:**
```
Keep English as your primary language? (y/n): n
Enter your primary language code: spa

Result: Keeps spanish, spa, es, es-mx, es-es
        Archives all other languages
```

**Command Line:**
```batch
SubScrub.bat spa
```

### Scenario 2: Bilingual Library (English + Spanish)
You want to keep BOTH English and Spanish:

**Interactive Mode:**
```
Keep English as your primary language? (y/n): y
Add additional language codes to KEEP? spa

Result: Keeps English + Spanish
        Archives all others
```

### Scenario 3: Anime Collection (Japanese)
```batch
SubScrub.bat jpn
```
Keeps: japanese, jpn, ja, ja-jp  
Archives: All other languages

---

## 🎯 How It Works

1. **Scans** your media directory for subtitle files
2. **Analyzes** filenames for language codes
3. **Detects** duplicate subtitles
4. **Keeps** subtitles matching your language preference
5. **Archives** all other subtitles to a backup folder (structure preserved)
6. **Cleans** empty folders (optional)
7. **Logs** everything in detailed reports

### What Gets Kept vs Archived?

**KEPT:**
- Files matching your selected language(s)
- Example: `movie.eng.srt`, `show.en.srt`, `video.english.srt`

**ARCHIVED:**
- All other subtitle files
- Example: `movie.spa.srt`, `show.fre.vtt`, `video.ger.ass`

---

## 📂 Output

After running SubScrub, you'll find:

```
C:\Backups\Media_Subtitles\Backup_20240214_153217\
├── archive_log.txt              ← Detailed log with timestamps
├── subtitle_archive_report.csv  ← CSV report (if generated)
└── [Your folder structure]      ← Archived subtitle files
```

**Desktop:**
```
subtitle_archive_report_20240214_153217.csv  ← Copy of CSV report
```

---

## 🛡️ Safety Features

- ✅ **Dry Run Mode** - Preview before making changes
- ✅ **Confirmation Prompts** - Script asks before major operations
- ✅ **Detailed Logging** - Track every file moved
- ✅ **Backup Preservation** - Files are moved, not deleted
- ✅ **Easy Restoration** - Folder structure maintained for easy recovery

---

## ⚙️ Advanced Usage

### Command Line Parameters
```powershell
# Specify language via parameter
.\SubScrub.ps1 -Language spa

# Batch file equivalent
SubScrub.bat spa
```

### Automation / Scheduled Tasks
SubScrub can be automated for scheduled cleanup:

**Windows Task Scheduler:**
```
Program: powershell.exe
Arguments: -NoProfile -ExecutionPolicy Bypass -File "C:\Scripts\SubScrub.ps1" -Language spa
```

### Custom Language Codes
Not in the built-in list? Just enter your code:
```
Enter your primary language code: tgl
Result: Uses "tgl" for Tagalog subtitles
```

---

## 🆘 Troubleshooting

### Antivirus Blocks SubScrub.exe
**Solution:** Use `SubScrub.bat` instead (no antivirus issues)

### Files Not Detected as English
**Check:** Filename must contain language code (e.g., `movie.eng.srt`)  
**Solution:** Add alternative codes when prompted

### Empty Folders Won't Delete
**Note:** Normal on network drives - Windows holds file handles briefly  
**Solution:** Script includes 100ms delay to help. You can delete manually if needed.

### Want to Restore Archived Subtitles?
1. Navigate to your backup folder
2. Find the timestamped backup (e.g., `Backup_20240214_153217`)
3. Copy files back to original locations (check `archive_log.txt` for paths)

---

## 📋 Documentation

- **README.txt** - Complete user guide
- **QUICK_REFERENCE.txt** - One-page cheat sheet
- **USAGE_EXAMPLES.txt** - Real-world scenarios
- **CHANGELOG.txt** - Version history

---

## 🔧 Development

### Building from Source

**Create the .exe:**
```powershell
Install-Module ps2exe -Scope CurrentUser
Invoke-ps2exe -InputFile "SubScrub-v1.1.ps1" -OutputFile "SubScrub.exe" -title "SubScrub v1.1" -version "1.1.0.0"
```

**Requirements:**
- PowerShell 5.1+
- PS2EXE module (for creating .exe)

---

## 📊 Version History

### v1.1 (2024-02-14)
- ✨ Hybrid language selection system (command line + interactive)
- ✨ Built-in mappings for 23+ languages
- ✨ Enhanced Step 2 with clearer default language indication
- 📚 Comprehensive documentation suite

### v1.0 (2024-02-14)
- 🐛 Fixed case-sensitive path handling
- 🐛 Fixed uninitialized variable crash
- 🐛 Added network drive stability (100ms delay)
- 🐛 Enhanced CSV archival (dual location)
- 🎨 Green progress bar
- 📊 Enhanced logging with timestamps and file details

See [CHANGELOG.txt](CHANGELOG.txt) for complete history.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### Areas for Contribution
- Additional language mappings
- GUI version
- Linux/macOS support
- Additional subtitle formats

---

## 📄 License

This software is provided "as is" without warranty of any kind. Use at your own risk.

Always backup your data before running utilities that modify your file system.

---

## 💬 Support

- **Issues:** [GitHub Issues](https://github.com/SaaS-Hole-Solutions/SubScrub/issues)
- **Documentation:** See included README.txt and USAGE_EXAMPLES.txt

---

## ⭐ Show Your Support

If SubScrub helped organize your media library, please consider:
- ⭐ Starring this repository
- 🐛 Reporting bugs or requesting features
- 📢 Sharing with others who might find it useful

---

**Made with ❤️ for media enthusiasts everywhere**

---

## 🎬 Example Output

```
  ____        _     ____                  _     
 / ___| _   _| |__ / ___|  ___ _ __ _   _| |__  
 \___ \| | | | '_ \\___ \ / __| '__| | | | '_ \ 
  ___) | |_| | |_) |___) | (__| |  | |_| | |_) |
 |____/ \__,_|_.__/|____/ \___|_|   \__,_|_.__/ 

        Subtitle Management Utility v1.1

==============================================
           SubScrub v1.1
   Intelligent Subtitle File Management
==============================================

STEP 1: Select Directory to Scan
Enter the directory path (Press Enter for default: 'Z:\Media'): 

[OK] Scan path set to: Z:\Media

STEP 2: Configure Language Preferences

DEFAULT: English subtitles will be KEPT
(Files matching: english, eng, en, en-us)

Keep English as your primary language? (y/n) [y]: n

Common language codes:
  spa (Spanish)    fre (French)     ger (German)      ita (Italian)
  por (Portuguese) jpn (Japanese)   chi (Chinese)     kor (Korean)
  rus (Russian)    ara (Arabic)     pol (Polish)      dut (Dutch)

Enter your primary language code: spa

[OK] Keep List set to: spanish, spa, es, es-mx, es-es

...processing...

==== FINAL STATISTICS ====
Files Kept:        127
Files Archived:    43
Duplicates Found:  8
Empty Folders:     2

Backup Location:   C:\Backups\Media_Subtitles\Backup_20240214_153217
Archive Log:       C:\Backups\Media_Subtitles\Backup_20240214_153217\archive_log.txt

==== ALL OPERATIONS COMPLETE ====
```

<div align="center">

## ⚖️ License

Distributed under the MIT License.

Made by **Chops Garbage Collection** for the self-hosted community. Enjoy! 🎬

</div>
