# AWS URL Shortener


The application takes a long URL, generates a short link, and uses the short link to redirect to the original URL.

---

## 1. Setting Up the S3 Buckets

I created two S3 buckets for the project:

* One bucket for storing the URL mappings
* One bucket for hosting the frontend

![S3 buckets](images/image11.PNG)

---

## 2. Enabling Website Hosting

I enabled **Static Website Hosting** on the S3 buckets and configured the required index and error documents.

![Static website hosting](images/image2.PNG)

---

## 3. Creating the Lambda Function

I created a Lambda function to handle the URL-shortening process.

I used **Python** as the runtime and configured the required environment variables for the S3 bucket and base URL.

![Lambda function](images/image3.PNG)

---

## 4. Adding the Lambda Code

I added the backend code to the Lambda function and deployed it.

The function handles the requests and stores the URL information in S3.

![Lambda code](images/image4.PNG)

---

## 5. Configuring IAM Permissions

I configured the Lambda execution role with the required S3 permissions so the function could interact with the buckets.

![IAM permissions](images/image5.PNG)

---

## 6. Setting Up API Gateway

I created an **HTTP API** in API Gateway and connected it to the Lambda function.

![API Gateway](images/image6.PNG)

---

## 7. Creating the API Routes

I added the required routes for the application, including the route used to create shortened URLs.

I also configured CORS so the frontend could communicate with the API.

![API routes and CORS](images/image7.PNG)
![API routes and CORS](images/image8.PNG)
---

## 8. Uploading the Frontend

I uploaded the frontend files to the frontend S3 bucket and configured the bucket for public access.

![Frontend uploaded to S3](images/image9.PNG)

---

## 9. Configuring the Bucket Policies

I added the necessary S3 bucket policies to allow the frontend and shortened URLs to be accessed correctly.

![S3 bucket policy](images/image10.PNG)

---

## 10. Testing the Application

I opened the S3 website URL and entered a long URL into the application.

After clicking the shorten button, the application generated a short URL.

![URL shortener test](images/image12.PNG)

---

## 11. Testing the Short Link

I opened the generated short URL to confirm that it redirected to the original website successfully.

![Short URL redirect](images/image12.PNG)
![API routes and CORS](images/image13.PNG)