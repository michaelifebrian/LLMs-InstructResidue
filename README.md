# Injecting New Knowledge to LLMs
### Balancing Continuous Pre-Training and Instruction Fine-Tuning: Optimizing Instruction-Following in LLMs (Jindal, Ishan, et al., 2024)

This repository implements the concepts from the paper *"[Balancing Continuous Pre-Training and Instruction Fine-Tuning: Optimizing Instruction-Following in LLMs](https://arxiv.org/abs/2410.10739)"* by Jindal, Ishan, et al. (2024). It explores how to add new knowledge to a fine-tuned instruction LLM model without retraining on supervised Q&A datasets or compromising instruction-following (IF) abilities.

---

## 📖 Key Idea

The approach involves separating the **instruction-following abilities** from the model parameters, referred to as the **Instruct-Residue**. The steps are:

1. **Pretrain a Base LLM Model** using unstructured text data.
2. **Fine-Tune with Q&A Data** to obtain the Final Instruct LLM Model.
3. **Extract the Instruct-Residue** by subtracting the base model's parameters from the final instruct model:
   ```
   Instruct Residue = Final Instruct LLM Model - Pretrained LLM Base Model
   ```
5. **Update the Base Model** with new unstructured data.
6. **Combine the Updated Base Model with the Instruct-Residue** to preserve IF abilities while integrating new knowledge:
   ```
   Final Updated model = Updated base model + Instruct Residue
   ```

On the notebook, the final updated model was pushed to your HuggingFace repo.
