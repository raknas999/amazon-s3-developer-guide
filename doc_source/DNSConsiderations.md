# DNS Considerations<a name="DNSConsiderations"></a>

 One of the design requirements of Amazon S3 is extremely high availability\. One of the ways we meet this requirement is by updating the IP addresses associated with the Amazon S3 endpoint in DNS as needed\. These changes are automatically reflected in short\-lived clients, but not in some long\-lived clients\. Long\-lived clients will need to take special action to re\-resolve the Amazon S3 endpoint periodically to benefit from these changes\. For more information about virtual machines \(VMs\)\. refer to the following: 

+  For Java, Sun's JVM caches DNS lookups forever by default; go to the "InetAddress Caching" section of [the InetAddress documentation](http://docs.oracle.com/javase/1.5.0/docs/api/java/net/InetAddress.html) for information on how to change this behavior\. 

+  For PHP, the persistent PHP VM that runs in the most popular deployment configurations caches DNS lookups until the VM is restarted\. Go to [the getHostByName PHP docs\.](http://us2.php.net/manual/en/function.gethostbyname.php) 