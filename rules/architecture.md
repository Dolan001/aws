# AWS architecture rules

Use separate AWS accounts for shared services, development, staging, and production when the
organization supports them; production must be isolated from non-production. Put CloudFront and
WAF at the edge, workloads and data in private subnets, and expose HTTP/HTTPS/WebSockets through an
ALB. ECS Fargate is the default runtime, ECR stores images, RDS PostgreSQL owns relational state,
ElastiCache Redis owns transient cache/broker/fan-out state, and private S3 owns objects.

React static output uses private S3 plus CloudFront. Next.js SSR uses a standalone Node.js ECS
service and must coordinate cache invalidation across replicas when ISR or tag revalidation is used.
DRF without realtime may use Gunicorn WSGI; DRF with realtime uses a production ASGI server and
Channels. FastAPI uses one Uvicorn process per ECS task. ALB, WAF, and CloudFront replace Nginx by
default; add Nginx only for a documented proxy requirement not met by managed components.

Create separate ECS services for web/API, Next.js SSR, realtime when isolation is justified, and
Celery workers. Run only one scheduler when schedules exist. Scale HTTP by request or latency,
workers by queue age/depth, and realtime by connections plus CPU/memory. Never use local container
disk for durable data. Treat SES, SNS, EventBridge, EFS, API Gateway, RDS Proxy, and Nginx as
conditional decisions, not defaults.
