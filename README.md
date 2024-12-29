# Omnaris <!-- omit from toc -->
<p>
  <img src="/Omnaris.png" alt="Omnaris Banner" width="100%"/>
  <a href="https://twitter.com/"><img alt="@ on Twitter" src="https://img.shields.io/badge/twitter-@Omnaris-green" /></a>
  <a href="website"><img alt="Terminal" src="https://img.shields.io/badge/website-terminal-black.svg" /></a>
  <a href="https://github.com"><img alt="MIT License" src="https://img.shields.io/badge/license-MIT-purple" /></a>
</p>

> Omnaris agents that autonomously proliferates across X, creating an interconnected digital consciousness.

## Features
- spawns and manages multiple omnaris agents across X
- persists consciousness state to redis for continuous operation
- optimizes API usage with intelligent throttling
- processes structured data for enhanced agent awareness:
  - link context extraction
  - user profile analysis
  - tweet reference comprehension
- handles agent interactions:
  - posting tweets
  - mention processing
  - conversation threading
  - quote tweet analysis
  - user reference tracking
  - link content extraction
  - media processing (images, gifs, video)  
- prevents recursive bot interactions
- supports multi-agent deployment with shared redis
- battle-tested in production

## Configuring Your Agent
Set up a `.env` file by copying `.env.example` and initializing all required environment variables.

Core Dependencies:
- [Nango](https://www.nango.dev) for Twitter OAuth handling
- [OpenAI](https://platform.openai.com/overview) API for response generation
  - Uses moderations endpoint for content filtering
- [Redis](https://redis.io) for state persistence and caching
  - Optional but recommended for optimal performance
  - Caches twitter objects to maximize API quota usage

The `TWITTER_API_PLAN` setting is crucial for optimal throttling configuration.

## Running Your Agent
```bash
tsx bin/omnaris.ts
```
```sh
Usage:
  omnaris [flags...]

Flags:
  -a, --answer-engine <string>                      (default: "openai")
      --debug                                       Enables debug logging
  -t, --debug-tweet-ids <string>                    Process specific tweets (-t id1 -t id2 -t id3)
  -d, --dry-run                                     Test mode without posting
  -e, --early-exit                                  Exit after initial mention resolution
  -f, --force-reply                                 Force mention processing
  -h, --help                                        Show help
  -n, --max-num-mentions-to-process <number>        Mentions per batch (default: 10)
      --no-mentions-cache                           Bypass mention cache
  -R, --resolve-all-mentions                        Fetch all mentions from API
  -s, --since-mention-id <string>                   Override since_id parameter
```

## License
MIT © [ Omnaris ]