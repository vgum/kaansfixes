Workaround for Java 8u131 “attempted to open sandboxed jar xxxxx as a Trusted-Library” error
A recent Java update to Java 8 build 131 changed what Java would accept as a “signed” JAR app. Specifically, any JAR signed with an MD5 hash will no longer be considered trusted, as the MD5 hash is now considered to be weak.

This change results in applications refusing to run with an error message like:
preloader: Delivering: ErrorEvent[url=https://XXXXX label=attempted to open sandboxed jar https://XXXXX/.jar as a Trusted-Library cause=attempted to open sandboxed jar https://XXXXX/.jar as a Trusted-Library

This occurs when the site delivering the applet is signing it with an MD5 hash, meaning that users are unable to securely access systems behind these devices.

Cisco do not currently have a solution.

The simplest workarounds are:
a) downgrade to an earlier release of Java, or
b) re-enable MD5 hash as an acceptable cipher.

Here’s how to do the latter on macOS. It involves editing the “java.security” config file which the Java Virtual Machine uses.

cd /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin/Contents/Home/lib/security
sudo vi java.security
Enter your password at the prompt so that you can edit the protected file.
Type “/jdk.jar.disabledAlg” to find the relevant line.

Current Line:
jdk.jar.disabledAlgorithms=MD2, MD5,  RSA keySize &lt; 1024

Change this to:
jdk.jar.disabledAlgorithms=MD2,  RSA keySize &lt; 1024

(i.e. remove the “MD5,” – use the cursor keys to move to the “MD5,” and press “x” to delete each character)
Save the file by holding down SHIFT and pressing “Z” twice.
