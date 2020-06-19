

> I was helping Skywire (dinoxel) translate Terraria to French but that
> project is dead now because  [Terraria will add official high quality
> translations](https://twitter.com/Cennxx/status/806506668758540288).  
> One issue we ran into was the display of special characters. With the
> default font they look terrible, so we had to figure out how to
> replace the ugly characters with pretty ones.   The first thing we
> tried was editing the unpacked sprite and repacking it (using 
> [XNBNode](https://github.com/draivin/XNBNode)) but this was a lot of
> effort and the spacing was off. The next attempt was using an
> assortment of spritefont creation tools but they all had one fault or
> another. So after trying and failing with MonoGame Pipeline we ended
> up going with  [XNA Game Studio
> 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=23714)  (XNA Game Studio does not support Visual Studio 15, use  [Visual C#
> 2010
> Express](https://stackoverflow.com/questions/8119698/visual-c-sharp-2010-express-full-download)
> instead).      Create .xnb font file  
> 
> 1.  Open Visual C# 2010 Express
> 2.  File -> New Project...
> 3.  Make a new "Windows Game (4)"
> 4.  Right click the Content Item in the Solution Explorer and do "Add -> New Item..."
> 5.  Choose sprite font and name it one of the following:
>     1.  Combat_Crit.spritefont
>     2.  Combat_Text.spritefont
>     3.  Death_Text.spritefont
>     4.  Item_Stack.spritefont
>     5.  Mouse_Text.spritefont
>     6.  Title_Font.spritefont
> 6.  Edit FontName, Andy Bold is just "Andy"
> 7.  You probably want to edit the size and expand the character region (French works perfectly with &#32; to &#342; )
> 8.  Press the green play button or hit F5 to start debugging
> 9.  Locate the output folder, for me it's "D:\Documents\Visual Studio 2010\Projects\WindowsGame1\WindowsGame1\WindowsGame1\bin\x86\Debug\Content"
> 10.  Copy the created .xnb files to the Terraria Content folder
> 
>    Info about the ingame font (mostly  [Andy
> Bold](http://ufonts.com/fonts/andy-bold.html))  
> 
> 1.  Combat_Crit.spritefont (unknown)
> 2.  Combat_Text.spritefont (unknown)
> 3.  Death_Text.spritefont (Andy Bold, size 40)
> 4.  Item_Stack.spritefont (Andy Bold, size 14)
> 5.  Mouse_Text.spritefont (Andy Bold, size 17 (needs to be 17 with Andy Bold, 16 has spacing issues with <i>))
> 
>    Where fonts are used ingame (easiest access)  
> 
> 1.  Combat_Crit and Combat_Text are used when you take damage or heal
> 2.  Death_Text is used on the main menu
> 3.  Item_Stack is used on the achievements page
> 4.  Mouse_Text is used where you select your character (Play, HP, Mana, etc.)
> 5.  Title_Font is currently unused
> 
>    Tip: Change this code in Game.cs (automatically moving the files
> would be even better)  
> 
> Code:
> 
> ``` protected override void Initialize() {
>     base.Initialize();
>     Process.Start(@"D:\Documents\Visual Studio 2010\Projects\WindowsGame1\WindowsGame1\WindowsGame1\bin\x86\Debug\Content");
> // replace with your content folder
>     Process.Start(@"C:\Program Files (x86)\Steam\steamapps\common\Terraria\Content\Fonts"); // replace with
> your Terraria folder
>     Exit(); } ```

Source: [https://forums.terraria.org/index.php?threads/xnb-spritefont-guide.52416/](https://forums.terraria.org/index.php?threads/xnb-spritefont-guide.52416/)
___

> This tool generates .xnb font files for Terraria 1.3.5.X, which
> doesn't need XNA Game Studio.      If you can run Terraria, then you
> can use this tool.      You simply need to create your description
> file (.dynamicfont) on the directory of the tool, and run 
> **DynamicFontGenerator.exe     
> _A simple description file can be found here:  [https://gist.github.com/mistzzt/9adc21f862859064bc60271f9e6e6c68](https://gist.github.com/mistzzt/9adc21f862859064bc60271f9e6e6c68)_
> 
> _Source code:  [https://github.com/mistzzt/DynamicSpriteFontGenerator](https://github.com/mistzzt/DynamicSpriteFontGenerator)_**

Source: [https://forums.terraria.org/index.php?threads/dynamicspritefontgenerator-0-4-generate-fonts-without-xna-game-studio.57127/](https://forums.terraria.org/index.php?threads/dynamicspritefontgenerator-0-4-generate-fonts-without-xna-game-studio.57127/)