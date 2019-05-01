Appendix_B_Troubleshooting

Speed Performance During Download
The Data Transfer Tool does have two performance tuning options that are presented during download operations.  The two options are presented below:
  --n (number of threads used)
  --http-chunk-size (can be used in large downloads)

The "--n" option assists with assigning the number of threads to the download process.  The default is 4 and can't be lowered below 3.  The --http-chunk-size setting can improve performance but we don't provide any hard settings due to the eclectic nature of client networks and their connections to the internet but instead we encourage clients to experiment with changing the default setting of 1048576 bytes to larger size ranges.       
