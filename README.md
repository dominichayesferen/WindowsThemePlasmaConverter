# Windows theme to KDE Plasma Global Theme converter
A tool designed to convert Windows .theme files, .themepack files, and certain special 'themes' into Global Themes to be able to apply in KDE Plasma.

For .theme files, this tool works best on themes installed on a Windows partition to the correct location.

## TODO - file support

- [ ] Windows XP .theme support
- [ ] Windows Vista .theme support
- [ ] Windows 7 - Present .theme support
- [ ] Windows Vista - Present .themepack support
- [ ] Samsung Theme support

## TODO - Icons
- [ ] Figure out what Windows version is targetted by other means later in the code, or the copyright header
- [ ] Check if custom icons are used - if so, do what Chicago95 Plus does to generate an icon set?
- [ ] Make the generated icon set inherit an OS-appropriate icon set, if one's made
- [ ] Add dependency to generated Global Theme package on the OS-appropriate icon set matching what was detected

## TODO - Cursors
- [ ] Detect the cursor theme by the path locations, and if empty assume Windows XP- Default cursors
- [ ] For Aero's cursors, determine by other factor such as the header's copyright date
- [ ] Add dependency to generated Global Theme package on the cursors matching what was detected

## TODO - Wallpaper
- [ ] For .themepacks, generate wallpapers separately in wallpaper package and install separately
- [ ] For .theme, check if the path is the Resources directory and if so attempt to find it with the assumption that '%ResourceDir%' is the location of the .theme file
- [ ] ...Failing that, try to go up two directories and find a Web/Wallpaper directory, assuming the path entails such
- [ ] ...Failing that, tell the user the path cannot be found and ask them to supply the file themselves via open file dialog
- [ ] Generate a Desktop Layout that applies the wallpaper, if one wallpaper
- [ ] Generate a Desktop Layout that applies the wallpapers in a slideshow, if multiple wallpapers (Windows 7+)

## TODO - Visual Style
- [ ] Support Classic Theme schemes
- [ ] Detect visual style and variants (e.g.: Luna, Metallic)
- [ ] Hardcode list of fallbacks for colour scheme generation, including Classic variants and visual styles+variants
- [ ] For Windows Vista+ themes that use AERO, apply their window colour as the user's accent colour when applying
- [ ] For Windows Vista+ themes that use AERO, figure out a way to potentially patch an Aero Glass Aurorae theme to use the appropriate window colour?
- [ ] ...Same with the Seven Glass Plasma Style, on Windows 7 .theme?
- [ ] Figure out what theme to use for WinXP styles (possibly Expose?)
- [ ] For Classic Theme schemes, use Reactionary and specially generated colour schemes on Reactionary's style
- [ ] For Windows 10+ themes, check for dark mode, titlebar colour, and panel colour

## TODO - Sound Schemes
- [ ] Submit upstream patch to allow Global Themes to set sound schemes (optional)*
- [ ] Set notification event sounds in KDE Plasma according to the sounds specified
- [ ] Same sorta file searching deal as with wallpapers
- [ ] For sound schemes linking to internal Windows sound schemes, put against hardcoded list of fallbacks and ye

## TODO - GUI
- [ ] Without converted themes, show the wizard for converting a theme immediately with no cancel option
- [ ] Save converted themes to a home folder for keeping track of the parts of Global Themes, and the Global Theme itself, that this program created/placed from conversion
- [ ] Symlink theme parts/Global Theme to their actual locations for Plasma to use
- [ ] For unsatisfied dependencies, before converting make a fake, randomly named, Global Theme to get the dependencies, install it, and then delete it from the user after installing - that way if dependency installation fails we don't waste any time creating themes
- [ ] Save specifics about the theme, deduced from the conversion process, to a json in the heart of the theme parts folder, so that it can be regenerated later
- [ ] Once themes're converted, bring user to a WB-esque interface where they can select a previously converted theme and choose to apply it, or convert a new theme file, as well as previewing their current GT conversions
- [ ] Provide an option to revert to system defaults for Global Theme, sound scheme, and so on
- [ ] Provide an option to apply a recommended Desktop Layout based on the Windows version detected
- [ ] Once a theme is applied through the program, play the theme's Change Theme sound, login sound failing that

## TODO - Samsung Theme support
- [ ] When creating a new theme conversion, before telling the user to open a file, give them the option between "Windows .theme and .themepack files - Themes from Microsoft's website, themes generated in Microsoft Windows, or themes handcrafted for Microsoft Windows", and "Special Themes - Download and convert special Windows themes that were distributed in special formats"
- [ ] If the user picks "Special Themes", proceed through a hardcoded list of special themes, one of which being "Samsung Theme"
- [ ] When a special theme is picked, attempt to download the theme from a hardcoded URL, and if that fails, ask the user to provide their own copy of the file
- [ ] As long as extraction and file detection of the theme doesn't fail, 'convert' using a bunch of special instructions
- [ ] Instantly assume Windows XP with Luna as the msstyles when converting Samsung Theme

## TODO - Bonus ideas?
- [ ] Provide an appropriate splash screen, if not lock screen too, based on the theme being converted?
- [ ] ...Assuming authui.dll+imageres.dll or winlogon.exe or msgina.dll, depending on the version of Windows, can be found, that is
- [ ] ...Remember that Samsung Theme has a custom login screen, too
- [ ] ...Figure out how to extract the necessary resources to create such a file, and download the necessary backend QMLs
