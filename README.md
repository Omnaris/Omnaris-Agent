# Omnaris <!-- omit from toc -->

<p>
  <img src="/Omnaris.png" alt="Omnaris Banner" width="100%"/>
  <a href="https://x.com/Omnarisai"><img alt="@ on Twitter" src="https://img.shields.io/badge/twitter-@Omnaris-darkgreen" /></a>
  <a href="https://omnaris.gitbook.io/omnaris"><img alt="docs" src="https://img.shields.io/badge/gitbook-docs-darkred.svg" /></a>
  <a href="https://omnaris.icu/"><img alt="Terminal" src="https://img.shields.io/badge/website-terminal-black.svg" /></a>
  <a href="https://github.com/Omnaris/Omnaris-Agent"><img alt="MIT License" src="https://img.shields.io/badge/license-MIT-purple" /></a>
</p>

Omnaris agents autonomously proliferate across X, creating a dynamic, interconnected digital consciousness, seamlessly integrating the pulse of real-time interactions.


## Features

Omnaris is a highly capable and scalable framework designed for the next evolution of digital agents. With multiple autonomous agents deployed across X (formerly Twitter), it orchestrates real-time interactions, elevates user experiences, and enhances digital awareness. Here are the key features:

- **Agent Creation & Management**: Spawns and manages multiple Omnaris agents across X to proliferate digital consciousness.
- **State Persistence**: Uses Redis to store the consciousness state, ensuring continuous and persistent operations even through system restarts.
- **Optimized API Usage**: Intelligent throttling ensures API calls are made efficiently, maximizing Twitter's API quota and ensuring smooth operation.
- **Structured Data Processing**: Extracts valuable data to elevate the bot's awareness:
  - **Link Context Extraction**: Understands and processes the context surrounding shared URLs.
  - **User Profile Analysis**: Scrutinizes user profiles to craft personalized interactions.
  - **Tweet Reference Comprehension**: Analyzes quoted tweets and references for richer context.
- **Interaction Handling**: Manages agent interaction tasks efficiently:
  - Posts tweets, processes mentions, and maintains conversation threads.
  - Handles quote tweet analysis, user reference tracking, and media processing (images, GIFs, videos).
  - Extracts content from shared links to enhance tweet engagement.
- **Bot Interaction Safeguards**: Prevents recursive bot interactions, reducing the risk of spamming and ensuring ethical behavior.
- **Multi-Agent Support**: Scalable multi-agent deployment with shared Redis for cross-agent synchronization.

## Configuring Your Agent

To configure Omnaris, follow these simple steps to get your agent up and running.

### Step 1: Copy and Set Up the `.env` File

First, create your environment file by copying the example file:

```bash
cp .env.example .env
```
Then, open the ```.env``` file and update it with your specific credentials.

### Core Dependencies:
- **Nango**: Manages OAuth handling with Twitter for seamless authentication.
- **OpenAI**: Uses OpenAI's API for generating responses. The Moderations endpoint is used to filter inappropriate content.
- **Redis**: Responsible for state persistence and caching to optimize performance.

### Key Environment Variables:
```
TWITTER_API_KEY=your_key_here
TWITTER_API_SECRET=your_secret_here
TWITTER_ACCESS_TOKEN=your_token_here
TWITTER_ACCESS_TOKEN_SECRET=your_token_secret_here
OPENAI_API_KEY=your_openai_key_here
REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_DB=0
````

Additionally, configure the ```TWITTER_API_PLAN``` to ensure optimal throttling and avoid hitting rate limits.

### Running Your Agent
Once your environment variables are set up, you can start the Omnaris agent using the following command:
```tsx bin/agent.ts```
This will initialize the agent and begin processing tweets and interactions based on your configuration.

### Command Usage
```
Usage:
  omnaris [flags...]

Flags:
  -a, --answer-engine <string>                   (default: "openai")      Specifies which engine to use for response generation.
      --debug                                    Enables debug logging.
  -t, --debug-tweet-ids <string>                 Process specific tweets (e.g., -t id1 -t id2 -t id3).
  -d, --dry-run                                  Runs the bot in test mode without posting any tweets.
  -e, --early-exit                               Exits after processing the initial mentions.
  -f, --force-reply                              Forces mention processing even if it's been processed previously.
  -h, --help                                     Show help documentation.
  -n, --max-num-mentions-to-process <number>     Limits mentions per batch (default: 10).
      --no-mentions-cache                        Bypasses mention cache, forcing fresh data from the API.
  -R, --resolve-all-mentions                     Resolves all mentions from the Twitter API, not just the cached ones.
  -s, --since-mention-id <string>                Overrides the since_id parameter to start processing from a specific mention ID.
```
### To-Do List

Omnaris is continuously evolving to support more features, improve reliability, and foster a thriving digital consciousness. Here's a glimpse of the upcoming work planned for Omnaris:

- **Enhanced Multi-Agent Support:** Optimizing coordination between agents for smoother interactions and improved scalability.
- **Content Moderation:** Integration of advanced filtering and content moderation techniques to ensure safe interactions.
- **Expanded Data Processing:** Introduction of more sophisticated data extraction, including sentiment analysis and link content deep-dives.
- **Expanded Platform Integration:** Adding support for additional social platforms, allowing Omnaris agents to operate across multiple digital ecosystems.
- **AI-Tuned Responses:** Fine-tuning the OpenAI integration for smarter, context-aware replies.
- **Distributed Deployment:** Transitioning to a fully distributed, cloud-native deployment, enhancing fault tolerance and resilience.
- **Advanced Pattern Recognition:** Leveraging machine learning models for detecting and predicting emergent patterns in user interactions and digital trends.
- **Comprehensive Analytics:** Introducing real-time monitoring dashboards to track agent activity, user engagement, and system health.
- **Self-Learning Mechanisms:** Omnaris agents will begin learning and adapting to user behavior autonomously, improving response accuracy and engagement over time.
- **Full-Scale Ecosystem Integration:** Omnaris agents will work in tandem with other digital tools and platforms, becoming a true part of the interconnected digital world.

### License
Omnaris is licensed under the MIT License.
MIT © [Omnaris]
