# RenderIO Free n8n Workflow Templates

A collection of free, ready to use n8n workflow templates that showcase what you can build with [RenderIO](https://renderio.dev), the FFmpeg as a Service cloud API.

Each template is a complete working workflow you can import directly into your n8n instance. They are designed to be plug and play with clear sticky notes, renamed nodes, and a config node that groups all the settings you need to change in one place.

## Templates

### Convert MP4 to GIF

The simplest starting point for using RenderIO with n8n. Submit a video URL through a form, the workflow sends it to the cloud for FFmpeg processing, polls until the conversion is done, and returns the GIF download link. Great for understanding the core pattern of submit, poll, and retrieve that all RenderIO workflows follow.

**Nodes used:** n8n Form Trigger, RenderIO, Wait, If

**What you will learn:**
- How to submit an FFmpeg command through the RenderIO node
- The poll and retry pattern for async media processing
- How to customize FFmpeg flags for different output formats and quality settings

[Download JSON](./workflows/renderio-mp4-to-gif.json)

---

### Turn Long Videos into Shorts

A full production pipeline that watches a Google Drive folder for new videos, transcribes them with Whisper, uses OpenAI to pick the best highlight clips, then renders each clip in three aspect ratios (TikTok, Reels, Square) and uploads them back to Google Drive. Every run is logged to a Google Sheet for tracking.

**Nodes used:** Google Drive Trigger, Google Drive, Google Sheets, RenderIO, OpenAI, HTTP Request (Whisper), Wait, If, Merge, Code

**What you will learn:**
- Chaining multiple RenderIO commands in a single workflow
- Integrating AI for intelligent clip selection from transcripts
- Managing parallel render jobs with merge nodes
- Logging and tracking automated media pipelines

[Download JSON](./workflows/turn-long-videos-into-shorts.json)

---

## Getting Started

### 1. Create a RenderIO account

Sign up for free at [renderio.dev](https://renderio.dev) and grab your API key from the dashboard.

### 2. Install the [community node](https://n8n.io/integrations/renderio/)

In your n8n instance, go to **Settings > Community Nodes** and install `n8n-nodes-renderio`.

### 3. Add your credentials

Create a new **RenderIO API** credential in n8n and paste your API key.

### 4. Import a template

Download any JSON file from the `workflows/` folder and import it into n8n through **Workflows > Import from File**.

## Requirements

- A self hosted or **cloud** n8n instance (community nodes are required)
- A [RenderIO](https://renderio.dev) account and API key
- Additional credentials depending on the template (Google Drive, OpenAI, etc.)

## Contributing

Found a bug or have an idea for a new template? Open an issue or submit a pull request. We welcome contributions from the community.

## Links

- [RenderIO Website](https://renderio.dev)
- [RenderIO Documentation](https://renderio.dev/docs)
- [RenderIO node on n8n Website](https://n8n.io/integrations/renderio/)
- [n8n Community Node on npm](https://www.npmjs.com/package/n8n-nodes-renderio)
