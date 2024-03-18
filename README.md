# SELinux Port Exception


---


1. Check the Current SELinux Policy:

Before adding an exception, it's a good idea to check if there are existing SELinux policies that may be affecting the port. You can use the semanage command to list the SELinux port type definitions:

	sudo semanage port -l


2. Add a SELinux Port Exception:

Use the semanage command to add an exception for your desired port. Replace <your_new_port> with the port number you've configured for Apache Tomcat. For example, if you changed the port to 8888:


	sudo semanage port -a -t http_port_t -p tcp <your_new_port>
 
This command associates the http_port_t SELinux type with the specified TCP port.

3. Verify the New SELinux Policy:

You can verify that the exception has been added successfully by listing the SELinux port definitions again:

	sudo semanage port -l






