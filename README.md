# LibreChat with GitHub MCP Integration

This repository contains LibreChat configured with GitHub Model Context Protocol (MCP) integration, allowing you to use GitHub functionality directly from AI conversations.

## Quick Start

### Prerequisites
- Docker and Docker Compose installed
- GitHub Personal Access Token (for full functionality)

### Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/tfa225/LibreChat-MCP-Ready.git
   cd LibreChat-MCP-Ready
   ```

2. Create your environment file:
   ```bash
   cp .env.example .env
   ```

3. Generate security credentials at https://www.librechat.ai/toolkit/creds_generator and add them to your `.env` file

4. Add your GitHub Personal Access Token to `librechat.yaml` file (optional but recommended):
   ```yaml
   plugins:
     github:
       enabled: true
       apiKey: 'your_github_token_here' 
   ```

5. Start LibreChat:
   ```bash
   docker compose up -d
   ```

6. Access LibreChat at http://localhost:3080

## Verifying GitHub MCP Integration

When you start a conversation with Claude, you should see GitHub tools available in the tools section. If you've configured your GitHub token, you'll be able to:

- Search repositories
- List commits
- Create issues
- Access file contents
- And more

## Troubleshooting

If you encounter issues:

1. Check logs: `docker compose logs -f api`
2. Ensure your `.env` has valid encryption keys
3. Verify your GitHub token has the necessary permissions
4. Make sure all containers are running: `docker compose ps`

## Additional Resources

- [LibreChat Documentation](https://www.librechat.ai/docs)
- [GitHub MCP Integration Guide](https://www.librechat.ai/docs/configuration/librechat_yaml/mcpServers)