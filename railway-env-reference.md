# Railway Environment Variables Reference

This file documents all environment variables needed for Railway deployment.

## Backend & Worker Services

### Database & Supabase
- `SUPABASE_URL` - Your Supabase project URL
- `SUPABASE_ANON_KEY` - Supabase anonymous key
- `SUPABASE_SERVICE_ROLE_KEY` - Supabase service role key

### Redis Configuration
- `REDIS_HOST` - Redis host address
- `REDIS_PORT` - Redis port (default: 6379)
- `REDIS_PASSWORD` - Redis password
- `REDIS_SSL` - Redis SSL setting (true/false)

### RabbitMQ Configuration
- `RABBITMQ_HOST` - RabbitMQ host address
- `RABBITMQ_PORT` - RabbitMQ port (default: 5672)

### AI Model APIs (at least one required)
- `ANTHROPIC_API_KEY` - Anthropic Claude API key
- `OPENAI_API_KEY` - OpenAI API key
- `OPENROUTER_API_KEY` - OpenRouter API key
- `MODEL_TO_USE` - Which model to use (anthropic/openai/openrouter)

### Search APIs
- `TAVILY_API_KEY` - Tavily search API key
- `FIRECRAWL_API_KEY` - Firecrawl API key
- `FIRECRAWL_URL` - Firecrawl URL
- `RAPID_API_KEY` - Rapid API key

### Sandbox/Daytona
- `DAYTONA_API_KEY` - Daytona API key
- `DAYTONA_SERVER_URL` - Daytona server URL
- `DAYTONA_TARGET` - Daytona target

### Webhooks & Triggers
- `QSTASH_URL` - QStash URL
- `QSTASH_TOKEN` - QStash token
- `QSTASH_CURRENT_SIGNING_KEY` - QStash current signing key
- `QSTASH_NEXT_SIGNING_KEY` - QStash next signing key
- `WEBHOOK_BASE_URL` - Webhook base URL

### Admin & Security
- `ADMIN_API_KEY` - Admin API key
- `MCP_CREDENTIAL_ENCRYPTION_KEY` - MCP credential encryption key

### External Services
- `CLOUDFLARE_API_TOKEN` - Cloudflare API token
- `LANGFUSE_PUBLIC_KEY` - Langfuse public key
- `LANGFUSE_SECRET_KEY` - Langfuse secret key
- `MAILTRAP_API_TOKEN` - Mailtrap API token

### Payment Processing
- `STRIPE_SECRET_KEY` - Stripe secret key
- `STRIPE_WEBHOOK_SECRET` - Stripe webhook secret

## Frontend Service

### Public Configuration (NEXT_PUBLIC_*)
- `NEXT_PUBLIC_BACKEND_URL` - Backend service URL
- `NEXT_PUBLIC_ENV_MODE` - Environment mode (production/staging/local)
- `NEXT_PUBLIC_SUPABASE_ANON_KEY` - Supabase anonymous key
- `NEXT_PUBLIC_SUPABASE_URL` - Supabase URL
- `NEXT_PUBLIC_URL` - Frontend domain URL

## Railway Service Setup

1. **Backend Service**: Point to `backend/` folder, include all variables
2. **Worker Service**: Point to `backend/` folder, include all variables  
3. **Frontend Service**: Point to `frontend/` folder, include only `NEXT_PUBLIC_*` variables

## Notes

- This file is for reference only - never commit actual values
- Use Railway's environment variable sharing feature for backend/worker services
- Generate `MCP_CREDENTIAL_ENCRYPTION_KEY` using the script in `backend/mcp_service/generate_encryption_key.py` 