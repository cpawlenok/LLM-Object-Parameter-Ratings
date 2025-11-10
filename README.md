# LLM Property Rating Experiment
*Exploring how small language models can quantify abstract properties of real-world objects.*

## Overview
This project investigates whether a compact language model can estimate **quantitative properties** (e.g., weight, strength, hardness) for a diverse set of nouns.  
By prompting an LLM to rate each noun along multiple axes from **1–10**, the goal was to explore how consistently the model perceives object-level attributes—and how far prompt engineering can improve that reliability.

I used the **Phi-3-mini-4k-instruct** model (3.8B parameters), which runs comfortably on local hardware (~8GB VRAM) or in Google Colab.  
The entire experiment was designed to simulate data enrichment tasks, where models are asked to clean or expand qualitative data into structured, numerical representations.

---

## Project Structure
The workflow is divided into six key phases:

### 1. Collecting Nouns
I assembled a dataset of **50+ nouns** spanning people, places, and things (e.g., *airplane, ant, actor, adobe*).  
Each noun was stored in `nouns.txt` for later iteration and testing.

### 2. Defining Properties
Next, I created a list of **5–10 measurable properties** relevant across many nouns, such as:

- Weight  
- Strength  
- Intelligence  
- Speed  
- Fragility  

These were saved in `properties.txt` and served as the basis for model prompts.

### 3. Baseline Prompting
Each noun–property pair was rated by the model using **simple, uniform prompts** formatted as JSON lines, for example:

```json
{"pre-prompt": "Output ONLY 1-10. How heavy would you rate this noun: ", "property": "weight"}
{"pre-prompt": "Output ONLY 1-10. How intelligent would you rate this noun: ", "property": "intelligence"}
```
```cmd
git clone https://github.com/cpawlenok/llm-property-rating.git
cd llm-property-rating
jupyter notebook
```
