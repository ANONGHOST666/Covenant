# Covenant

## [DOWNLOAD SOURCES HERE](https://mega.nz/#!i6ZS3ACQ!qlHyYRdOWZMjN8hKvqtjVkklelwAXXik152-bwDiDyE)

So I'm not going to write down a user guide for this project since
that is a Poc.

But let's start talking about some things to make everything clear.

This is a Proof Of Concept of a **meterpreter** clone. Do you know that powerful
malware included inside Metasploit Framework that you can drop using exploits,
bugs, and so on ? Here it is the little brother of it.

## Why this project ?

I tryed so long to : compile it, debug it. I tried to figure out how it works but I'm too stupid and I wanted a fully custom server side so I decided to write a my own meterpreter. So based on the work of **Stephen Fewer** I wrote down this source.

![cli1](http://i68.tinypic.com/30u3joh.png)

## Basically how it works ? 

Using the DLL injection technique it infects a process in order to run the reverse shell and connect back to the C&C.. of course I could give you a ultra technical explaination talking about the RemoteThread or CreateThread event and so on but Stephen worked so hard on this so just bounce on his project and read there everything. Some days ago a dude called SandBox..something created a Poc using the same technique merged to a 0day exploit giving to the process elevated privileges ... You can google it and finding the sources it might be an extra feature but in this project I don't want anything else. So the DLL Injection allows to avoid .. more less to be detected by AVs, IDs, ... In order to not create another process for the malware, this also is called FILELESS malware so the DLL gets executed in memory by the infected process so nothing will be written on the HD, this will make the reverse engineering more difficult ( obfuscate the DLL and you rock. ) 

## Personal Considerations

I tried to mix some other functions taken from other famous malwares, but it's still a Poc so this is not completed but some fts such as persistence installation only when the computer gets shutted down or native process injection are taken from other guys ( Stuxnet, ...) I wanted to created something really powerful but I don't have time now to complete it.

## The cool thing : the server

I wrote down a really cool but simple GUI ( metasploit style ) that you can extend with other modules, payloads, ... everything has colors .. yay... but i tryed to make a C&C really well built ... some codes or something could be useless but i keep remind you that is a Poc. The C&C is written in Python 2.7 it requires : colorama and some other libraries .. just compile it and you'll see. The use is pretty simple, 'cause it's just like MSF but type '*HELP*' in any moment to figure how where the F*ck did you landed.

## The Client

The client is written in C++ and you can use VS2017-18 without troubles, or I used it so...yes you have to understand how to link the *base64.h* to the project but once you made it will works.

Once you compiled it just go in the **bin** folder and run you version : x32, x64 or arm ( i think it doesn't work properly..dunno). It will get the "explorer.exe" process and it will inject there the DLL, once it finishes explorer.exe will restart slowly so do not panic! At least try it on another process. To use the Stuxnet method ( inject in : lsass.exe, or others remember the Admin privileges ) 

## Final Thoughts

I'm releasing this Poc 'cause i saw that there's not any kind of version online, so maybe it could return useful for someone, if you implement it please share and merge so the project can live, of course this is only for study purposes no hacking, no sh*t, everything is up to you and I don't take any kind of responsability of your actions.

If you got questions, send me a pm on twitter (find the link on my github page) or contact me on my forum [ZetaBay.net](http://zetabay.net) and enjoy it.
