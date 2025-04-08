# 📹 Video Ad Classification

> Automatically classify video ads using IAB taxonomy and extract key moments for better targeting and performance analysis.

## 🎯 Use Case

The video advertising industry requires sophisticated tools to classify content, identify key moments, and analyze performance. This recipe demonstrates how to use Mixpeek to:

1. **Automatically classify video ads** according to the IAB taxonomy
2. **Detect important scenes and objects** within video content
3. **Extract spoken content** for analysis
4. **Enable content-based search** across video ad libraries

## 🛠️ Implementation

### Key Components

- **Scene Detection**: Identify distinct scenes within video ads
- **Object Detection**: Recognize products, people, and key visual elements
- **Speech-to-Text**: Convert spoken content to searchable text
- **IAB Taxonomy Classification**: Categorize content according to industry standards

### Code Example

```javascript
// Configure video ad classification pipeline
const pipeline = new MixpeekPipeline({
  featureExtractors: [
    'scene-detection',
    'object-detection',
    'speech-to-text',
    'iab-taxonomy-classifier'
  ],
  retrievers: ['content-search']
});

// Process video ad content
const results = await pipeline.process(adVideoFile);

// Search for specific content across processed ads
const matches = await pipeline.search({
  query: "sports equipment outdoor activity",
  filters: {
    iabCategory: "Sports",
    duration: { min: 15, max: 30 }  // 15-30 second ads
  }
});
```

## 🔄 Pipeline Flow

1. **Ingestion**: Video ads are uploaded to a Mixpeek bucket
2. **Feature Extraction**:
   - Scene detection divides videos into meaningful segments
   - Object detection identifies key visual elements
   - Speech-to-text converts spoken content to searchable text
   - IAB classifier assigns taxonomy categories
3. **Indexing**: Extracted features are stored in optimized feature stores
4. **Retrieval**: Content can be searched using natural language, visual similarity, or metadata filters

## 📊 Business Benefits

- **Improved Ad Targeting**: Automatically classify ads for better audience matching
- **Time Savings**: Eliminate manual tagging and classification
- **Performance Insights**: Identify which visual elements and scenes drive engagement
- **Compliance Support**: Ensure ads meet platform and regulatory requirements

## 🔗 Additional Resources

- [Complete Advertising Solution](https://mixpeek.com/solutions/advertising)
- [Blog: Automating Video Ad Classification with IAB Taxonomy](https://mixpeek.com/blog/video-ad-classification)
- [GitHub Example Repository](https://github.com/mixpeek/recipes/ad-video-classification-example)

## 📚 Key Mixpeek Concepts Used

- **Multimodal Ingestion**: Processing video and audio in a single pipeline
- **Feature Extraction**: Extracting visual elements, scenes, and spoken content
- **Taxonomies**: Applying IAB classification to organize content
- **Content Retrieval**: Searching across processed video content 