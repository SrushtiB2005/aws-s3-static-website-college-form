# Mini Project: College Admission Form – AWS S3 Hosting  

 📌 Project Overview  
This mini project demonstrates how to host a static website using Amazon S3.  
The website is a College Admission Form created in HTML and deployed to an S3 bucket with public access enabled.  

The project highlights:  
- Creating an S3 bucket  
- Uploading a static website (`index.html`)  
- Applying a bucket policy for public access  
- Enabling static website hosting 
- Accessing the site via the AWS website endpoint URL  

# Steps Implemented  

1. Create an S3 Bucket  
- Bucket name: `mybucky123-addmission-form`  
- Region: `ap-south-1 (Mumbai)`  
- Disabled  Block all public access  
<img width="1920" height="885" alt="Screenshot 2025-08-28 151745" src="https://github.com/user-attachments/assets/86fa05ed-1fa8-4ce2-9411-4f1b6dabb574" />

2. Upload Website File  
- Uploaded `index.html` (College Admission Form webpage)   
<img width="1920" height="885" alt="Screenshot 2025-08-28 152109" src="https://github.com/user-attachments/assets/12dd4153-c82e-49a9-bb60-b82b3f208e62" />

3. Apply Bucket Policy  
The following policy was added to allow public access to objects:  

json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "mybucky123-admission-form",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": [
                "arn:aws:s3:::mybucky123-admission-form/*",
                "arn:aws:s3:::mybucky123-admission-form"
            ]
        }
    ]
}
<img width="1920" height="876" alt="Screenshot 2025-08-28 152945" src="https://github.com/user-attachments/assets/92b2be2f-ac7c-4bf9-963a-5d1d802300c4" />

4. Enable Static Website Hosting
	Index document: index.html
•	Error document: (not used)
<img width="1920" height="883" alt="Screenshot 2025-08-28 152453" src="https://github.com/user-attachments/assets/99bac82d-fd44-4e56-a283-94b895211ee0" />

5. Access Website
Used the S3 Website Endpoint:
https://mybucky123-admission-form.s3.ap-south-1.amazonaws.com/index.html
<img width="1920" height="1027" alt="image" src="https://github.com/user-attachments/assets/8f285ac1-d33d-4e20-b8f8-f63b7e7814c8" />

# Project Files
•	index.html → Admission Form webpage

# Technologies Used
•	Amazon S3 (Static Website Hosting)
•	HTML5

# Live demo
Click the link below:
https://mybucky123-admission-form.s3.ap-south-1.amazonaws.com/index.html

# Browser Compatibility Note

During testing, the website initially worked in Microsoft Edge but not in Google Chrome.
Reason:
• Chrome cached an old version of the site
• Chrome sometimes blocks HTTP content (S3 websites don’t support HTTPS)

Solution:
• Cleared cache and tested in Incognito mode
• Used the correct HTTP endpoint
• Verified metadata (Content-Type: text/html)

After these steps, the site worked in both browsers.

# Final Outcome
This project successfully demonstrates hosting a static website on AWS S3 with public access and serves as a practical example of cloud computing basics.




