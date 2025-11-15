# What Are APIs? (Short Intro)

APIs are the communication bridge between two software systems.
Instead of exposing your entire backend, you expose small, controlled “entry points” that other apps can call.

In simple terms:

“Ask me something → I return exactly what you need → without revealing my internal system.”

This is how mobile apps, websites, microservices, and AI systems talk to each other.

# Why Build APIs? (Advantages)
1. Frontend ↔ Backend Communication

APIs let your app (web/mobile) request data from the server.

2. Security Layer

Your database remains hidden — APIs expose only what is safe.

3. Reusability

One API can be used by multiple apps, services, scripts, and automations.

4. Scalability

Cloud APIs (like this one) handle high traffic with ease.

5. Easy Integrations

Payments, Authentication, Maps, AI, YouTube — everything works on APIs.

6. Microservice Friendly

Each service exposes its own API → app stays modular and clean.

7. Cloud & Serverless Ready

Using AWS Lambda + API Gateway means:

No servers to manage

Pay only for actual API calls

Highly cost-efficient

# Architecture
```
Client → API Gateway (HTTP API) → Lambda Function → JSON Response
```

Serverless, fast, affordable.

# Steps to Build a simple API (e.g, prodiy-api)
1. Create Lambda Function

Go to AWS Lambda → Create Function

Runtime: Python 3.x

Keep default permissions

Use this handler :-
```
def lambda_handler(event, context):
    return {
        "statusCode": 200,
        "body": "Hello from prodigy-api!"
    }
```

Click Deploy.

2. Create HTTP API in API Gateway

Open API Gateway → Create API

Choose HTTP API

Name it: prodigy-api

Create the API

3. Add the /predict Route

Navigate to Routes → Create Route

Method: GET (or ANY)

Resource Path: /predict

4. Attach Lambda to /predict

Click the /predict route

Choose Attach Integration

Select your Lambda function

Save changes

5. Deploy the API

Go to Deployments / Stages

Deploy to $default stage

Copy the Invoke URL

Final URL looks like:
```
https://<api-id>.execute-api.<region>.amazonaws.com/predict
```

6. Test the API

Browser or terminal:
```
curl https://<api-id>.execute-api.amazonaws.com/predict
```
Expected Output:
```
Hello from prodigy-api!
```

# Final Result

You now have a fully functional, globally accessible serverless API built entirely on AWS using:

Lambda for compute

API Gateway for routing

$default stage for deployment

A clean starting point for building real backend services, ML inference APIs, and cloud-native systems.
