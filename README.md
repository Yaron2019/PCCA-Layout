# Hyperspin layout for the Attract Mode frontend

### Version 1.15 
This script is intended to work with the Attract-Mode frontend http://attractmode.org/ , it intends to reproduce the real hyperspin experience in HD as precise as possible using the same themes and folder structure as a real Hyperspin setup.

PCCA's Attract Mode official forum thread:
http://forum.attractmode.org/index.php?topic=3526.0

Hypertheme can be used to build new themes or you can build your own with a higher resolution than hyperspin's default 1024x768.

## Video
[![Theme PCCA](http://i3.ytimg.com/vi/TtoKfDMz860/maxresdefault.jpg)](https://youtu.be/TtoKfDMz860) 
 
## Restrictions
It is MANDATORY to set in Attract-Mode options: General->Startup Mode to 'Show Display Menu' and Displays->'Display Menu Options->'Allow Exit from 'Display Menu' to 'No'.


## Theme.xml
It's possible to add to your artwork xml tags: width and height for auto resizing media artwork.

example:
`<artwork3 w="550" h="280" x="777" y="417" time="0.7" delay ="0" type="ease" start="right" rest="none"/>`

These options keeps the aspect ratio and the picture is flipped according to its orientation (P or L).
Using this technique, you don't need to resize all your media everytime.

An additional xml tag is `<hd lw="1920" lh="1080" />`
It informs the script that you are using a real HD theme, 'lw' and 'lh' must be the resolution at which the theme was created.

Bezel and background stretch have no ifluence if 'hd' tag is present.

Unified video themes can be used. Place videos named as system name / rom name in their respective Themes folders and the unified video will be diplayed in full-screen.
 

# Layouts Options

### Media Path
Path to your hyperspin media, for example c:\attract\layouts\pcca\media

### Low GPU mode
Low GPU (Intel HD,.. less backgrounds transition)

### Interface language
Preferred user language (English or French at the moment)

### Main menu stats
Enable or disable the main menu stats system: game counting, number of times played, total play time

### Wheel offset
Wheel's X Offset ocoordinates

### Wheel transition time
Time in milliseconds for wheel spin

### Wheel fade time
Time in seconds for wheel fade out (0 disables fading)

### Wheel fade alpha
Alpha value of the faded wheel

### Show wheel pointer
Show or hide wheel pointer

### Wheel pointer position
Minimal or Nomral wheel pointer position

### Wheel sounds
Enable sounds when navigating the wheel

### Override transitions
Use flv transition videos placed in folder -> \Media\Frontend\Video\Transitions

If you think a certain transtion would look great for a certain game, then you can make a copy of that transition to 
your \Media\{SYSTEME NAME}\Video\Override Transitions folder and rename the video with the same name of the rom you would like to see the transition on.

If you give a transition the same name as one of your genre categories you will see the transtion when a game match the category if no other transition is available for that game.

### Animated backgrounds
Use background transitions

### Theme aspect
Stretch or Center the theme on the screen

### Show bezels
If display is centered, use bezels to replace pixel stretched border

### Bezels on top
Put bezel on top of the theme artworks

### Background stretch
'Yes': Strecth Background only (some themes with video frame in background may look distorted with this option enabled).

'Main Menu': Stretch background only when you are in main menu wheel.

### Show game info
Show or hide game info

### Game info coordinates
Game info x,y coordinates on the screen. If empty = left bottom

### Show manufacturer name
Show manufacturer name if available

### Enable random text colors
Enable game info random text colors

### Reload backgrounds
Force reloading background transitions when navigating on default theme

### Video snap CRT effect
Enable CRT special effect for video snaps

### Special artwork
Enable or disable the special artwork (if set to 'No', special artwork is disabled globally)

### Search key
Choose the key to initiate a search

### Search results
Choose the search method



## Media

### Folders structure
Identical to Hyperspin.

### Bezels

Bezels need to be placed in images/bezel of 'pcca' layout folder, named as the system you want the bezel for.

### Backgrounds

Background should be named as your roms/system and placed in media/Background folder.
If background is found in your theme.zip, the theme background is used, and not the one in the media folder.

### Sounds
Identical to Hyperspin.

Enable Wheel Game Sounds - These are the short game sounds played everytime you navigate the wheel.

Enable Wheel Click Sound - There is a small wheel click sound that also plays when you navigate the wheel.

these sounds are played when:

Sound_Letter_Click = when you press prev_letter or next_letter

Sound_Screen_Click = when you change selection on a screen overlay (Exit, tags, favorites, filters)

Sound_Screen_In = When you enter screen overlay (Exit, tags, favorites, filters)

Sound_Screen_Out = When you exit screen overlay (Exit, tags, favorites, filters)

Sound_Wheel_In = when you enter a new system (ToNewList)

Sound_Wheel_Out = when you exit a system (StartLayout)

Sound_Wheel_Jump = when you use prev_page or next_page


Background Music is played if an mp3 file is found anywhere in theme.zip, no matter how it is named or in the media folder Sound/Background Music/ named as the rom name of the game you want music for.

if Background Music is found in the theme.zip file or the Sound/Background Music folder ("C:\Hyperspin\Media\Atari 2600\Sound\Background Music\Vanguard.mp3" for example), the theme Background Music is used and video snap sound is automaticly muted.


### Specials Artwork

Identical to Hyperspin.
pcca layout use special artworks placed in folder -> \Media\{SYSTEME NAME}\Images\Special

Special artwork media should be named :
SpecialA1 , SpecialA2, ...
SpecialB1 , SpecialB2, ...

Special artwork settings is defined in pcca/Settings/{SYSTEME NAME}.ini , and for main menu,  pcca/Settings/Main Menu.ini

Real Hyperspin Settings ini can be used as is by copying it to the pcca layout Settings folder.

```
[Special Art A] // the name of the special artwork collection (A or B)
default=false    -> When in system use default artworks from main menu
active=true      -> enabled (true) or disabled (false)
x=512            -> x alignement ( if width and height are specified , then it's real coord , if not, it's hyperspin default 1024x768 scaled for your screen resolution)
y=720            -> y alignement ( if width and height are specified , then it's real coord , if not, it's hyperspin default 1024x768 scaled for your screen resolution)
in=0.4           -> Time it takes the artworks to animate in  position (in seconds).
out=0.4          -> Time it takes the artworks to animate out  position (in seconds).
length=3         -> The length of time the artwork stays in position before animating out (in seconds).
delay=0          -> The amount of time to wait between animations (in seconds).
type=normal      -> The style of animation you want to use (normal = linear, fade, bounce)
start=bottom     -> The side of the screen from which animations enter. (bottom, top , left , right)
/* Added for Attract-mode (not mandatory) */
w=500            -> width of your special artwork
h=100            -> height of your special artwork
ext=png          -> extension of your special artwork (you can use any media extension (video, swf, or any image supported by Attract-mode)
```
If no .ini file is found but you have special artwork inside your images/Special folder , the default settings will be applied.

The special artworks defaults settings is:

###Special A

```
active=true 
in=0.5
out=0.5
length=3
delay=0
type=normal
start=bottom
```

###Special B
```
active=true 
in=0.5
out=0.5
length=3
delay=0
type=fade
start=none
```

default media extension is swf, as in hyperspin.
default alignement is bottom center.

### Tags
2 tags are available: 'completed' and 'fail'. These tags are displayed in the on-screen game info area (bottom left corner by default). You can add your own png file named as your tag name in pcca/images/tags (must be in .png format).

## Known Issues:
- axis rotation for video snap (AM does not have z-axis property for axis rotation ).

- particles animation is missing

- crash sometime occurs with some swf backgrounds, it's due to a buggy swf implementation in Attract-Mode, not the pcca script itself.


### How To Use:
1. Download the latest PCCA layout from this repository.

Optional: download video transitions pack I have prepared:
https://mega.nz/file/RBdUWTzb#e7D5HmsqTMW32Z0vKg-rfGjnC5yY-rFpETDlqSDIu_w

2. Unzip and from the 'modules' folder copy the 'hs-animate' folder to your attract/modules/ folder.
From the 'layouts' folder, copy the 'pcca' folder to your attract/layouts/ folder.

3. Within your attract/layouts/pcca/ folder, create a new folder called 'media' (for example) - this is where you will store all your Hyperspin themes.
If you want, you can place this folder outside of the 'pcca' main folder, but for the purpose of this tutorial it will be within it.

4. To make things easy, I highly recommend downloading the official Hyperspin install so we can use it's default media library as a basis for our own themes folder:
https://hyperspin-fe.com/files/file/17585-hyperspin-151-full-package/

Unzip it and copy the 'Media' folder CONTENTS to our own 'media' folder that we created within 'pcca'.
When done, you can delete the Hyperspin install folder and zip file as we have no more use for it!

If you take a look at these default themes you will see two types of folders: 'Main Menu' and folders named after systems (like 'MAME' or 'Sega CD' for example).
Within the 'Main Menu' folder you will place all the Hyperspin themes that you want 'pcca' to use for the main menu.
Each system folder will house the Hyperspin themes relevant to that system.
In both cases, the Hyperspin themes must have the same name as the System Display names in Attract Mode.


5. Launch Attract Mode and go to Attract Mode's general options screen (called "configure") by pressing the 'Tab' button:
In Configure->Startup Mode set to 'Show Display Menu' and in Displays->Display Menu Options->'Allow Exit from 'Display Menu' set to 'No'.
THIS IS MANDATORY and pcca will not work properly without this step.

6. Go to Attract Mode Configure->Displays->'Display Menu' Options->Menu Style / Layout and set it to 'pcca'.
This tells attract mode to use pcca as it's main menu theme. This is not mandatory and should be done only if you want pcca as your main menu layout as well.

7. Set each system you have in the display menu list to 'pcca' if you want this system to use Hyperspin themes. For example:
Configure->Displays->Mame->Layout and set to 'pcca'
-OR-
Configure->Displays->Nintendo Entertainment System->Layout and set to 'pcca'

8. In any of the systems that uses pcca, go to 'Layout Options' and set the 'Media Path' option to where you store
your Hyperspin themes. for example: C:\attract\layouts\pcca\media
This needs to be done ONLY ONCE. pcca will use this path as a starting point to find all the Hyperspin themes that you have.
Example: 'Configure->Displays->Mame->Layout Options->Media Path' and insert the above path to the 'media' folder.


Short Video of setting it up through the Attract Mode menus:
https://youtu.be/rH6FBcYWPSU


PCCA also knows how to work with unified video themes such as those that are available from emumovies.com. This capability comes in handy if an original hyperspin theme
doesn't work properly (there are very few of those). Just copy the unified video to the relevant system's Themes folder (for example "C:\attract\layouts\pcca\Media\Mame\Themes") making sure it has the same name as non-working theme file.

You should now be able to run and use any original Hyperspin theme on your Attract Mode setup.
