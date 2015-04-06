>**Notice:** This tutorial assumes that you are familiar with Eclipse and MCP.![](https://ga-beacon.appspot.com/UA-52838431-1/GitHub/wiki/Debugging-Wurst-in-Eclipse?pixel)

1. **Install [MCP](http://www.modcoderpack.com/website/releases)** like you would normally.
2. **Apply the [patch](https://github.com/Wurst-Imperium/Wurst-Client/blob/master/patch/minecraft.patch)** to your decompiled Minecraft source code using [Git](https://windows.github.com/). The Git command for that is  
`git apply --ignore-space-change --ignore-whitespace minecraft.patch`.
3. **Create a clone** of Wurst. This is the tricky part, so read carefully!
  - In Eclipse, go to `File>Import...>Git/Projects from Git>Clone URI`.
  - Type `git@github.com:Wurst-Imperium/Wurst-Client.git` into the first text field. The rest will be filled out automatically.
  - Click `Next >` until it asks you for a wizard. Select `Use the New Project wizard` and click `Finish`.
  - A new window will open. Select `Java/Java Project` and click `Next >`.
  - Give your project a name and change the project location to the `Wurst Client` folder inside of your clone.  
*Example:* If your clone is at `C:\Users\Octocat\GitHub\Wurst-Client-clone`, your project location is at `C:\Users\Octocat\GitHub\Wurst-Client-clone\Wurst Client`.
  - Click `Finish`.
4. **Add all libraries** that Minecraft uses to the Build Path. They are all inside of `YOUR_MCP_FOLDER\jars\libraries`.
5. **Add the [Slick2D library](http://slick.ninjacave.com/)** as well.
6. **Add the Minecraft code:**
  - Create a linked folder in the root of your project.
  - Link it to your patched Minecraft source code.
  - Turn it into a source folder.
  - Enable `Ignore optional compiler problems` in the properties of the folder.
7. **Change the compliance level** to `1.6` if you still have errors. You can do that in the project properties.
8. **That's it!** You should now be able to create a launch config and debug Wurst without any errors or warnings.

>**Notice:** Contributing changes in the vanilla MC source code requires some extra steps. Read [#412](https://github.com/Wurst-Imperium/Wurst-Client/issues/412) for more information.