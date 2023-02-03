# Creating a Shell Script

Hello all, thank you for reading my very important and beneficial blog that no one else in the world could have written as I have immense knowledge on the topic of shell scripting.

As a starting web developer I am constantly creating new projects to test various website ideas/layouts. Doing this by hand takes a LOT of time; time that I could be using to create more useful websites and scritps. So to counteract this massive problem I've written up a short script that does it automatically.

Here is the full script:

```
    #! bin/bash

    # Prompt user for project name
    echo "Enter the name of your project: "
    read project_name

    # Make Folders
    mkdir $project_name
    cd $project_name
    mkdir styles img js 

    # Make files
    touch index.html
    touch styles/style.css
    touch js/main.js

    # Write base index.html file
    echo "<!DOCTYPE html>" >> index.html
    echo "<html>" >> index.html
    echo "  <head>" >> index.html
    echo "    <meta charset=\"utf-8\">" >> index.html
    echo "    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">" >> index.html
    echo "    <link rel=\"stylesheet\" href=\"styles/style.css\">" >> index.html
    echo "  </head>" >> index.html
    echo "  <body>" >> index.html
    echo "    <h1>If this is red, css is working.</h1>" >> index.html
    echo "    <h2 id='blue'>If this is blue, js is working.</h1>" >> index.html
    echo "    <!-- loads javascript --> " >> index.html
    echo "    <script src='js/main.js'></script> " >> index.html
    echo "  </body>" >> index.html
    echo "</html>" >> index.html

    # Write styles
    echo "h1 {color:red;}" >> styles/style.css
    echo "progress,sub,sup{vertical-align:baseline}*,::after,::before{box-sizing:border-box}html{line-height:1.15;-webkit-text-size-adjust:100%;-moz-tab-size:4;tab-size:4}body{margin:0;font-family:system-ui,-apple-system,'Segoe UI',Roboto,Helvetica,Arial,sans-serif,'Apple Color Emoji','Segoe UI Emoji'}hr{height:0;color:inherit}abbr[title]{text-decoration:underline dotted}b,strong{font-weight:bolder}code,kbd,pre,samp{font-family:ui-monospace,SFMono-Regular,Consolas,'Liberation Mono',Menlo,monospace;font-size:1em}small{font-size:80%}sub,sup{font-size:75%;line-height:0;position:relative}sub{bottom:-.25em}sup{top:-.5em}table{text-indent:0;border-color:inherit}button,input,optgroup,select,textarea{font-family:inherit;font-size:100%;line-height:1.15;margin:0}button,select{text-transform:none}[type=button],[type=reset],[type=submit],button{-webkit-appearance:button;appearance:button;}::-moz-focus-inner{border-style:none;padding:0}:-moz-focusring{outline:ButtonText dotted 1px}:-moz-ui-invalid{box-shadow:none}legend{padding:0}::-webkit-inner-spin-button,::-webkit-outer-spin-button{height:auto}[type=search]{-webkit-appearance:textfield;appearance:textfield;outline-offset:-2px}::-webkit-search-decoration{-webkit-appearance:none;appearance:none;}::-webkit-file-upload-button{-webkit-appearance:button;appearance:button;font:inherit}summary{display:list-item}html{font-size:62.5%;}body{font-size:1.6rem;}img{width:100%;height:auto;user-select:none;}button{color:inherit;}a,button{touch-action: manipulation;}svg{height:100%;width:100%;fill:currentColor;pointer-events:none;}iframe,video{height:100%;width:100%}" >> styles/style.css

    # JS test
    echo "document.getElementById('blue').style.color = 'blue' " >> js/main.js;

    # Open files
    code index.html
    code styles/style.css
    code js/main.js

    open index.html
```

Now I will further explain the script and what it does.

```
    # Prompt user for project name
    echo "Enter the name of your project: "
    read project_name
```

These lines of code print "Enter the name of your project: " into the terminal and waits for the user to type the name of the project into the terminal

```
    # Make Folders
    mkdir $project_name
    cd $project_name
    mkdir styles img js 
```

These lines of code create a folder (the project folder) with the name that the user typed into the termianl, then moves into that project folder, and makes three more folders within the project folder.

```   # Make files
    touch index.html
    touch styles/style.css
    touch js/main.js
```

The script then creates files within each of the three new folders we made within the project folder

```    # Write base index.html file
    echo "<!DOCTYPE html>" >> index.html
    echo "<html>" >> index.html
    echo "  <head>" >> index.html
    echo "    <meta charset=\"utf-8\">" >> index.html
    echo "    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">" >> index.html
    echo "    <link rel=\"stylesheet\" href=\"styles/style.css\">" >> index.html
    echo "  </head>" >> index.html
    echo "  <body>" >> index.html
    echo "    <h1>If this is red, css is working.</h1>" >> index.html
    echo "    <h2 id='blue'>If this is blue, js is working.</h1>" >> index.html
    echo "    <!-- loads javascript --> " >> index.html
    echo "    <script src='js/main.js'></script> " >> index.html
    echo "  </body>" >> index.html
    echo "</html>" >> index.html
```

It then fills the index.html file with a basic starter/outline including a links to the style.css and main.js files

```
 # Write styles
    echo "h1 {color:red;}" >> styles/style.css
    echo "progress,sub,sup{vertical-align:baseline}*,::after,::before{box-sizing:border-box}html{line-height:1.15;-webkit-text-size-adjust:100%;-moz-tab-size:4;tab-size:4}body{margin:0;font-family:system-ui,-apple-system,'Segoe UI',Roboto,Helvetica,Arial,sans-serif,'Apple Color Emoji','Segoe UI Emoji'}hr{height:0;color:inherit}abbr[title]{text-decoration:underline dotted}b,strong{font-weight:bolder}code,kbd,pre,samp{font-family:ui-monospace,SFMono-Regular,Consolas,'Liberation Mono',Menlo,monospace;font-size:1em}small{font-size:80%}sub,sup{font-size:75%;line-height:0;position:relative}sub{bottom:-.25em}sup{top:-.5em}table{text-indent:0;border-color:inherit}button,input,optgroup,select,textarea{font-family:inherit;font-size:100%;line-height:1.15;margin:0}button,select{text-transform:none}[type=button],[type=reset],[type=submit],button{-webkit-appearance:button;appearance:button;}::-moz-focus-inner{border-style:none;padding:0}:-moz-focusring{outline:ButtonText dotted 1px}:-moz-ui-invalid{box-shadow:none}legend{padding:0}::-webkit-inner-spin-button,::-webkit-outer-spin-button{height:auto}[type=search]{-webkit-appearance:textfield;appearance:textfield;outline-offset:-2px}::-webkit-search-decoration{-webkit-appearance:none;appearance:none;}::-webkit-file-upload-button{-webkit-appearance:button;appearance:button;font:inherit}summary{display:list-item}html{font-size:62.5%;}body{font-size:1.6rem;}img{width:100%;height:auto;user-select:none;}button{color:inherit;}a,button{touch-action: manipulation;}svg{height:100%;width:100%;fill:currentColor;pointer-events:none;}iframe,video{height:100%;width:100%}" >> styles/style.css
```

Next, it writes a generic set of styles into the style.css file

```
    # JS test
    echo "document.getElementById('blue').style.color = 'blue' " >> js/main.js;
```

The script then writes a test into the javascript that makes a line of text in the html the color blue

```
    # Open files
    code index.html
    code styles/style.css
    code js/main.js

    open index.html
```

Finally the script opens each of the files in VS Code, and the index.html file in a browser.