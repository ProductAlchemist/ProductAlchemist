# AI PM Learning Path - Karpathy Curriculum

**Purpose:** Structured 6-week plan to gain AI/LLM/RAG expertise through hands-on building

**Goal:** "Become PM expert in AI/LLM/RAG through hands-on building" (from USER-PROFILE.md)

**Last Updated:** Feb 7, 2026

---

## Why Andrej Karpathy's Materials?

**Who is Karpathy:**
- Former Tesla AI Director, OpenAI founding member
- Created "Neural Networks: Zero to Hero" educational course
- Known for making AI/deep learning accessible through minimal, educational code

**Matches your learning style:**
- ✅ Step-by-step guidance with explanations (you prefer understanding "why" before "how")
- ✅ Hands-on code you can run and modify (not just theory)
- ✅ Explains fundamentals from scratch (builds intuition)
- ✅ Minimal dependencies (can run locally on your Windows setup)

---

## PM Value Proposition

### Better Product Decisions
- ✅ Understand token limits aren't arbitrary (context windows = memory constraints)
- ✅ Evaluate vendor claims (is fine-tuning needed vs prompt engineering?)
- ✅ Scope technical feasibility (can we build this in-house vs API?)
- ✅ Design better AI product features (know what's possible vs impossible)

### Technical Credibility
- ✅ Speak engineer's language in AI product discussions
- ✅ Challenge assumptions with first-principles thinking
- ✅ Write better PRDs for AI features (understand implementation constraints)
- ✅ Debug AI product issues intelligently (is it data, model, or prompt?)

### Interview Edge
- ✅ Stand out in AI PM interviews (most PMs don't understand internals)
- ✅ Discuss trade-offs intelligently (model size vs latency vs cost)
- ✅ Answer "How would you build X with AI?" with technical depth
- ✅ Add "LLM Fundamentals (Karpathy)" to resume skills section

---

## 6-Week Curriculum

### Week 1: Neural Network Fundamentals

**YouTube Lectures** (Watch first):
- "The spelled-out intro to neural networks and backpropagation: building micrograd"
- Duration: ~2 hours

**Hands-On** (Clone and run):
```bash
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\AI-PM-Learning-Journey"
git clone https://github.com/karpathy/micrograd.git
cd micrograd
python demo.py
```

**What You'll Learn:**
- How neural networks actually learn (backpropagation)
- What "training" means mathematically
- Why gradient descent works

**PM Application:**
- Understand why AI models need training data (can't just program rules)
- Recognize when retraining is necessary vs fine-tuning
- Estimate computational costs for training

**Modify & Experiment:**
- Change learning rate → observe convergence speed
- Add more layers → see diminishing returns
- Break something → fix it (best way to learn)

**Time:** 3-4 hours (lecture + hands-on)

---

### Week 2: Language Models from Scratch

**YouTube Lectures:**
- "The spelled-out intro to language modeling: building makemore"
- Duration: ~2.5 hours

**Hands-On:**
```bash
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\AI-PM-Learning-Journey"
git clone https://github.com/karpathy/makemore.git
cd makemore
python makemore.py
```

**What You'll Learn:**
- How language models predict next token
- Character-level vs word-level models
- Why context matters (context window)

**PM Application:**
- Understand why ChatGPT can't "remember" long conversations (context limits)
- Design better chat UX (show token count, warn before limit)
- Evaluate LLM APIs (context window = key differentiator)

**Modify & Experiment:**
- Train on your own text (Porter PRD documents?)
- Vary context window size → see quality vs speed trade-off
- Generate text → observe common failure modes

**Time:** 4-5 hours

---

### Week 3: Transformer Architecture (Part 1)

**YouTube Lectures:**
- "Let's build GPT: from scratch, in code, spelled out"
- Duration: ~3 hours (dense, may need to rewatch sections)

**Hands-On:**
```bash
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\AI-PM-Learning-Journey"
git clone https://github.com/karpathy/nanoGPT.git
cd nanoGPT
python train.py config/train_shakespeare_char.py
```

**What You'll Learn:**
- Attention mechanism (the breakthrough behind GPT)
- Why transformers scaled better than RNNs
- Multi-head attention, positional encoding

**PM Application:**
- Understand GPT-4 vs GPT-3.5 architectural differences
- Design features leveraging attention (summarization, Q&A)
- Estimate inference costs (attention is O(n²) in context length)

**Modify & Experiment:**
- Reduce model size → observe quality degradation
- Change number of attention heads → see impact
- Train on small dataset → understand data requirements

**Time:** 5-6 hours (this week is denser)

---

### Week 4: Transformer Architecture (Part 2)

**YouTube Lectures:**
- Continue "Let's build GPT" (finish remaining sections)
- Rewatch attention mechanism explanation if needed

**Hands-On:**
```bash
# Continue with nanoGPT
# Try different configs:
python train.py config/train_gpt2.py
```

**What You'll Learn:**
- Layer normalization, residual connections
- Why deeper models train better with skip connections
- Scaling laws (bigger models = better performance, but at what cost?)

**PM Application:**
- Understand why GPT-4 costs more than GPT-3.5 (inference cost scales with size)
- Trade-off decisions: quality vs cost vs latency
- When to use smaller models (edge deployment, real-time apps)

**Modify & Experiment:**
- Remove layer norm → see training instability
- Add more layers → observe training time increase
- Profile inference speed → understand latency sources

**Time:** 5-6 hours

---

### Week 5: Tokenization & Production Considerations

**YouTube Lectures:**
- "Let's build the GPT Tokenizer" (if available, or read BPE paper)

**Hands-On:**
```bash
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\AI-PM-Learning-Journey"
git clone https://github.com/karpathy/minbpe.git
cd minbpe
python train.py
```

**What You'll Learn:**
- Why tokenization matters (affects model efficiency)
- Byte-Pair Encoding (BPE) algorithm
- Token limits ≠ character limits (varies by language)

**PM Application:**
- Design better token usage UI (show "tokens used" not just "characters")
- Understand why some prompts are more expensive (token density)
- Optimize prompts for cost (reduce redundant tokens)

**Modify & Experiment:**
- Tokenize different languages → observe efficiency differences
- Compare GPT-4 vs GPT-3.5 tokenizers → see evolution
- Measure token overhead → optimize your own prompts

**Time:** 3-4 hours

---

### Week 6: Capstone - Build Something Useful

**Project Ideas:**
1. **AI-Powered Porter Insights Bot**
   - Train nanoGPT on your Porter PRDs and case studies
   - Generate Q&A: "What was learned from lending platform?"
   - PM Value: Demonstrates "learning from documentation" capability

2. **Resume Bullet Generator**
   - Fine-tune on high-quality resume bullets
   - Input: Raw achievement → Output: Polished bullet
   - PM Value: Showcases AI for content generation

3. **YouTube Analytics Explainer**
   - Train on YouTube analytics data
   - Natural language queries: "Why did video X perform well?"
   - PM Value: Demonstrates AI for business intelligence

**Hands-On:**
```bash
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\AI-PM-Learning-Journey"
mkdir my-ai-project
# Use nanoGPT as base, customize for your use case
```

**What You'll Learn:**
- Data preparation for real-world use case
- Fine-tuning vs training from scratch
- Evaluation metrics (perplexity, accuracy, user satisfaction)

**PM Application:**
- End-to-end AI product development (data → training → deployment)
- Real-world constraints (data quality, compute limits, user expectations)
- Iterative improvement (v1 → v2 based on feedback)

**Deliverable:**
- Working prototype (even if rough)
- Blog post or GitHub README explaining what you built
- Add to resume: "Built custom LLM for [use case]"

**Time:** 8-10 hours (spread across week)

---

## Progress Tracking

### Completion Checklist

**Week 1: Micrograd**
- [ ] Watched "building micrograd" lecture
- [ ] Cloned and ran micrograd demo
- [ ] Modified learning rate and observed results
- [ ] Can explain backpropagation in plain English

**Week 2: Makemore**
- [ ] Watched "building makemore" lecture
- [ ] Cloned and ran makemore
- [ ] Trained on custom text dataset
- [ ] Can explain next-token prediction

**Week 3-4: NanoGPT**
- [ ] Watched "Let's build GPT" lecture (full)
- [ ] Cloned and trained nanoGPT on Shakespeare
- [ ] Experimented with model size variations
- [ ] Can explain attention mechanism to engineer

**Week 5: Tokenization**
- [ ] Understood BPE algorithm
- [ ] Ran minbpe examples
- [ ] Compared different tokenization strategies
- [ ] Can explain why token limits matter

**Week 6: Capstone**
- [ ] Built working AI prototype
- [ ] Documented learnings in GitHub README
- [ ] Added to portfolio/resume
- [ ] Can demo to interviewer

---

## Integration with Existing Work

### Add to Resume (After Completion)

**Before:**
- Skills: SQL, Mixpanel, Tableau, AI prototyping

**After:**
- Skills: SQL, Mixpanel, Tableau, AI prototyping, **LLM Fundamentals (Karpathy)**
- Projects: Built custom GPT model for [use case] (nanoGPT, PyTorch)

### Add to GitHub Profile

**Create:**
- `AI-PM-Learning-Journey/karpathy-course/` folder
- README.md with learnings summary
- Link from main profile README
- Showcase capstone project

### Add to Interview Prep

**Technical Depth Questions:**
- "Explain how transformers work" → Can answer with first principles
- "When would you use GPT-4 vs fine-tuned GPT-3.5?" → Understand trade-offs
- "How would you reduce AI feature costs?" → Know tokenization, caching, prompt optimization

---

## Recommended Schedule

**Intensity:** 2-3 hours/week (manageable alongside job)

**Timeline:** 6 weeks = 1.5 months

**Best Time:**
- Weekends: 1-2 hour deep work sessions
- Weeknights: 30-min lecture watching (can do passively)

**Completion Target:** Mid-March 2026 (starting Feb 7)

---

## Success Metrics

### Technical Understanding
- ✅ Can explain transformers without slides (whiteboard test)
- ✅ Can debug simple AI product issues (prompt vs model problem)
- ✅ Can estimate costs for LLM features (token usage × API pricing)

### Career Impact
- ✅ Added "LLM Fundamentals" to resume skills
- ✅ Built AI project on GitHub (demonstrates hands-on ability)
- ✅ Confident discussing AI in PM interviews

### Product Intuition
- ✅ Can evaluate AI vendor claims critically
- ✅ Can scope AI features realistically
- ✅ Can write better AI product PRDs

---

## Resources

### GitHub Repositories
- **micrograd:** https://github.com/karpathy/micrograd
- **makemore:** https://github.com/karpathy/makemore
- **nanoGPT:** https://github.com/karpathy/nanoGPT
- **minbpe:** https://github.com/karpathy/minbpe

### YouTube Playlist
- Search: "Andrej Karpathy Neural Networks Zero to Hero"
- Channel: Andrej Karpathy
- Playlist URL: (find and bookmark)

### Local Storage
- Clone to: `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\AI-PM-Learning-Journey`
- Use AI-PM-Learning-Journey repo for all course work

---

## Troubleshooting

### "Import errors when running Python scripts"
```bash
# Install PyTorch:
python -m pip install torch numpy matplotlib

# If CUDA errors (don't worry, CPU is fine for learning):
# Use CPU-only version
```

### "Code is too complex to understand"
- Rewatch lecture section explaining that part
- Add print statements to see intermediate values
- Ask Claude Code to explain specific functions
- Remember: Goal is PM understanding, not becoming ML engineer

### "Not enough time this week"
- Skip hands-on experiments, just watch lectures
- Catch up next week
- Quality > speed (better to understand deeply than rush)

---

## Next Steps (After Completion)

### Advanced Topics (Optional)
- **Reinforcement Learning from Human Feedback (RLHF):** How ChatGPT is fine-tuned
- **Retrieval-Augmented Generation (RAG):** Combining LLMs with knowledge bases
- **Fine-tuning vs Prompt Engineering:** When to use each approach

### Apply to Porter Work
- Could Porter lending platform benefit from AI underwriting?
- Could taxation platform use LLM for rule interpretation?
- Could fraud detection improve with ML models?

### Apply to Side Projects
- YouTube automation: AI-generated video scripts?
- Cipher game: AI-powered hint system?
- Resume reviewer: AI-powered bullet optimization?

---

**Remember:** The goal is PM expertise, not ML engineering. You're learning HOW AI works to build BETTER AI products, not to replace engineers. Focus on understanding trade-offs, constraints, and possibilities.

**When stuck:** Ask Claude Code for help. I'm here to guide you through this journey.
