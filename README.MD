# Published White Papers & Sample Architecture
- #### [AWS Kinesis & Lambda Best Practices](https://github.com/thomasfeduk/Published-Whitepapers/blob/main/Whitepaper%20Kinesis%20%26%20Lambda%20Best%20Practices%20-%20Thomas%20Feduk%2C%20Jr.pdf)
  - Implementing eventual consistency and disaster recovery methodologies in event-driven distributed systems with Kinesis and Lambdas.
  - Ensuring exactly-once-processing with or without idempotency with reliable error recovery, re-try handling and DLQs. 
- #### [Workflow Decisioning Bridge Service](https://github.com/thomasfeduk/Published-Whitepapers/blob/main/Workflow%20Decisioning%20Bridge%20Service.pdf)
  - Serverless bridge service enabling external systems (Zapier, Nintex, Tray.io) to delegate complex decision logic to LLM processors such as OpenAI.
  - API Gateway with Lambda authorizer generates secure presigned S3 upload URLs tied to an idempotent workflow ID.
  - S3 PUT trigger launches an asynchronous processing pipeline that uploads PDFs to OpenAI and manages the lifecycle of a structured prompt thread.
  - Workflow state is persisted in DynamoDB with TTL and status tracking to ensure idempotency and retry safety.
  - Final decision is parsed and transformed into a format compatible with the originating workflow system, then sent via webhook for flow continuation.