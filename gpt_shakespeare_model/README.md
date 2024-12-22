# Shakespeare Text Generation with GPT-2

This project fine-tunes GPT-2 on Shakespeare's works to generate Shakespeare-style text. It uses the `karpathy/tiny_shakespeare` dataset and the Hugging Face transformers library.

## Features

- Custom dataset handling with efficient text chunking
- Fine-tuning of GPT-2 with optimized hyperparameters
- Text generation with configurable parameters
- Training progress monitoring and checkpointing
- GPU acceleration support

## Requirements

```
torch
transformers
datasets
tensorboard
```

## Model Details

- Base model: GPT-2 (small)
- Context window: 1024 tokens
- Training setup: 5 epochs, batch size 4, gradient accumulation 2
- Mixed precision training (fp16)
- Final training loss: ~6.7
- Final validation loss: 3.16

## Sample Outputs

```
Prompt: "HAMLET: My kingdom for"
Output: "HAMLET: My kingdom for ever
Is in the hands of this traitor. O, look! my lord's face is pale; 
his eyes are heavy and he speaks so much ill..."

Prompt: "ROMEO: But soft, what light"
Output: "ROMEO: But soft, what light is it to your eyes?
I have seen the sun rise and fall in a thousand colours.
And yet I see no moon but that which lies between them..."
```

## Usage

1. Install dependencies
2. Run the training script:
```bash
python train.py
```

3. Generate text using the trained model:
```python
generated_text = generate_text("YOUR_PROMPT", model, tokenizer)
```

## Training Configuration

The model uses the following key parameters:
- Learning rate: 5e-5
- Warmup steps: 200
- Weight decay: 0.01
- Generation parameters:
  - Temperature: 0.7
  - Top-k: 20
  - Top-p: 0.9
  - No repeat ngram size: 4
  - Repetition penalty: 1.3

## Model Performance

The model shows strong capabilities in:
- Maintaining Shakespearean language style
- Character-appropriate dialogue
- Thematic consistency
- Dramatic structure
