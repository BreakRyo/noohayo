# NOOHAYO 

command line interface (cli) tool made with python, it displays a banner when ever you open a new ternimal tab.

## ScreenShots -
<div style="display: flex;"><img src="screenshots/1.png" style="Height:500px"/>
<img src="screenshots/2.png" style="Height:500px;margin-left:10px"/></div>

## Usage -

### 1 Installation 
You can install it via pip :

  ``` pip install noohayo ```
### 2 Create a profile  
- when you first install the tool you will find no profile, to create one :

  ``` noohayo -n ProfileName ```
- if the profile is created successfully run this command to see all the profiles you have :

  ``` noohayo -s ```
- to select a profile as the default one run this command :

  ``` noohayo -s ProfileName ```
- if you want to locate the profiles folder for [Customization](#customization) run this command :
  
  ``` noohayo -l ```
- for more information about the command run this command :
  
  ``` noohayo -h ```    

## Customization 

- All what's being displayed in the banned is customizable, to start Customizing :
    ``` 
    Ryu@suke ~/⮞  noohayo -l
        C:\Users\user\AppData\Local\BreakRyo\noohayo\Profiles 
    ```
    after running ```noohayo -l``` you will get the location of the profiles, if you didn't find the profiles folder follow these steps first [Create a profile](#2-create-a-profile)
    - Each profile has 2 files `ProfileName.json` and `ProfileName.txt`.
- Before explaining the Customization of those two files of the profile, this is how the coloring works :
  - you will notice 色, 止 are inside `ProfileName.json` and `ProfileName.txt`.
  - `色[number]` is a where you want a certain color to start and end the previous color.
  - `止` is where you want the color to end and reset to white.

    ### ProfileName.json :
    - would look like this :
        ```json
        {
            "MyComputer": [
                "色1Ryu色2@色1Desktop-suke止",
                "色1----------------------止",
                "色2OS: 色1Windows 10 10.0.19045 SP0止",
                "色2Host: 色1DESKTOP C8VCRNP止",
                "色2Kernel: 色110.0.19045止",
                "色2Uptime:色1 19816.0 days, 7.0 hours, 8.0 minutes止",
                "色2Resolution: 色11920 x 1080                       止",
                "色2Packages: 色17 (scoop)止",
                "色2CPU: 色1AMD64 Family 23 Model 96 Stepping 1, AuthenticAMD止",
                "色2GPU: 色1AMD Radeon(TM) Graphics  止",
                "色2Memory: 色115591.43 MiB止"
            ],
            "customLeftMargin":40,
            "colors": [ // Colors the lines in MyComputer ↑
                "#aab7b8", // 色1
                "#7b7d7d" // 色2
            ],
            "logoColors": [ // Colors the lines in ProfileName.txt
                "#212425", // 色1
                "#5b6366" // 色2
            ],
            "palette": [
                "#212425",
                "#3f4447",
                "#5b6366",
                "#323739",
                "#0b0c0c"
            ]
        }
        ```
      - `MyComputer` : is the information that show in the right side of the logo, you can add/remove as many info as you want.
      - `customLeftMargin` : you can increase this option if you see a bad display of the informations, it won't be effective if any of the logo's lines is bigger than it in that case locate the big line in the logo and delete the additional spaces.
      - `colors` : contains all the colors you want the information `MyComputer` to have, you can add as many colors as you want. (read the comments in the json file above)
      - `logoColors` : contains all the colors you want the logo to have, you can add as many colors as you want. (read the comments in the json file above)
      - `palette` : the colors of the bottom right color palette.
        
    ### ProfileName.txt :
    - would look like this :
      - `色` colors from  `logoColors` in the json file, `色1` is the first color and `色2` is the second color, you can add as many colors as you want.
        ``` 
        色1                    .....                            止 
        色1              :=+*#########*+=:                      止
        色1             =#################+                     止
        色1         ::. +###**+==-==++*###* .::                 止
        色1       =####*:=+.           .=+:*####+               止
        色1     .*#####+:   色2   :*#*-    色1  :=#####*:       止
        色1    .*####*:    色2  =#######=   色1   .*####*.      止 
        色1    *####*   色2 .==-:*##+##*--==. 色1   *####*      止 
        色1   -#####. 色2 +*####*:+# *+:+####*+ 色1 .#####=     止
        色1   +####+  色2 *####==+:-:-:+==####*. 色1 +####*     止
        色1   *####=  色2 .#####+- *## -+*####.  色1 =#####     止
        色1   +####+  色2  .--===+:::-.+===--.  色1  +####+     止 
        色1    :=++=-  色2  -####-=# #=-####-  色1  :=++=-      止
        色1      :+*#   色2 .*###### ######*. 色1   **+-        止
        色1     :####*.  色2 +#####* +#####*  色1 .*####-       止
        色1     .*#####=.  ..         ..  .=#####*.             止
        色1       =######+-.           .-+######+.              止
        色1        .+#######*+==+ +==+*#######+:                止
        色1          .-*########* *########*=.                  止
        色1             .:=+*#*+. .=*#*+=:.                     止
        ```
    ### Conclusion :
    - noohayo will read the json file and gets the colors and reads the the txt that contains the logo, and replaces `色` with the colors while printing the banner.
## How to make the banner show when ever you open a new tab ?
- run this command `Notepad $PROFILE`, it will open notepad file .
- if it didn't find the file run this first `New-Item -Path $PROFILE -Type File -Force` after that `Notepad $PROFILE`.
- if you found something inside the file add this `; noohayo` otherwise `noohayo`.

        
