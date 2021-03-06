# Problem Set 0.5

## Due Friday, August 31, at 11:59pm local time

### Part 1: Access the Problem Set

1. Create a folder on your computer for this class called CS2 or CS1102. I have mine on my Desktop so it's easy to find.

2. By now you should have received an email with an invitation to accept Problem Set 0.5. If you didn't receive the email or can't find it, you can find the link to the invitation on Canvas. Accept the invitation, which will create a repository just for you to use to complete this assignment.

3. Follow the link to the repository that was created, and locate the green "Clone or download" on the right. Click that button, and then copy the the URL beginning with ``https://`` that appears, as shown below.

<img src="img/clone.png" width="700"  />

4. You will need the URL in Part 5, so paste it somewhere you can easily access it in a few minutes. And of course, you can always find it again by just going to github.com and selecting this problem set repository. 

### Part 2: Install Java SE

1. Although there are several newer versions of Java, we'll be using Java 8. Download the Java SE Development Kit 8u181 (the last three numbers might be different, that's okay!) for your operating system from [here](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

2. After you download the .dmg (Mac) or .exe (Windows), double-click it to start the installation. Click where you need to click to complete the installation, and you should be all set. If something goes wrong, contact a TA.

### Part 3: Install the textbook library

1. Installing `algs4.jar`

One of the nice things about the Sedgewick and Wayne Algorithms book (which we'll call SW for short) is the extensive software library developed by the authors. The library is housed in the Java archive `algs4.jar`.  The simplest option for setting this up is to use the automated installation scripts developed by SW. **Note: Follow ONLY step 0, starting from the third bullet, of the instructions there**.

+ [MacOS](https://algs4.cs.princeton.edu/mac/)
+ [Windows](https://algs4.cs.princeton.edu/windows/)

Following the instructions **only for Step 0 starting from the third bullet** and executing the downloaded installer script on your computer will download the `algs4.jar` library for you (along with other tools). **If you run into problems on Mac, please have a close look at the installation FAQs. Mostly likely you'll have to move the algs4.app to another folder and try again, but if that doesn't work, follow the instructions for the sudo command at the end of installation FAQs.**

2. Setting the `CLASSPATH` variable

Java needs to know where to look for libraries, like the `algs4.jar` file you just installed, that are not included with the Java installation. Java uses a special system environment variable called `CLASSPATH` to tell Java where to search for such libraries. The `CLASSPATH` variable needs to be set correctly in order to compile and run your Java code. Setting this variable varies depending on whether you are using MacOS or Windows.

#### MacOS

The easiest way to set the `CLASSPATH` is to use the *unix shell* that comes installed on MacOS in the Terminal app. You can find the Terminal app in your Applications folder, or you can search for it using Spotlight by clicking the magnifying glass in the upper right corner of the screen. Launch Terminal, and you'll see something like this:

<img src="img/terminal.png" width="600"  />

Terminal provides a bash shell by default. The shell is waiting for you to type a unix command. You don't have to master unix for this course, but it would be helpful to study it if you aren't familiar with it. To learn more, Google a tutorial or follow along with the [very basic tutorial I use in my other classes](https://people.rit.edu/emilypx/lab1.html) (no need to turn it in, of course).

For now type **exactly** what is shown to the right of the `$` prompt. Feel free to copy and paste, but don't include the `$`!:

```bash
$ cd
$ echo "export CLASSPATH=\$CLASSPATH:/usr/local/algs4/algs4.jar" >> ~/.bash_profile
$ source .bash_profile
```

The first command makes your home directory (i.e.,  `/Users/yourusername/`) the current working directory. The second command appends a key line to your bash startup file (``.bash_profile``) setting your `CLASSPATH` variable. The third command executes that startup file. That same startup file will be automatically executed each time you launch the Terminal app. 

Confirm that Java is installed by typing

```bash
$ javac -version
```

you should see something like

```bash
javac 1.8.0_181          # it doesn't matter if the last 3 digits differ
```

Confirm that your `CLASSPATH` variable is properly defined by typing

```bash
$ echo $CLASSPATH
```

you should see something like

```bash
/usr/local/algs4/algs4.jar
```

If you have problems with any of these steps, reach out to a TA or the instructor. If it worked, move on to Part 4 and skip over the Windows instructions, below.

#### Windows

What follows comes from the instructions on SW's algs4 website for adding the `algs4.jar` library to the `CLASSPATH` for Windows.

1. Windows 7: Start -> Computer -> System Properties -> Advanced system settings -> Environment Variables -> User variables -> CLASSPATH. Windows 8 and 10: Search -> System (Control Panel) -> Advanced system settings -> Environment Variables -> User variables -> CLASSPATH.

2. Prepend the following to the beginning of the `CLASSPATH` variable:

   ```bash
   C:\Users\username\algs4\algs4.jar;
   ```

   where `username` is **your username** on your computer. A semicolon separates entries in the `CLASSPATH` so don't forget include it when you paste in the above text.

3. Click OK three times.

*NOTE:* If you don't see a variable named `CLASSPATH`, click **New** and in the popup window enter `CLASSPATH` for the variable name. Then, perform the instructions above. If you have problems with any of these steps, reach out to the Windows expert TA, Anthony.

### Part 4: Install and configure Atom

In this course we'll be using GitHub's Atom editor to write our Java code, and we'll be using git and GitHub to distribute and collect problem sets. Fortunately, git and GitHub are nicely integrated into the Atom editor. You can find a lot of [video tutorials on using Atom](https://www.leveluptutorials.com/tutorials/atom-editor-tutorials) though you probably won't need much guidance since we'll be using only a small part of its functionality.

1. [Download Atom](https://atom.io). Double click the downloaded file unzip it (if necessary), then move Atom to a place on your computer where it will be easy to find (e.g., in the Applications folder or on your desktop).

2. Launch Atom. There are a few tabs or frames that open automatically, which you can close by clicking the "X" in the upper right corner of the tab or frame. (If all these windows keep popping up when start Atom, you can turn them off in the Preferences and by clicking on the ``Do not show Welcome message`` on the Welcome tab.)

3. You now need to install an Atom package that will customize Atom for use in this class. From Atom's menu bar, click the Atom menu, and then select Preferences to open the Settings menu. You can also access the settings via a keyboard shortcut: in MacOS hold down the ``command``key and type a comma; in Windows, hold down the ``control`` key and type a comma.

<img src="img/atommenu.png" width="300"  />

4. On the left of the Settings area, you’ll see a menu with items like Core, Editor, URI Handling, and so on. Click on the menu item that says Install, which has a plus-sign icon next to it.

<img src="img/install.png" width="600"  />

5. In the search box that appears, enter ``platformio-ide-terminal``. Click Install button for ``platform-ide-terminal``, and wait for installation to complete.

### Part 5: Get a local copy of the repository from GitHub

1. In Atom, go to ``Packages -> Command Palette -> Toggle``.

2. In the pop-up window that opens, start typing ``GitHub``, and the GitHub: commands will appear. Select ``GitHub: Clone``.

3. Paste the URL from Part 1 in the first box, and the path to the **course folder** you created to Part 1 in the second box.

4. Click the ``Clone`` button. This will copy your personal ps0.5 repository to your computer. 

**NOTE:** Some students have reported difficulty using the usual GUI way to clone a repository in Atom, described above. If you end up with an empty repository following theese instructions, do one of the following (1) use the GitHub Desktop app to do your cloning (recommended for Windows users); or (2) go to ``Packages -> platform-ide-terminal -> New Terminal``; then type ``git clone`` followed by the link to your repository, which will ask for your GitHub username and password, and will clone the repo to your home directory. 


### Part 6: Edit a file and push edits to GitHub

1. If you just did Part 5, you should see the contents of the repository in Atom. If you can't see the ps0.5 repository, then go to `File -> Open`, and navigate to your class folder, where you should find your local respoitory. Select it and click ``Open``.

2. You should now see something like this, below, with a tree structure showing the files in your current directory in the left pane and an empty pane on the right. (Feel free to close any of the pesky Welcome tabs and panes that Atom likes to open up.)

<img src="img/atom1.png" width="700"  />


3. Click on ``src`` to view the code for this assignment, then click on ``HelloWorld.java``. code will appear in the panel on the right. Find where you see this in the code:

```bash
System.out.println("Hello, World!")
```

Replace the words ``Hello, World!`` with your favorite greeting.

4. From the ``File`` menu, select ``Save`` (or use your usual keyboard shortcut for saving, like command-s in MacOS or control-s in Windows).

5. Go to ``Packages -> GitHub -> Toggle Git Tab``.

6. The Git tab will open, and you'll see something like this, below. Click ``Stage all``.

<img src="img/atom2.png" width="700"  />

7. Type a comment explaining what you did and why where it says ``Commit message``.

8. Click ``Commit to master``.

9. Click the ``Push`` on the right in the bottom menubar, between ``master`` and ``files``. 

9. Go to GitHub and find your respository for this problem set. You should see the changes reflected in your problem set repository and see ``last updated 1 minute ago`` (or thereabouts). This is what we will grade. Congratulations! You are ready for Problem Set 1.


