# X509-inetd-client
The x509-client that goes with the https://github.com/newsworthy39/x509-inetd-superserver

The x509 inetd-like client. The inetd-superserver, takes simple init-style sysv-scripts, and executes them, outputting any result via echo, printf back to the client. Since its a TLS-1.2 (tls1.1-compatible) TCP server, listening on a specific-port, you may use whatever protocol as you see fint. The same does the inetd-client.

# Arguments:

 -h(ost to connecto, default= "0.0.0.0", multiple delimited by a : or a ,),
  
 -p(ort, default="5001"),
 
 -d(irectory to look for scripts, to execute when called, , multiple delimited by a : or a ,)
 
 -f(files to execute, multiple delimited by a : or a ,)
 
 -c(ertificate X509 pki-bundle, default="mycrt.pem")
   
 -n(o run scripts, default off)
  
 -r(ecursive. When using directories (or multiple), recurse directories. Default off)
 
 -i(nput, from cli. null-terminated string, that allows data to be supplied before files/dirs)
 
 -s(ilent. Do not output error-messages or the likes)
 
# Compile:
 git clone https://github.com/newsworthy39/X509-inetd-client
 
 cd X509-inetd-client
 
 RELEASE="Release"
 
 cd $RELEASE && make

# Lauch example
 x509-inetd-client -c ${project_loc}/certs/mycert.pem -d ${project_loc}/etherclient.d/facts
 
