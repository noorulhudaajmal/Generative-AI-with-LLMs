# PARAMETER EFFICIENT TUNING LLM

Fine tuning an LLM for the specified use-case is computationally challenging. 
PEFT is the of instruction fine-tuning that is much more efficient than full fine-tuning, with a slight trade-off of accuracy as regard to full fine-tunning.

PEFT is a generic term that includes Low-Rank Adaptation (LoRA) and prompt tuning (which is NOT THE SAME as prompt engineering!). In most cases, when someone says PEFT, they typically mean LoRA. LoRA, at a very high level, allows the user to fine-tune their model using fewer compute resources (in some cases, a single GPU). After fine-tuning for a specific task, use case, or tenant with LoRA, the result is that the original LLM remains unchanged and a newly-trained “LoRA adapter” emerges. This LoRA adapter is much, much smaller than the original LLM - on the order of a single-digit % of the original LLM size (MBs vs GBs).

That said, at inference time, the LoRA adapter needs to be reunited and combined with its original LLM to serve the inference request. The benefit, however, is that many LoRA adapters can re-use the original LLM which reduces overall memory requirements when serving multiple tasks and use cases.


