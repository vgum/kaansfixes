You can use homebrew installer.

First, make sure you have Xcode installed (it’s free in the Mac App Store) with its optional command line tools installed (in Xcode go to Preferences, Downloads, and click “Install” next to Command Line Tools).

Next, install Homebrew by running the following in a terminal:
ruby -e “$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)”

Note : Note: The above command is changed by the Homebrew guys from time to time.
If the above command doesn’t seem to be working, check the Homebrew website for the latest incantation: http://brew.sh/
Follow the instructions and enter your system password when prompted.

Once Homebrew is installed, it’s super easy to install Scala by typing the following in a terminal: brew install scala
Homebrew will install Scala in /usr/local

Or you can install it manually
Download scala-X.XX.tgz from the official site.

Unzip archive and move it to /usr/local folder
sudo cp -R scala-X.XX /usr/local/scala

Open your .bash_profile file :
sudo nano ~/.bash_profile

Add scala/bin folder to your PATH
export PATH=/usr/local/scala/bin:$PATH

Save it and restart your terminal. Now you can check if scala works by simply typing scala in console.
If everything was setup correctly you should see this on your screen :
Welcome to Scala version 2.11.0 (Java HotSpot(TM) 64-Bit Server VM, Java 1.7.0_51). Type in expressions to have them evaluated.
Type :help for more information.
scala>
