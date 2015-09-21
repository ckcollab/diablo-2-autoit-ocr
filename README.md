# diablo-2-autoit-ocr
A Diablo 2 AutoIT OCR I wrote when I was 12


## How it works

I noticed a pattern in the Diablo 2 font. 

 1. The pixel colors are fairly unique. You can tell apart a normal, magic, rare, set, and unique item easily
 2. The spacing between characters is at least 2 pixels
 3. The spacing between lines is at least 2 pixels
 
Using this pattern I was able to find each line and each character, then make a unique ID from each character by mapping from the top-left most pixel and creating a pattern based on that. See the character definition file to see what the character mappings look like.


## Usage

Get all of the lines

    $lines = GetLines($StartX, $StartY, $EndX, $EndY, $Color)

Read the characters in each line

    For $LineNum = 1 to $Line[0][0]
        $Find = GetCharacters($Line[$LineNum][0], $Line[$LineNum][1], $Line[$LineNum][2], $Line[$LineNum][3], $Pixel)
        ...
    Next
      
