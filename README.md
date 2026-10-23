# **Coding Assignment 4: Language Models, from RNNs to Transformers**

</br>

## **Overview**

This assignment is about **autoregressive** models, which factor a distribution over sequences into
one token at a time: each token is modeled as a conditional probability given the ones before it.
It is the approach behind every modern language model.

You'll build a character-level language model three ways, a simple RNN, a multi-layer RNN, and a
Transformer, and train each on short children's stories. Along the way you'll count what each
architecture costs to train and to generate from, which explains why Transformers won. You'll
finish by swapping characters for subword tokens, the way production systems do it.

---

## **Notebook**

### **CA4 — Language Model Architectures: RNNs to Transformers**

**Topics:**
- Recurrent neural networks (Elman cells, backpropagation through time)
- Multi-layer RNN architectures
- The Transformer (attention, causal masking, positional embeddings)
- Computational cost (FLOPs, sequential steps, parallelization)
- Real-world tokenization (SentencePiece, BPE)

**Point breakdown (60 points + 6 extra credit):**

| Section | Points |
|---------|--------|
| Exercise 1 — Recurrent generation | 8 pts |
| Exercise 2 — RNN training loop | 3 pts |
| Multi-layer RNN — implementation | 3 pts |
| Multi-layer RNN — training loop | 3 pts |
| Computational cost of the RNN (4 questions) | 7 pts |
| Transformer — implementation | 10 pts |
| Computational cost of the Transformer (4 questions) | 14 pts |
| Subword tokenization — train the tokenizer | 2 pts |
| Subword tokenization — subword dataset | 3 pts |
| Subword tokenization — train the RNN on subwords | 1 pt |
| Character vs. subword analysis (4 questions) | 6 pts |
| **Total** | **60 pts** |
| *Extra credit — Transformer with subword tokenization* | *+6 pts* |

---

## **Grading: 60 points here, 20 from discussion**

This assignment is worth **80 points total**.

| | Points |
|---|--------|
| Notebook in this repository | 60 |
| Group discussion | 20 |
| **Total** | **80** |

**How to read the point markers.** Every graded item carries exactly one point value, written in
square brackets next to it. A section heading never carries a separate total on top of the items
underneath it, so you can add up the brackets as you go and get the right number.

**About the discussion.** You'll be in a small group of about three students. We'll walk through
parts of the assignment together and ask you to talk through your own work: why you took a
particular approach, what gave you trouble, what you would do differently. You can also earn credit
by weighing in on a question put to someone else in your group.

Keep it relaxed. There's nothing extra to prepare beyond knowing what you submitted, and "I got
stuck on this part and looked it up" is a perfectly good answer. The point is to hear you reason
about your own code, not to catch anyone out.

---

## **Setup**

The notebook trains several small language models, so use a GPU. Either option works:

- **Explorer HPC.** Start a JupyterLab session on the `courses-gpu` partition through
  [Open OnDemand](https://ood.explorer.northeastern.edu/), using the course's shared Python
  environment at `/courses/CS7150.202710/shared/env/cs7150`. Everything this notebook needs is
  already installed there. The
  [course Explorer guide](https://docs.google.com/document/d/1nsP4YUBajdM6j3R0tA4gRnwo9qPdRv5gTtXHYdiXCz8/)
  walks through starting the session.
- **Google Colab.** Use the link at the top of the notebook, then switch to a GPU runtime
  (*Runtime → Change runtime type*).

The TinyStories dataset downloads automatically the first time you run the notebook.

To run locally instead:

```bash
pip install torch numpy matplotlib tqdm datasets sentencepiece ipywidgets
```

---

## **Submission Instructions**

### **Deliverables:**
- `CA4_LanguageModels.ipynb`

Keep the original filename. Zip the completed notebook into a single archive named:

```
CA4-Your-Last-Name.zip
```

For example, a student named Jordan Rivera submits `CA4-Rivera.zip`.

### **Requirements:**
- All TODO sections filled in with working code
- All questions answered in the markdown cells marked "YOUR ANSWER:"
- Generated outputs visible (loss plots, sample text)
- Notebook runs top to bottom without errors

### **Where to submit:**
Post your zip file as a direct **reply** to the **Coding Assignment 4** discussion thread on Canvas.
You'll find that thread in the **Coding Assignments** module for the week this assignment is due.

- Reply to the existing thread — do not start a new one.
- Attach the zip file — do not upload the notebook on its own.
- If you cannot find the thread, check the course Canvas page or contact the TA (see *Getting Help*).

---

## **Resources**

**Papers referenced:**
- RNNs: Elman (1990) — *Finding Structure in Time*
- Transformers: Vaswani et al. (2017) — [*Attention Is All You Need*](https://arxiv.org/abs/1706.03762)
- TinyStories: Eldan and Li (2023) — [*How Small Can Language Models Be and Still Speak Coherent English?*](https://arxiv.org/abs/2305.07759)

**Additional reading:**
- [Andrej Karpathy's nanoGPT](https://github.com/karpathy/nanoGPT)
- [ARENA Transformer Tutorial](https://arena-chapter1-transformer-interp.streamlit.app/)
- [SentencePiece](https://github.com/google/sentencepiece)

---

## **Getting Help**

If you hit a problem with the notebook, spot an error, or have a question about the setup, please
reach out. Email me at **[patel.pranav2@northeastern.edu](mailto:patel.pranav2@northeastern.edu)**
or send me a message on Microsoft Teams.

---

## **Academic Integrity**

- **Collaboration:** Follow the course syllabus policy on collaboration
- **Citations:** Credit any external resources, discussions, and AI assistance you used
- **Code reuse:** Cite any code adapted from online sources
- **Individual work:** Submit your own implementations — copying code is prohibited
