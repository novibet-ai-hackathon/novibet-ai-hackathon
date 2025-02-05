# 🎲 GenAI-Powered Dynamic Backgrounds: Personalized Visuals Based on Player Activity

## ❗ Overview
Welcome to the **GenAI-Powered Dynamic Backgrounds** challenge! In this hackathon, you will leverage **Generative AI** to create **personalized, dynamic backgrounds** based on user betting activity. The goal is to process betting data and derive insights into user preferences, which can then be transformed into visual representations using generative models.

### 📌 The Challenge
Your task is to analyze customer betting behaviors from the provided dataset and generate **custom background images** that reflect their individual betting preferences. These visuals should serve as a unique, artistic representation of each user’s history and choices.

#### **How It Works**
- Extract meaningful insights from the dataset to **profile user preferences**.
- Convert structured data into **text prompts** describing betting behavior.
- Use **Generative AI models** to create visually appealing backgrounds that mirror user activity.
- Optimize for local execution on standard laptops (12-32GB RAM, no GPUs).

## 📂 Dataset Details
The dataset consists of **20555 rows** of user betting activity across various sports, competitions, and bet types. The dataset is synthetic meaning that these are not actual customer ids and selections. Below is a breakdown of the dataset structure:

| Column Name     | Data Type    | Description |
|----------------|-------------|-------------|
| `Customer ID`  | `int`       | Unique identifier for each customer. |
| `Time of Bet`  | `datetime`  | The timestamp when the bet was placed. |
| `Live Bet`     | `bool`      | `True` if the bet was placed live during a match; otherwise `False`. |
| `Sport`        | `string`    | The sport category (e.g., Soccer, Basketball). |
| `Competition`  | `string`    | The league or tournament name (e.g., Premier League, La Liga). |
| `Region`       | `string`    | The country or geographical region where the competition is held. |
| `Teams Involved` | `string`  | The teams or players participating in the match. |
| `Type of Bet`  | `string`    | The specific type of bet placed (e.g., Full Time Result, Goals Over/Under). |

## 🛠️ Tools & Models for Generative AI
Since you’ll be working **locally** without access to GPU clusters, here are some **lightweight and efficient** generative models and APIs you can use:

### **1. Open-Source Text-to-Image Models**
- **Stable Diffusion (Optimized for CPU)**  
  - Model: `stable-diffusion-1.5` or `stable-diffusion-2.1` (smaller VRAM footprint)
  - Install via:
    ```bash
    pip install diffusers transformers torch torchvision
    ```
  - Example Usage:
    ```python
    from diffusers import StableDiffusionPipeline
    import torch
    
    pipe = StableDiffusionPipeline.from_pretrained("CompVis/stable-diffusion-v1-4")
    pipe.to("cpu")  # Run on CPU
    image = pipe("A futuristic soccer match with digital effects").images[0]
    image.show()
    ```

### **2. APIs for Cloud-Based Image Generation (Free Tiers Available)**
- **DeepAI** (`https://deepai.org/machine-learning-model/text2img`)
- **Replicate** (`https://replicate.com`) - Lightweight API-based inference for Stable Diffusion and other models.
- **Hugging Face Inference API** (`https://huggingface.co/inference-api`) - Provides free-tier cloud inference for multiple models.

### **3. Lightweight On-Device Image Generation Models**
- **Kandinsky 2.2**: Smaller than Stable Diffusion, optimized for CPU-based execution (`https://github.com/ai-forever/Kandinsky-2`)
- **Deep Dream Generator**: Can generate artistic visuals based on descriptions with minimal compute power.

## 🚀 Suggested Approach
1. **Preprocess Data**: Extract **patterns** from user bets (e.g., preferred sport, favorite teams, favourite type of betting etc.).
2. **Transform to Prompts**: Convert structured data into **descriptive text prompts** (e.g., "A dynamic background featuring Real Madrid, bold colors, and high-energy scenes").
3. **Generate Images**: Use AI models (local or API-based) to **convert text prompts into visuals**.
4. **Optimize for Aesthetics**: Post-process images with filters and color adjustments.
5. **Deliver Your Solution**: Create a demo app or simple script to generate user-specific backgrounds dynamically.

## 👤 Getting Started
1. **Download the dataset**
[gen-ai-personalized-backgrounds-dataset.csv](https://github.com/novibet-ai-hackathon/novibet-ai-hackathon/blob/main/gen-ai-personalized-backgrounds/gen-ai-personalized-backgrounds-dataset.csv)

2. **Install Dependencies**
   ```bash
   pip install pandas numpy diffusers transformers torch torchvision
   ```

## 📑 Submission Guidelines
- Document your approach clearly.
- Provide a script or notebook demonstrating your method.
- Include sample images generated for different users.
- Feel free to be creative with the visualization styles!

## 🎯 Final Thoughts
This challenge is all about blending **data science and creative AI**! Have fun experimenting with generative models and push the boundaries of **personalized AI-driven visual experiences**. 🚀

