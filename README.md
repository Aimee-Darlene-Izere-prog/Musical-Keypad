Musical Keypad Project in LC-3 Assembly programming

Author : AIMEE DARLENE IZERE

ABOUT THE PROJECT 

This LC3 code reads a key that is being played from a keypad and then play a corresponding note to the speaker 
Throughout this code, I use different memory-mapped I/O addresses to get data from the keypad and play the note to the speaker. 
Those addresses are labeled as KPDR, FGCR , FGDR , KPSR, and GLCR

INPUTING : Getting the key value from the keypad

The ASCII value of the current key being pressed is stored in the memory-mapped I/O address KPDR
If there is no key that is pressed, then the main program keeps looping
if KPDR = 0, then no key is pressed or the key has been released
ELSE, we play the note of the key that is pressed

GETTING THE FREQUENCY FOR THE OUTPOUT TONE

Once we have confirmed that the is a key that is currently being pressed, then, we look up its frequency in FREQ_TABLE and use FGCR to play that note

START/STOP PLAYING A NOTE

The memory-mapped I/O FGCR controls wehn to stop and start playing the note
if FGCR = 1, then we start playing a key note
else if FGCR = 0, then we stop playing a key note

RELEASING A KEY

After we start playing a key note, we keep checking to see if the key has been released.
Once the key is released, the function generator stops playing 
The memory-mapped I/O address KPSR keep track for how long a key has been pressed
if KPSR = 0, then the key is released and the program stops playing 
