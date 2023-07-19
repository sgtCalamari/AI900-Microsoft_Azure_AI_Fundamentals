# Introduction to Azure OpenAI Service

## What is Generative AI?

- **Artificial Intelligence**: imitate human behavior by relying on machine models
- **Machine Learning**: algorithms take data to produce models to predict parameters
- **Deep Learning**: layers of algorithms for complex use cases. Many built on deep learning models
- **Generative AI**: produce new content based on what's described by inputs

##  Azure's OpenAI Service

- Consists of 4 components:
    - Pre-trained generative models
    - Customization capabilities: ability to fine-tune using your own data
    - Built-in tools to help detect and mitigate harmful use cases and implement AI responsibly
    - Enterprise-grade security with role-based access control (RBAC) and private networks
- 3 groupings for Azure AI services:
    - Azure ML platform
    - Applied AI Services
    - Cognitive Services: split into 5 pillars
        - Vision
        - Speech
        - Language
        - Decision
        - OpenAI
- Several overlapping capabilities between Cognitive Services and OpenAI with differences in pricing

## How to use Azure OpenAI

- Apply for access to Azure OpenAI
- REST APIs, Python SDK or web-based GUI (Azure OpenAI Studio)
- Azure OpenAI models include:
    - **GPT-4**: latest models for NLP and code
    - **GPT-3.5**: generate natural language and code based on inputs
    - **Embeddings**: convert text to numeric vectors for analysis (i.e. similarity comparison)
    - **DALL-E**: generate images based on descriptions
- Playgrounds available to workshop models by providing examples

## Understand OpenAI's natural language capabilities

- Natural language models are trained on words or chunks of characters known as "tokens"
    - i.e. "hamburger" may be chunked as ["ham", "bur", "ger"] while "pear" is one token
- GPT: generative pre-trained transformer
- Chatbots consist of a front-end for users to provide inputs and back-end that includes a generative AI model

## Understand OpenAI code generation capabilities

- OpenAI models are proficient in over a dozen languages, such as C#, JavaScript, Perl, PHP, and especially proficient in Python
- Codex models: based off GPT-3 and optimized to understand and write code
    - Developers can break down a goal into simpler tasks then use Codex to build them
    - Given a code snippet, can generate unit tests
    - Can summarize written functions, SQL queries/tables, convert functions between languages
- GitHub Copilot: dubbed an "AI pair programmer," integrates with IDEs like Visual Studio Code
    - Offers suggestions for code completion and infers from code comments

## Understand OpenAI's image generation capabilities

- Create image from prompt, base image, or both
- DALL-E: image capabilities categorized as image creation, image editing and image variation creation
    - The more detailed the prompt, the more likely to produce the desired output
    - Providing the style of art desired available for all three categories
    - Image edits are made by providing the original image and a transparent mask to indicate which area of the image to edit, with a prompt instructing the model to the nature of the edit
    - Image variations created by a supplied image and number of variants to create

## Describe Azure OpenAI access and responsible AI policies

- Development and deploy of AI systems need consideration to identify, measure and mitigate harm
- Transparency Notes are intended to help understand how Microsoft's AI technology works, the choices system owners can make that influence system performance and behavior, and the importance of thinking about the whole system ( including technology, people and the environment)
- Access to Azure OpenAI is currently limited and requires registration
    - Separate registration for experimentation and production deployment
    - Additional registration to modify content filters or modify abuse monitoring settings
