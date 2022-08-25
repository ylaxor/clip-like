# clip-like
Train (fine-tune) OpenAI's CLIP models on custom image-caption data sets, cf. COCO dataset.

# What's CLIP ?

CLIP (Contrastive Language-Image Pre-Training) is a neural network trained on a variety of (image, text) pairs. It can be instructed in natural language to predict the most relevant text snippet, given an image, without directly optimizing for the task, similarly to the zero-shot capabilities of GPT-2 and 3. We found CLIP matches the performance of the original ResNet50 on ImageNet “zero-shot” without using any of the original 1.28M labeled examples, overcoming several major challenges in computer vision.

[[Blog]](https://openai.com/blog/clip/) [[Paper]](https://arxiv.org/abs/2103.00020) [[Model Card]](model-card.md) [[Colab]](https://colab.research.google.com/github/openai/clip/blob/master/notebooks/Interacting_with_CLIP.ipynb)

# Usage

The notebook ’’fine-tune-clip.ipynb’’ could be used to train (fine-tune) a clip-like model from scratch. It illustrates the process on [COCO](https://cocodataset.org/#home) dataset. It leverages the VisionTextDualEncoderProcessor toolkit from Hugging Face transformers library. The dual encoder's encoders are pre-trained text and image networks that would be fine-tuned (along with a common projection head) to create adapted representations for text-image pairs by minimizing a constrastive loss computed using those representations. The objective is to maximize similarity between valid pairs and reduce it between invalid ones.

One should be able to launch the notebook on Colab free sessions without any problem.
