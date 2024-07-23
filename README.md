# Serverless LocalStack Project

This project demonstrates a serverless application using AWS Lambda and API Gateway, developed locally using LocalStack and the Serverless Framework.

## Setup

1. Install dependencies:
   ```
   npm install
   ```

2. Start LocalStack and PostgreSQL:
   ```
   docker-compose up -d
   ```

3. Deploy the serverless application:
   ```
   serverless deploy --stage local
   ```

## Project Structure

- `serverless.yml`: Serverless Framework configuration
- `functions/`: Contains Lambda function handlers
- `docker-compose.yml`: Defines LocalStack and PostgreSQL services
- `localstack_endpoints.json`: LocalStack endpoint configuration

## Key Components

1. **Serverless Framework**: Used for defining and deploying serverless functions.
2. **LocalStack**: Emulates AWS services locally for development and testing.
3. **PostgreSQL**: Database for the application (if needed).
4. **Lambda Functions**: Located in the `functions/` directory.

## Available Commands

- Deploy the application:
  ```
  serverless deploy --stage local
  ```

- Invoke a function locally:
  ```
  serverless invoke local --function hello
  ```

- Remove the deployed stack:
  ```
  serverless remove --stage local
  ```

## API Endpoints

- Hello endpoint: GET /hello
- Goodbye endpoint: GET /goodbye

## Notes

- The project uses Python 3.11 runtime for Lambda functions.
- LocalStack is configured to emulate Lambda, API Gateway, CloudFormation, S3, CloudWatch Logs, and IAM.
- PostgreSQL is set up but not directly used in the Lambda functions. It's available for future database needs.

## Troubleshooting

If you encounter issues with LocalStack, check the Docker logs:
```
docker logs localstack
```

Ensure that the `localstack_endpoints.json` file is correctly configured and matches your LocalStack setup.
