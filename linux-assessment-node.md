# KodeKloud_Linux_Assesment

## Add the text KodeKloud Linux Test to a new file called test.txt inside bob's home directory.
To add the text "KodeKloud Linux Test" to a new file called `test.txt` inside Bob's home directory, you can use the `echo` command and the `>` operator to redirect the output to the file. Assuming Bob's home directory is `/home/bob`, you can run the following command:

```bash
echo "KodeKloud Linux Test" > /home/bob/test.txt
```

This command will create a new file named `test.txt` in Bob's home directory and write the specified text into it. Make sure you have the necessary permissions to write to Bob's home directory or use `sudo` if required.

### Question 3


# What is IP Address assigned to the physical interface eth1? Save the answer in a new file: /home/bob/physical_ipaddress.

To find the IP address assigned to the physical interface `eth1` and save the answer in a new file named "physical_ipaddress" in Bob's home directory, you can use the `ip` command. Here's how you can do it:

```bash
ip addr show eth1 | grep -oP 'inet \K[\d.]*' > /home/bob/physical_ipaddress
```

This command will retrieve the IP address associated with the `eth1` interface and save it in the "physical_ipaddress" file located in Bob's home directory. After running this command, you can check the "physical_ipaddress" file to find the IP address assigned to the `eth1` interface.

### Question 7


# Change the default shell for bob from BASH shell to Bourne shell.


Note: bob's password is caleston123

If you encounter the "sudo: chsh: command not found" error, it's possible that the `chsh` command is not available or not configured for use with `sudo` on your system. 

Here are some steps to resolve this issue:

1. **Check Availability of `chsh`:** First, ensure that the `chsh` command is available on your system. You can do this by running `chsh` without `sudo`. If it's not available, you might need to install it or use a different method to change the shell.

2. **Use Usermod:**
    If `chsh` is not available or if you are unable to use it with `sudo`, you can use the `usermod` command to change the default shell for a user. Here's how you can use it:

    ```bash
    sudo usermod -s /bin/sh bob
    ```

    This command will change the default shell for the user "bob" to the Bourne shell (/bin/sh).

3. **Alternative Shells:** If `/bin/sh` is not the Bourne shell (sh) on your system, you can specify the correct path to the Bourne shell. The path to the Bourne shell can vary by system, so you might need to confirm the correct path with the `which sh` command.

    For example, if the Bourne shell is located at `/bin/ash`, you would use:

    ```bash
    sudo usermod -s /bin/ash bob
    ```

Make sure to replace `/bin/ash` with the correct path to the Bourne shell on your system if it's different from `/bin/sh`.

### Question 9


# The student-node server is supposed to run an Apache service. However, it has been configured incorrectly. Fix the issues listed below:
The service is running with user: apache and group: apache
The service should run on port 8081


If the issues are fixed, the application will be accessible by clicking on HTTP Server Test button that is located above the terminal.

Note: The http configuration file is located at: /etc/httpd/conf/httpd.conf


To fix the issues with the Apache service on the "student-node" server, you need to make changes to the Apache HTTP server configuration file located at `/etc/httpd/conf/httpd.conf`. Specifically, you'll need to set the user and group to "apache" and change the listening port to 8081. Here are the steps to do this:

1. Open the Apache HTTP server configuration file for editing using a text editor. You'll need root permissions, so use `sudo` with your preferred text editor. For example, you can use `nano`:

    ```bash
    sudo nano /etc/httpd/conf/httpd.conf
    ```

2. Inside the configuration file, locate the lines that specify the `User` and `Group` directives. Change both the `User` and `Group` to "apache". It should look like this:

    ```apache
    User apache
    Group apache
    ```

3. Next, locate the line that specifies the listening port and change it to 8081. Look for the `Listen` directive:

    ```apache
    Listen 8081
    ```

4. Save the changes in your text editor (e.g., in `nano`, press `Ctrl + O`, then press Enter, and finally press `Ctrl + X` to exit).

5. Restart the Apache service to apply the changes:

    ```bash
    sudo systemctl restart httpd
    ```

With these changes, the Apache service on the "student-node" server will run with the user and group set to "apache" and listen on port 8081. You should be able to access the application by clicking on the "HTTP Server Test" button.






```ruby

```
