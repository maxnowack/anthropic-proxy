# anthropic-proxy

A proxy server that transforms Anthropic API requests to OpenAI format and sends it to openrouter.ai. This enables you to use Anthropic's API format while connecting to OpenAI-compatible endpoints.

## Usage

With this command, you can start the proxy server with your OpenRouter API key on port 3000:

```bash
OPENROUTER_API_KEY=your-api-key npx anthropic-proxy
```

Environment variables:

- `OPENROUTER_API_KEY`: Your OpenRouter API key (required when using OpenRouter)
- `ANTHROPIC_PROXY_BASE_URL`: Custom base URL for the transformed OpenAI-format message (default: `openrouter.ai`)
- `PORT`: The port the proxy server should listen on (default: 3000)
- `REASONING_MODEL`: The reasoning model to use (default: `google/gemini-2.0-pro-exp-02-05:free`)
- `COMPLETION_MODEL`: The completion model to use (default: `google/gemini-2.0-pro-exp-02-05:free`)
- `DEBUG`: Set to `1` to enable debug logging

Note: When `ANTHROPIC_PROXY_BASE_URL` is set to a custom URL, the `OPENROUTER_API_KEY` is not required.

## Claude Code

To use the proxy server as a backend for Claude Code, you have to set the `ANTHROPIC_BASE_URL` to the URL of the proxy server:

```bash
ANTHROPIC_BASE_URL=http://0.0.0.0:3000 claude
```

## License
Licensed under MIT license. Copyright (c) 2025 Max Nowack

## Contributions
Contributions are welcome. Please open issues and/or file Pull Requests.
