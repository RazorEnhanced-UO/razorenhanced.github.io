[ Patch place for files ]( http://www.xn--gchti-gra.ch/howto.html .md)

{{ :mulpatcher_1_.zip | mulpatcher}}

{{ :legacymulconverter-n2.2_1_.zip | uop<->mul converter}}

{{ :greenbags.zip | green bags}}

{{ :greencorpse.zip | green corpse}}

{{ :journal_1_.zip | dark journal}}

{{ :justnotrees.zip | only tree stumps}}

{{ :morecolorspellicons.zip | color icons for spells, but doesn't fit this step by step}}

__Example step by step for art replacement:__
  -  make copy of UO directory for safety, my copy is named c:\UO_Copy used in following commands
  -  make a subdirectory named c:\UO_Copy\Temp
  - you need mulpatcher and LegacyMULCL-N in the temp directory from download at above web site
  - copy  artLegacyMUL.uop  to C:\UO_Copy\Temp  directory
  - Temp should look like this {{:no_trees_1.png?200|}}
  - open a command window
  - cd  C:\UO_Copy\Temp
  - LegacyMULCL-N.exe -x c:\UO_Copy\Temp
  - Now Temp looks like this {{:no_trees_2.png?200|}}
  - note you have art.mul and art.idx now .. this is only file type mulpatcher works on
  - I apply justnotrees.zip  so download that zip
  - move the unzip file ART_justnotrees to the Temp folder
  - now Temp folder looks like {{:no_trees_3.png?200|}}
  - start mulpatcher
  - click on settings tab at bottom, sometimes you have to make window bigger to see tabs
  - in Art secion (second column top place) click the ... and pick your artidx.mul and art.mul files that you made when you ran LegacyMULCL-N in step  6 {{:no_trees_4.png?200|}}
  - Click Load and wait a minute while it loads
  - click on features tab {{:no_trees_5.png?200|}}
  - in Autopatch section select justnotreesOSI.txt  file that is in your  c:\UO_Copy\Temp\ART_justnotrees directory {{:no_trees_6.png?200|}}
  - in drop down pick Art (s)
  - * Mulpatcher should look like this {{:no_trees_7.png?200|}}
  - Press start
  - * Success will present this {{:no_trees_8.png?200|}}
  - click OK
  - Back to Settings tab {{:no_trees_9.png?200|no}}
  - In that art section you did load in step 12, you now want to do save
  - Save back into Temp .. you will probably have to change up 1 directory because the save is going to open in the justnotrees directory {{:no_trees_10.jpg?200|}}
  - It will save 2 times, once for Artidx.mul and once for art.mul
  - Done with mulpatcher. click close box(edited)
  - now have to convert those mul back to uop, but it wont write over your c:\UO_Copy\Temp\artLegacyMUL.uop file so you have to delete  c:\UO_Copy\Temp\artLegacyMUL.uop first
  - back to command prompt
  - run LegacyMULCL-N.exe .\  in command prompt result will look like {{:no_trees_12.png?200|}}
  - Now you have a NEW c:\UO_Copy\Temp\artLegacyMUL.uop  file{{:no_trees_11.png?200|}}
  - copy this c:\UO_Copy\Temp\artLegacyMUL.uop back to c:\UO_Copy\artLegacyMUL.uop ... Maybe save your old c:\UO_Copy\artLegacyMUL.uop  file first(edited)
  - Change your RE startup to point to client in UO_Copy .. fill out all the stuff based on your server {{:no_trees_13.png?200|}}

**PLAY WITHOUT TREES  !!**
