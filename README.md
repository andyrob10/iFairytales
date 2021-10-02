# iFairytales

A secure encrypted link generator for AWS's content delivery network, CloudFront to work in Unity 3D

Purpose:
This script was created to allow content (movies and files) to be delivered securely via Amazon's content delivery network (Cloudfront). The content is stored in one geographical location on a cloud hardrive (a bucket). The content delivery network allows for faster data rates and speeds between data centers. The link generator creates RSA encrypted links that allows for secure data transfers between the bucket and the end user no matter where they are in the world, at fast speeds using the content delivery network.

Usage:
The scripts were written from AWS C# .net SDK specifically for Unity 3D in order to be able to stream video to mobile users around the world. There are two basic scripts. The first is the class CloudFrontSecurityProvider and the second the Download method script. The download method is called when a user would click on the download button.



<img src="https://user-images.githubusercontent.com/50190461/135717985-a04a067b-31bd-49d0-9936-ee28104ba89b.png" width="700"/>




