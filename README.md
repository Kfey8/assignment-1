# assignment-1      Kamryn Fey  Cloud Computing     TR 7:30-8:45pm
For this assignment I had to create and deploy a static website to AWS. 
To do this I started by creating my actual website using HTML, CSS, and
 javascript. I actually used an alternative way to create my HTML than 
 what we had discussed in class. Instead I used visual studios code, and 
 installed live server. Which basically gives you a preview almost 
 instantly into what your website looks like as you develop it. I 
 persoally found this very helpful to me when putting all the finishing
 touches on my website, both visually and functionally. After I was satisfied
 with the content of my website, I began creating the S3 bucket for it. 
 I began this by logging into amazon AWS and going to the Amazon S3 console 
 and clicking create bucket. I decided to name it
 feytheoryequinetrainingmethods.com. Once it was created I had to enable 
 static website hosting. To do this I clicked on the bucket I wanted to edit
 and went to "properties", I scrolled down to static website hosting and 
 chose enable. I then wwent to the index document and entered index.html, 
 which is the home screen to my website. After that wwas done I needed to
 edit the "block public access" settings so that it would make it a public 
 website. Before doing this I made sure that I was willing to risk anyone
 seeing my website from any source. When you take off the block on public
 access, anyone and everyone with a computer can have access to that site. 
 I then went into permissions, and under "block public access" I chose edit
 and unblocked all public access to my website, and saved before continuing. 
 My next task wwas to add a bucket policy that makes the content of my bucket
 publicly availible. I proceeded with this by continuing under permissions
 and under bucket policy chose edit. I cleared the code in the bucket policy
 editor and replaced it with the following lines...

 {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::feytheoryequinetrainingmethods.com/*"
            ]
        }
    ]
}

I made a special note to ensure that my bucket name was spelled correctly
and saved the changes. This is the only spot I had trouble with when doing 
this assignment since it did take me two tries since I had accidentally 
forgot the /* at the end of my bucket name. But other than that this process
was very pain free! After this I needed to upload my HTML files and content 
associated with it. To do this I went to objects and upload, then selected 
the files. Already having the HTML file completely modified and ready to go 
helped me with this part tremendously. I only had to upload all files once 
instead of going back and forth while editing my HTML to my liking. After 
this all I had to do was go to properties once again, and scroll all the way
to the bottom where it gives my endpoint. I clicked the link and all of my 
website looked exactly as I wanted it to! Just to be sure that everything 
was functioning properly I opened it up on my phone as well and 

Website link:
http://feytheoryequinetrainingmethods.com.s3-website-us-east-1.amazonaws.com/