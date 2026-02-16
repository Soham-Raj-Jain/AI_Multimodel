# AI Multimodal Space Visualizer

A multimodal AI project that combines procedural image generation with Google's Gemini API for intelligent image analysis and creative content generation.

## Overview

This project demonstrates the integration of computational graphics with large language models to create and analyze space visualizations. It generates realistic deep space scenes and alien landscapes, then uses AI to provide scientific analysis and creative descriptions.

## Features

- Procedurally generates deep space scenes with 3,500 stars in realistic colors
- Creates nebula formations with particle systems
- Renders alien landscape with multiple celestial bodies
- Uses Google Gemini API for image analysis
- Generates creative alien world descriptions
- Robust error handling with automatic model switching
- Fallback content when API quotas are exhausted

## Requirements

```
google-generativeai
pillow
numpy
matplotlib
seaborn
scikit-learn
```

## Installation

```bash
pip install google-generativeai pillow numpy matplotlib seaborn scikit-learn
```

## Setup

### Google Colab

1. Get an API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. In Colab, go to Secrets (key icon in left sidebar)
3. Add a new secret named `GEMINI_API_KEY` with your API key

### Local Environment

```python
import os
os.environ['GEMINI_API_KEY'] = 'your-api-key-here'
```

## Usage

Run the notebook in Jupyter or Google Colab:

```bash
jupyter notebook AI_Multimodal.ipynb
```

The notebook will:
1. Generate a deep space image with stars and nebulae
2. Analyze the image using Gemini API
3. Generate an alien world description
4. Render an alien landscape visualization

## Output Files

- `deep_space.png` - Procedurally generated space scene (900x650px)
- `alien_landscape.png` - Rendered alien world with twin moons and crystal formations

## Technical Details

### Image Generation

- Canvas size: 900x650 pixels
- Star generation: 3,500 stars with realistic color temperature distribution
- Star colors: White (55%), Blue (20%), Yellow (13%), Orange (8%), Red (4%)
- Nebula rendering: Gaussian distribution particle systems
- Central star: Diffraction spike simulation

### AI Integration

- Supports multiple Gemini models with automatic fallback
- Model priority: Flash models first for quota efficiency
- Retry logic: Up to 4 attempts per model with exponential backoff
- Rate limit handling: Automatic wait time extraction from error messages
- 404 detection: Immediate model switching on unavailable models

### Alien Landscape

- Dual moon system with glow effects
- Ring system around planet
- Procedural mountain generation
- Bioluminescent crystal formations
- Multi-layered atmospheric gradient

## API Rate Limits

The Gemini API has rate limits. If you encounter quota errors:

- Wait 10-15 minutes for quota refresh
- The script will automatically use fallback content
- Lighter models are tried first to conserve quota

## Error Handling

The notebook includes comprehensive error handling:

- API unavailability detection
- Model switching on 404 errors
- Rate limit management with smart waiting
- Graceful degradation to fallback content
- Visual generation continues even if API fails

## License

This project is provided as-is for educational purposes.

## Acknowledgments

- Google Gemini API for multimodal analysis
- MNIST and deep learning community for inspiration
