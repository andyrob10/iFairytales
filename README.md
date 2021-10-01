# iFairytales

A secure encrypted link generator for AWS's content delivery network, CloudFront to work in Unity 3D

There are two basic scripts. The first is the class CloudFrontSecurityProvider and the second the Download method script. The download method is called when a user would click on the download button (having purchased the content).

The .mp4 files/content/data sits in local AWS buckets. In this way streaming video frames are able to be stream at high bandwidths globally. For example using a content delivery network if the files are hosted on a bucket in USA East, the bandwidth is faster via a CDN than if a user were to download from Asia. 

Implementation: 

First the content or mp4 is uploaded to the AWS bucket. Cloudfront URL's are generated that forward to these buckets but access to these buckets from the cloudfront URL's is restricted to specific IAM user ID. The content in the buckets is then encrypted and secured using RSA 2028 bit encryption. Under accounts you set up an IAM user ID account that is permitted to access that data/content provided that they provide the correct user ID and private key. On AWS the cloudfront pass through and bucket access policies must match the parameters set in both the method and the class.

These scripts enable developers to generate the required RSA compliant urls to access the data they wish to stream contained within those buckets and serve out content securely to their end users. It can be deployed to delivery the content/data to iOS, android, or a wide variety of platforms that are provided within the Unity 3D framework using C#.

AAAAA = the cloudfront base URL
XXXXXX = the name of the file name whether using a high / medium or low data feed (a requirement of Apple) to serve out multiple feeds at different bandwidths. These scripts ultimately saves the mp4 to the application's persistent data path on the device. HOWEVER it is possible to stream the data via a .M3U8 and host different feeds for live streams as well.
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX = the private key generated from AWS to grant access to the bucket.

The download script generates the url string which includes information about how long the user will be requesting access to the bucket for which is set in this instance for 120 minutes in order to be able to download the mp4.

The update function also is constantly checking a boolean to establish if a user has pressed the download button. If true the mp4 download begins and it stored on the device. The CloudFront class came mostly from AWS C# SDK library but was edited and paired down significantly in order to be able to download video securely. 

More over most of the AWS C# SDK files were simply deleted and the only thing that remained was this highly edited script.  






