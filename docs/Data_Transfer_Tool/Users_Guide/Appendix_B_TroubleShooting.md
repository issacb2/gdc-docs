Appendix_B_Troubleshooting

Speed Performance During Download
The Data Transfer Tool does have two performance tuning options that are presented during download operations.  The two options are presented below:
  --n (number of threads used)
  --http-chunk-size (can be used in large downloads)

The "--n" option assists with assigning the number of threads to the download process.  The default is 4 and can't be lowered below three.  The --http-chunk-size setting can improve performance but we don't provide any hard settings due to the eclectic nature of client networks and their connections to the internet but instead we encourage clients to experiment with changing the default setting of 1048576 bytes to larger size ranges.       

Manifest Streamline
Some clients have needed to create very large manifest files to satisfy the scope of their work.  Using very large manifest files can from time to time lead to the end user experiencing  network time outs due to network topologies, internet connections, or load on the client side systems.  To help mitigate these issues we recommended that clients breakup their manifest files into smaller chunks.  

Troubleshooting
From time to time the GDC User Services Team will request that you run the application with the following flags { --debug --logfile } to assist with troubleshooting any issues that might have appeared.  These flags will run the application in debug mode and create a logfile file with the debug logs in it.  
Example Usage:
>gdc-client download -m lung.manifest.txt -t token.file --debug --logfile logfile.txt
