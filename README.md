# How to install a keystore on JKD
1. Export your certified through firefox and save it with .cer extension.

2. Go to JDK certificates directory. Example: 
   ```
   /Library/Java/JavaVirtualMachines/jdk1.8.0_181.jdk/Contents/Home/jre/lib/security*
   ```

3. Type the following command on one line:

   ```shell
   sudo keytool -import -alias example -keystore cacerts -file ~/your_cert.cer
   ```

  1. For default passworld you can use: changeit

4.  Now run keytool -list again to verify that your private root certificate was added:

     ```shell
     keytool -list -keystore cacerts
     ```
