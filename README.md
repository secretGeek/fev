# fev

## aka `your-favorite-editor`

whatever platform you're on, whatever editor you use, run the `fev` command, with or without parameters as needed, and it will launch your favorite editor on that platform, configured the way you like it for the file or other parameters you provided.

install the `your-favorite-editor` package from the default package provider on your platform.

instructions are provided for Windows, MacOS, and the six most popular linux distributions. We always value more contributors.

on first run fev will notice that there is no favorite editor configured and guide you through an intelligent and user friendly menu system that helps you install and configure the editor you use most. this includes the option of storing or retrieving your own or someone else's configuration from a public network of repositories.

thereafter the command `fev` (and whatever parameters you choose to provide) will invoke your actual favorite editor, passing along your arguments in tact, unless you've chosen to alias or reduce or in some way substitute in parameters of your own using fev's lightweight macro system.

the lightweight-macro-system is also available on its own as a package on all your favorite platforms. contributors are also welcome in the lightweight-macro-system, las.

...well that's the vision.

so far i have just 1 function, on powershell, and it took me 14 hours to write it, because i had to rewrite my profile 7 times.

It looks like this:

    function Invoke-FavoriteEditor() {
      if (($null -ne $args[-1]) -and (test-path $args[-1] -pathtype Container)) {
        write-host -NoNewline "Nope. " -ForegroundColor white -nonewline
        write-host "That's a folder" -ForegroundColor red
      }
      elseif (test-path "C:\Program Files (x86)\Notepad++\notepad++.exe") {
        & "C:\Program Files (x86)\Notepad++\notepad++.exe" $args
      }  
    }

    set-alias fev Invoke-FavoriteEditor
    set-alias n fev






