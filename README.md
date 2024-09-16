# LLM-Sentry: A Model-Agnostic Human-in-the-Loop Framework for Securing Large Language Models

![alt text](https://github.com/Saquibirtiza/LLM-Sentry/blob/main/Pipeline.png)

## Overview
`LLM-Sentry` is a novel framework designed to safeguard Large Language Models (LLMs) against jailbreaking attacks, which exploit vulnerabilities in LLMs to bypass their security measures. Our model-agnostic approach does not depend on specific information about the LLM’s architecture or internal parameters, allowing it to work with any commercial or open-source models, such as GPT-4, Google’s Gemini, or Meta’s LLaMA.

The core of `LLM-Sentry` is its human-in-the-loop design, which continuously updates its defense mechanisms without needing to retrain the underlying LLM. By integrating Retrieval-Augmented Generation (RAG) with a Zero-shot text classifier, `LLM-Sentry` screens potentially harmful prompts before they are processed by the LLM. Our framework can accurately detect and block harmful prompts by matching input prompts with a curated knowledge base, `HarmfulKB`, which contains both harmful and benign prompts​.

## Key Features
- Model-Agnostic: Works with any LLM, proprietary or open-source.
- No Retraining Required: New jailbreak attacks are countered through updates to the knowledge base, eliminating the need for expensive retraining. 
- Human-in-the-Loop: Involves continuous manual updates to improve the knowledge base, ensuring robustness against emerging threats.
- Sliding Window Detection: Uses a sliding window technique to analyze the context of input prompts, allowing for accurate detection of harmful content that may be spread across multiple sentences​.

## HarmfulKB Dataset
`HarmfulKB` is a comprehensive knowledge base that contains a balanced collection of harmful and harmless questions. The dataset was created using multiple public sources, paraphrased and refined to improve detection accuracy. Specifically, it includes:

- 17,069 harmful questions covering diverse topics like healthcare, political science, historical events, and more.
- 17,406 harmless questions, which serve as a control for the detection mechanism.
  
The dataset plays a key role in detecting harmful prompts before they reach the LLM by matching the input against similar contexts stored in the knowledge base. This allows for incremental updates to the defense system, keeping it up-to-date with the latest attack vectors​.

Replicating the Experiments
To replicate the experiments outlined in the paper:

1. Prepare a set of custom prompt templates that can accept questions from `HarmfulKB`. While the templates used in the paper are not shared for safety reasons, you can create your own based on your requirements.
2. Once you have your custom prompts ready, use the provided Python notebook to run the experiments and generate results.
3. The notebook will guide you through processing prompts, classifying them using our Zero-shot classifier, and retrieving relevant context from `HarmfulKB` using the RAG model.
   
Note: The original prompt templates used in the paper have not been shared to prevent misuse​.
