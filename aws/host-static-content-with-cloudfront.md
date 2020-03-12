# Host static content with cloudfront

## Prerequisites
* Have access to an AWS account
* Know the difference between S3 API vs S3 Website Hosting as an Origin for Cloudfront. [Tutorial here](https://www.youtube.com/watch?v=DiIaoIcoKNY)

## Steps
1. create a simple HTML file
   ```
   <!DOCTYPE html>
   <html>
   <body>

     <h1>I am hosted on cloudfront</h1>

   </body>
   </html>
   ```
2. create a bucket on s3 and upload the HTML file
3. create a cloudfront distribution that points to the file we have created before
4. open browser and check if you can reach the website served by cloudfront