<div align="center">
  
## LlamaGenAI: Consistent Self-Attention for Long-Range Comic Generation 

  [![GitHub](https://img.shields.io/github/stars/LlamaGenAI/LlamaGenAI?style=social)](https://github.com/aregrid/ComicDiffusion)
  [![Twitter](https://img.shields.io/twitter/follow/llama_gen?style=social)](https://twitter.com/llama_gen)
  [![Discord](https://img.shields.io/discord/1190979134051074110?label=Join%20us%20on%20Discord&logo=Discord&style=social)](https://discord.gg/Jrsff8YFKw)
  [![YouTube](https://img.shields.io/youtube/channel/subscribers/UCfuH6OsUcop2Y8lOHQtHIwA)](https://www.youtube.com/@LlamaGenAI)
</div>


## Features

### AI-powered Anime Art Creation
Unleash your inner mangaka with our advanced AI tools. Simply describe your vision, and our AI will generate breathtaking anime art, complete with intricate details and dynamic compositions.

### Comic Storyboarding Made Easy
Say goodbye to the tedious process of sketching out panels and layouts. Our AI will automatically generate professional-quality comic storyboards based on your script or story outline.

### Limitless Comic Art Styles
From classic manga to avant-garde graphic novels, our AI can create comics in any art style you can imagine. Explore new creative frontiers and bring your unique vision to life.

### The Ultimate AI Artist Community
Connect with like-minded creators from around the globe. Share your work, get feedback, and collaborate on exciting projects with our vibrant AI artist community.

## Examples

### Example 1: Anime Art Creation
![image](https://github.com/aregrid/ComicDiffusion/assets/5910926/f205b6ec-cbae-423d-a2e6-e77b8c00fd60)


### Example 2: Comic Storyboarding
![image](https://github.com/aregrid/ComicDiffusion/assets/5910926/b599a21a-04e3-4e13-80f8-b9fc884a060c)




## Community and Collaboration
We believe that the future of ACG creation lies in the seamless integration of human creativity and advanced AI technology. At LlamaGen.Ai, we're dedicated to empowering artists and creators with the tools they need to push the boundaries of imagination. 🌠

Join our community to share your work, get feedback, and collaborate on exciting projects.

# LlamaGen.Ai REST API

The LlamaGen Comic API allows you to generate and retrieve comic artwork using AI-powered image generation. This API provides endpoints to create comic artwork based on prompts and retrieve the generated comic panels with different styles.

## Introduction

The LlamaGen Comic API offers three main methods for interacting with comic images:

1. Creating comic panels from scratch based on a text prompt
2. Retrieving generated comic artwork
3. (Future feature) Creating variations of existing comic panels

This guide covers the basics of using these API endpoints with useful code samples.

## Usage

### Create Comic Artwork

Creates a new comic artwork based on the provided prompt and other parameters.

```bash
curl -X POST "https://api.llamagen.ai/v1/comics/generations" \
-H "Content-Type: application/json" \
-H "Authorization: Bearer $LLAMAGENAI_API_KEY" \
-d '{
  "model": "cyani-model",
  "prompt": "a comic about a cat and a dog",
  "size": "1024x1024"
}'
```

#### Parameters

- `model` (string): The AI model to use for generation (e.g., "cyani-model")
- `prompt` (string): A text description of the desired comic scene
- `size` (string): The size of the generated image (e.g., "1024x1024")

#### Example Response

```json
{
  "id": "cm20e3dnb00097k8753vd0wt4",
  "status": "LOADING",
  "prompt": "a comic about a cat and a dog"
}
```

The response includes the ID of the created comic artwork, which can be used to retrieve the comic panels later.

### Retrieve Comic Artwork

Retrieves the generated comic panels for a specific artwork ID.

```bash
curl -X GET "https://api.llamagen.ai/v1/comics/generations/YOUR_ARTWORK_ID" \
-H "Authorization: Bearer YOUR_API_KEY"
```

#### Example Response

```json
{
  "id": "cm20e3dnb00097k8753vd0wt4",
  "status": "LOADING",
  "prompt": "a comic about a cat and a dog",
  "comics": [
    {
      "page": 0,
      "panels": [
        {
          "assetUrl": "",
          "panel": 0,
          "caption": ""
        },
        {
          "assetUrl": "",
          "panel": 1,
          "caption": ""
        },
        {
          "assetUrl": "",
          "panel": 2,
          "caption": ""
        },
        {
          "assetUrl": "",
          "panel": 3,
          "caption": ""
        }
      ]
    }
  ]
}
```

The response includes the status of the comic artwork and the `comicData` field containing a JSON-encoded string representing the comic panels.

// ... existing code for Types and Error Handling ...

## Versioning

This documentation refers to version 1.0 of the LlamaGen Comic API. Future updates and changes will be documented here.

---

For more information or support, please contact our API support team at [support@llamagen.ai](mailto:support@llamagen.ai).

