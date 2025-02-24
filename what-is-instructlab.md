# Overview

InstructLab is an open source project for enhancing large language models (LLMs) used in generative artificial intelligence (gen AI) applications. Created by IBM and Red Hat, the InstructLab community project provides a cost-effective solution for improving the alignment of LLMs and opens the doors for those with minimal machine learning experience to contribute.

## Join the InstructLab community

## What does InstructLab do?

LLMs can power a range of useful applications like chatbots and coding assistants. These LLMs can be proprietary (such as OpenAI’s GPT models and Anthropic’s Claude models) or offer varying degrees of openness around pretraining data and usage restrictions (such as Meta’s Llama models, Mistral AI’s Mistral models, and IBM’s Granite models).

AI practitioners often need to adapt a pretrained LLM to suit a particular business purpose. But there are limits to the ways you can modify an LLM:

- Fine-tuning an LLM to understand a specific area of knowledge or skills typically involves forking an existing open model, then running expensive, resource-intensive training.
- There’s no way to incorporate improvements back to the upstream project, and thus no way for models to continuously improve from community contributions.
- LLM refinements have typically required large amounts of human-generated data, which can be time-consuming and expensive to get.

InstructLab follows an approach that punches through those limitations. It can enhance an LLM using far less human-generated information and far fewer computing resources than are typically used to retrain a model. And it makes it possible for upstream contributions to continuously make the model better.

InstructLab is named after and based on IBM Research’s work on Large-scale Alignment for chatBots, abbreviated as LAB. The LAB method is described in a 2024 research paper by members of the MIT-IBM Watson AI Lab and IBM Research.

InstructLab is not model-specific. It can provide supplemental skills and knowledge fine-tuning to an LLM of your choice. This “tree of skills and knowledge” improves continuously from community contributions and can be applied to support regular builds of an enhanced LLM. InstructLab maintains an enhanced version of IBM Granite. Two other lab-enhanced models released by IBM include Labradorite, which is derived from Llama 2, and Merlinite, which is derived from Mistral. The InstructLab project prioritizes fast iteration and intends to retrain models on a regular basis. Organizations can also use the InstructLab model alignment tools to train their own private LLMs with their own proprietary skills and knowledge.

## Red Hat resources

### Keep reading

## How does InstructLab work?

The LAB method consists of three components:

1. **Taxonomy-driven data curation** - Taxonomy is a set of diverse training data curated by humans as examples of new knowledge and skills for the model.
2. **Large-scale synthetic data generation** - The model is then used to generate new examples based on the seed training data. Recognizing that synthetic data can vary in quality, the LAB method adds an automated step to refine the example answers, making sure they’re grounded and safe.
3. **Iterative, large-scale alignment tuning** - Finally, the model is retrained based on the set of synthetic data. The LAB method includes two tuning phases: knowledge tuning, followed by skill tuning.

The contributions of data from the community can lead to regular iterative builds of enhanced LLMs, each made better by the tree of skills generated from community contributions.

## How is InstructLab different from other methods of training an LLM?

### Pretraining

During pretraining, an LLM is trained to predict the next token using trillions of tokens of unlabeled data. This gets really expensive, sometimes requiring thousands of GPUs and months of time. Pretraining a highly capable LLM is only possible for organizations with significant resources.

### Alignment tuning

After pretraining, LLMs undergo alignment tuning to make the model’s answers as accurate and useful as possible. The first step in alignment tuning is typically instruction tuning, in which a model is trained directly on specific tasks of interest. Next is preference tuning, which can include reinforcement learning from human feedback (RLHF). In this step, humans test the model and rate its output, noting if the model’s answers are preferred or unpreferred. An RLHF process may include multiple rounds of feedback and refinement to optimize a model.

Researchers have found that the amount of feedback at this alignment tuning stage can be much smaller than the initial set of training data—tens of thousands of human annotations, compared to the trillions of tokens of data required for pretraining—and still unlock latent capabilities of the model.

### InstructLab

The LAB method emerged from the idea that it should be possible to realize the benefits of model alignment from an even smaller set of human-generated data. An AI model can use a handful of human examples to generate a large amount of synthetic data—then refine that list for quality—and use that high-quality synthetic data set for further tuning and training. In contrast to instruction tuning, which typically needs thousands of examples of human feedback, LAB can make a model significantly better using relatively few examples provided by humans.

## How is InstructLab different from retrieval-augmented generation (RAG)?

The short answer is InstructLab and retrieval-augmented generation (RAG) solve different problems.

RAG is a cost-efficient method for supplementing an LLM with domain-specific knowledge that wasn’t part of its pretraining. RAG makes it possible for a chatbot to accurately answer questions related to a specific field or business without retraining the model. Knowledge documents are stored in a vector database, then retrieved in chunks and sent to the model as part of user queries. This is helpful for anyone who wants to add proprietary data to an LLM without giving up control of their information, or who needs an LLM to access timely information.

This is in contrast to the InstructLab method, which sources end-user contributions to support regular builds of an enhanced version of an LLM. InstructLab helps add knowledge and unlock new skills of an LLM.

It’s possible to "supercharge" a RAG process by using the RAG technique on an InstructLab-tuned model.

## Learn more about RAG

## What are the components of the InstructLab project?

InstructLab is composed of several projects.

### Taxonomy

InstructLab is driven by taxonomies, which are largely created manually and with care. InstructLab contains a taxonomy tree that lets users create models tuned with human-provided data, which is then enhanced with synthetic data generation.

### Command-line interface (CLI)

The InstructLab CLI lets contributors test their contributions using their laptop or workstation. Community members can use the InstructLab technique to generate a low-fidelity approximation of synthetic data generation and model-instruction tuning without access to specialized hardware.

### Model training infrastructure

Finally, there’s the process of creating the enhanced LLMs. It takes GPU-intensive infrastructure to regularly retrain models based on new contributions from the community. IBM donates and maintains the infrastructure necessary to frequently retrain the InstructLab project’s enhanced models.

## Discover Red Hat Enterprise Linux AI

When you’re ready to bring AI to the enterprise, Red Hat® Enterprise Linux® AI brings together the Granite family of open source-licensed LLMs, InstructLab model alignment tools, a bootable image of Red Hat Enterprise Linux, enterprise-grade technical support, and model intellectual property indemnification.
