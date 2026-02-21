# vsif2vcd

This utility initially written by SiPlus allows for decompiling scenes.image file to original VCD faceposer files.
The expectations are to run on any computer that HLLib supports.

# Compiling
- 1. Install CMake. Make sure it is working in command prompt (Installed correctly in PATH)
- 2. Run cmake in command prompt and make sure to specify the visual studio version you are using (or other compiler).
- Here is an example of a correct way to build it in cmake in command prompt: 

- cmake -S "pathtofolder\vsif2vcd" -B "pathtofolder\vsif2vcd\build" -G "Visual Studio 17 2022"

- 3. You should successfully now have the visual studio (or other compiler) files compiled. Go into the build folder and open the project file (.sln for Visual Studio, I'm not sure what it'd be for another program)
- 4. In your compiler, make sure "/FORCE:MULTIPLE" is in the command line options for the linker, otherwise it will error.
- 5. Compile the ALL_BUILD option, it will compile everything. If it doesn't succeed at first, try again and if it errors again compile each part individually. Last but not least, find where it saved the .dll file and .exe file (use your build in search program in your pc)
- 6. Copy them both to a suitable folder and start using the program! Good Luck!

# TODO
- [X] Make LZMALib static and use its API instead.
- [X] Parse scripts/talker/response_rules.txt file to get scene values
- [X] SteamPipe update brought necessary files packed. Unpack those via HLLib.
- [X] We do not wanna dirty the game directory. Make temporary directory, where we do all work.
- [ ] Try to use sourcepp.
- [ ] TF2 item parsing.
- [ ] Due to gameinfo.txt mounting order, and way those files are mounted, scenes.image file contains compound data for all directories mounted. This is problematic beacuse only top mod directory has maps. Most of those games have Half-Life 2 scenes. Episode Two has additionally Episode One scenes. We need to resolve this.


# Source for reference
Reference source is at src/old/Vsif2vcd.c
