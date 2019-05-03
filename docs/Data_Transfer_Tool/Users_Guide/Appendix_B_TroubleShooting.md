#Appendix_B_Troubleshooting

##Speed Performance During Download
The Data Transfer Tool does have two performance tuning options that are presented during download operations.  The two options are presented below:
  --n (number of threads used)
  --http-chunk-size (can be used in large downloads)

The "--n" option assists with assigning the number of threads to the download process.  The default is 4 and can't be lowered below three.  The --http-chunk-size setting can improve performance but we don't provide any hard settings due to the eclectic nature of client networks and their connections to the internet but instead we encourage clients to experiment with changing the default setting of 1048576 bytes to larger size ranges.       

##Manifest Streamline
Some clients have needed to create very large manifest files to satisfy the scope of their work.  Using very large manifest files can from time to time lead to the end user experiencing  network time outs due to network topologies, internet connections, or load on the client side systems.  To help mitigate these issues we recommended that clients breakup their manifest files into smaller chunks.  

##Troubleshooting and Logging
From time to time the GDC User Services Team will request that you run the application with the following flags { --debug --logfile } to assist with troubleshooting any issues that might have appeared.  These flags will run the application in debug mode and create a logfile file with the debug logs in it.  
Example Usage:
>gdc-client download -m lung.manifest.txt -t token.file --debug --logfile logfile.txt

##Common Error Codes
This is a list of the most common error codes the DTT generates and their meaning
<ul TYPE="square">
<li> Unable to connect to API – you might be running an out of data client so consider upgrading.</li>
<li> Error: Max Retries Exceeded – network connect timeouts </li>
<li>CryptographyDeprecationWarning – a warning that you should consider upgrading to a higher   
  version python – please upgrade to 2.7.x or higher.</li>
<li>ERROR: An unexpected error has occurred during normal operation of the client -	This could</li>    
  be a variety of problems and we ask you to contact our helpdesk.
<li>ECONNRESET - network connection dropped.</li>
