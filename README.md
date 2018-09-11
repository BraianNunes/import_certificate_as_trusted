# How to install a keystore on JKD
1. Export your certified through firefox and save it with .cer extension.

2. Go to JDK certificates directory. Example: 
   ```
   /Library/Java/JavaVirtualMachines/jdk1.8.0_181.jdk/Contents/Home/jre/lib/security
   ```

3. Type the following command on one line:

   ```shell
   sudo keytool -import -alias example -keystore cacerts -file ~/your_cert.cer
   ```

  4. For default passworld you can use: changeit

5. Now run keytool -list again to verify that your private root certificate was added:

     ```shell
     keytool -list -keystore cacerts
     ```

# How to list all alias stored
You can run the following command to list the content of your keystore file (and alias name):
   ```
   keytool -v -list -keystore .keystore
   ```

If you are looking for a specific alias, you can also specify it in the command:
   ```
   keytool -list -keystore .keystore -alias foo
   ```

If the alias is not found, it will display an exception:
   ```   
   keytool error: java.lang.Exception: Alias does not exist 
   ```

# How to Remove Imported Certificates From Java Keystore

If a problem occurred during the PatchPro installation, you might just remove the certificates and import them again.
   ```
    1. Become superuser.

    2. Remove the previously imported certificates.

    # keytool -delete -alias your_cert -keystore cacerts
    Enter keystore password:  changeit
   ```
