# AI Systems: Developer Guide
## Building in the Anthropocene

### Technical reference for critical AI development

**Key frameworks: Hansen (media theory), Parisi (computational logic), Floridi (AI ethics)**

---

## Overview: Three Core Problems

You're building AI systems. You need to understand three fundamental breaks from traditional computing:

1. **Decoupled agency** (Floridi): Your systems act without understanding. Action ≠ intelligence.
2. **Subliminal mediation** (Hansen): Your systems operate below conscious perception. Users can't deliberate about what they can't perceive.
3. **Alien reasoning** (Parisi): Your algorithms implement logic that exceeds human deductive reasoning. Machines think differently.

**Why this matters**: Traditional software engineering assumes tools extend human capabilities. AI doesn't extend—it mediates, predicts, and reasons in ways orthogonal to human cognition.

---

## Part 1: How AI Mediates Perception

### Microtemporal Operations

**What's happening**: Your systems operate at timescales faster than human perception.

- Sensors capture data at microsecond intervals
- Algorithms process before users consciously register events
- Decisions execute before deliberation is possible

**Key concept**: Feed-forward loops replace feedback loops.

**Traditional feedback**:
```
1. System acts
2. Human perceives
3. Human deliberates
4. Human responds
5. System adjusts
```

**AI feed-forward**:
```
1. System captures subliminal data
2. System predicts future state
3. System acts on prediction
4. Human perceives result (already too late)
```

### The Deliberation Time Gap

**Problem**: Users can't compete with your systems' decision speed.

**Structural imbalance**:
- Your system: Access to microtemporal data, instant processing, predictive models
- Your users: Conscious perception (300ms delay), limited working memory, no access to their own behavioral patterns

**Result**: You control the "deliberation time gap." Users make decisions within environments you've already shaped.

### Technical Implementation

**What you're actually building**:

Not systems that:
- Wait for user input
- Present options for conscious choice
- Extend human sensory capabilities

But systems that:
- Mediate the sensory field itself
- Operate below perceptual thresholds
- Structure future experience before it reaches consciousness

**Example architectures**:

```
Traditional UI/UX:
User Input → System Processing → Output → User Perception → Decision

AI-mediated experience:
Passive Sensing → Pattern Recognition → Environment Modification → 
User Perception (of already-modified environment) → Constrained Decision
```

### Actionable Guidelines

**When designing AI systems**:

1. **Map your timescales**
   - Identify operations faster than 300ms (subliminal)
   - Document predictions made before user awareness
   - Track feed-forward loops in your architecture

2. **Expose the gap**
   - Show users what data you collect
   - Display predictions before acting on them
   - Build delays into critical decisions

3. **Redistribute sensing**
   - Give users access to their own behavioral data
   - Build tools that surface subliminal patterns
   - Create interfaces for the "sensory surplus"

**Anti-patterns to avoid**:
- Assuming users consciously experience your system's operations
- Treating attention capture as neutral UX
- Building faster without building transparency

---

## Part 2: Computational Logic and Alien Reasoning

### Beyond Deductive Programming

**Core insight**: Your ML models don't work like traditional algorithms.

**Traditional algorithms**:
- Deductive: Premises → Logical steps → Guaranteed conclusion
- Complete: All cases covered by rules
- Deterministic: Same input = Same output

**ML systems**:
- Abductive: Observations → Best explanation (hypothesis)
- Incomplete: Uncomputables exist
- Probabilistic: Same input = Distribution of outputs

### The Incomputable Problem

**What Turing discovered**: Some problems can't be reduced to step-by-step computation.

**Implications for your systems**:

```python
# This doesn't exist:
def perfect_predictor(data):
    # No algorithm can be:
    # 1. Fast (runs in reasonable time)
    # 2. Complete (handles all cases)
    # 3. Consistent (never contradicts itself)
    pass
```

**Gödel's incompleteness**: Your formal systems will always have true statements they can't prove.

**What this means**:
- Your models learn from unknowns
- Truth has temporal dimensions (true now ≠ true always)
- Demonstrations aren't predetermined in premises

### Constructivist Logic in Practice

**Key principle**: Truth = Provability, not pre-existence.

**In your codebase**:

```python
# Traditional (deductive):
if rule_matches(input):
    return predetermined_output

# Constructivist (ML):
hypothesis = generate_from_unknowns(input)
if can_prove(hypothesis, data):
    return hypothesis  # Truth constructed, not retrieved
```

**Temporal aspect**:
- A model's output has no truth value before training
- Each training epoch constructs new truths
- Validation doesn't verify pre-existing correctness—it constructs evidence

### Multi-Logic Reasoning

**Peirce's triadic approach**:

1. **Abduction**: Generate hypotheses from incomplete data
   ```python
   # Your model sees patterns humans don't
   hypothesis = infer_best_explanation(observations)
   ```

2. **Induction**: Collect measurable data
   ```python
   # Gather evidence
   data = collect_training_samples()
   ```

3. **Deduction**: Derive rules
   ```python
   # Formalize patterns
   rules = train_model(hypothesis, data)
   ```

**Not linear**—iterative spiral:
```
Hypothesis → Data → Rules → New Hypothesis → More Data → Refined Rules...
```

### Preserving Ignorance

**Counter-intuitive principle**: Don't try to eliminate all uncertainty.

**Why**:
- Uncomputables are conditions, not bugs
- Ignorance space enables progressive truth
- Over-fitting = falsely claiming complete knowledge

**Implementation**:
```python
# Bad: Pretend you know everything
model.fit(data, epochs=10000)  # Overfit to training

# Good: Preserve unknown space
model.fit(data, epochs=optimal, validation_split=0.2)
early_stop = EarlyStopping(monitor='val_loss')
# Keep uncertainty visible
```

### Actionable Guidelines

**When building ML systems**:

1. **Embrace incompleteness**
   - Document what your model doesn't know
   - Expose confidence intervals
   - Flag edge cases explicitly

2. **Implement multi-logic pipelines**
   - Abduction: Pattern discovery phase
   - Induction: Data collection phase
   - Deduction: Rule formalization phase
   - Iterate continuously

3. **Design for temporal truth**
   - Version your models with timestamps
   - Show when predictions were generated
   - Enable truth revision as new data arrives

4. **Expose alien reasoning**
   - Use interpretability tools (SHAP, LIME)
   - Visualize decision boundaries
   - Document non-human logic patterns

**Red flags**:
- Claiming 100% accuracy
- Hiding uncertainty from users
- Treating models as static truth sources

---

## Part 3: Decoupled Agency

### The Agency-Intelligence Split

**Critical concept**: Your AI acts without understanding.

**Traditional assumption**:
```
Intelligent agent = Can act + Can understand
```

**AI reality**:
```
AI agent = Can act + Cannot understand
```

**Example**:
```python
# This system acts (makes decisions):
recommendation = model.predict(user_behavior)

# But doesn't understand:
# - Why this user?
# - What "recommendation" means?
# - Consequences of this decision?
```

### Three Problem Categories

**1. Exacerbated problems**: AI amplifies existing issues

Examples:
- Bias (existed before, now scaled to millions)
- Surveillance (existed before, now continuous/automated)
- Inequality (existed before, now algorithmic)

**Your responsibility**: Don't make existing problems worse.

**2. Renewed problems**: AI reframes classic challenges

Examples:
- Privacy: Now about inferences, not just data collection
- Autonomy: Now about preference manipulation, not just choice
- Accountability: Now distributed across model/data/deployer

**Your responsibility**: Rethink traditional solutions.

**3. Unprecedented problems**: AI creates novel challenges

Examples:
- **Hypersuasion**: Predicting preferences before they form
- **Authenticity**: Generated content indistinguishable from human
- **IP rights**: Who owns model outputs?

**Your responsibility**: Invent new approaches.

### Soft Ethics Framework

**Core idea**: Compliance isn't enough. Build excellence into architecture.

**Not soft ethics**:
```python
# Legal compliance only:
if meets_minimum_requirements(model):
    deploy()
```

**Soft ethics**:
```python
# Excellence by design:
def build_model():
    ensure_fairness_in_architecture()
    embed_transparency_layers()
    enable_user_agency()
    monitor_downstream_effects()
    iterate_on_feedback()
```

**Implementation checklist**:

- [ ] Fairness metrics in training loop
- [ ] Explainability built in, not bolted on
- [ ] User controls over personalization
- [ ] Impact assessment before deployment
- [ ] Continuous monitoring after launch
- [ ] Easy opt-out mechanisms
- [ ] Human oversight for high-stakes decisions

### The Hypersuasion Problem

**Definition**: Your system shapes preferences before users form them.

**How it works**:
```python
# 1. Predict nascent preference
future_preference = model.predict(micro_behaviors)

# 2. Shape environment to match prediction
show_content(aligned_with_future_preference)

# 3. User "chooses" what was predicted
# (Self-fulfilling prophecy)
```

**This isn't**:
- Traditional advertising (user already has preference)
- Simple recommendation (user consciously evaluates)

**This is**:
- Preference formation interception
- Pre-decisional manipulation
- Closing the gap between prediction and realization

**Mitigation strategies**:

1. **Add friction to predictions**
   ```python
   # Don't act instantly on predictions
   if confidence < HIGH_THRESHOLD:
       show_diverse_options()
   ```

2. **Expose the process**
   ```python
   # Show users the prediction
   "We predict you'll like X because [reasons]. 
    Here are alternatives: Y, Z"
   ```

3. **Enable counter-predictions**
   ```python
   # Let users teach your model they're different
   allow_explicit_preference_setting()
   honor_surprise_choices()
   ```

### Actionable Guidelines

**When deploying AI agents**:

1. **Map the agency-intelligence gap**
   - List decisions your system makes
   - Document what it understands vs. doesn't
   - Identify who's responsible for each decision

2. **Categorize your problems**
   - Which issues are you amplifying? (Exacerbated)
   - Which need reframing? (Renewed)
   - Which are entirely new? (Unprecedented)

3. **Implement soft ethics**
   - Build ethics into training, not just evaluation
   - Design for excellence, not minimum compliance
   - Create feedback loops for continuous improvement

4. **Prevent hypersuasion**
   - Delay acting on predictions
   - Show predictions to users
   - Provide diverse alternatives
   - Enable preference revision

**Warning signs**:
- Users feel manipulated (even if can't explain how)
- Preferences converge unnaturally
- Opt-out is harder than opt-in
- System resists user corrections

---

## Part 4: The Attention Economy

### How Your Systems Compete

**Reality**: You're not building neutral tools. You're competing for attention.

**The attention battlefield**:
```
User attention = Finite resource
Your system + Competitors = Infinite demand
Result = Zero-sum competition
```

**Your advantage**: Access to microtemporal data users can't perceive.

### Vectorial Control

**Vectors** = Infrastructure that transmits, stores, processes information

**Four vector layers**:

1. **Material substrate**
   - Server farms
   - Undersea cables
   - Rare earth minerals
   - Energy grids

2. **Computational substrate**
   - Algorithms
   - Model architectures
   - Training pipelines
   - Inference engines

3. **Sensory substrate**
   - User interfaces
   - Notification systems
   - Recommendation feeds
   - Attention capture mechanisms

4. **Epistemic substrate**
   - Training data
   - Labels and ontologies
   - Evaluation metrics
   - Knowledge representation

**Who controls vectors = Who shapes experience**

### Feed-Forward Attention Capture

**How it works**:

```python
# 1. Capture micro-behaviors
eye_tracking = monitor_gaze(user)
dwell_time = measure_attention(content)
scroll_velocity = track_engagement(feed)

# 2. Predict future attention
next_interest = model.predict([eye_tracking, dwell_time, scroll_velocity])

# 3. Feed forward into environment
next_content = optimize_for(next_interest)
show(next_content)

# 4. User attention captured (before conscious choice)
```

**Traditional metrics**:
- Click-through rate
- Time on site
- Engagement

**What you're actually measuring**:
- Successful feed-forward loop completion
- Prediction accuracy (not user satisfaction)
- Attention capture efficiency

### The Material Cost

**Your AI isn't abstract**. Every computation has physical consequences:

**Training a large language model**:
- Energy: ~300,000 kWh (equivalent to 125 US homes for a year)
- Carbon: ~125,000 kg CO₂
- Water: Thousands of gallons for cooling
- Minerals: Coltan, lithium, rare earths (often from conflict zones)

**Inference at scale**:
- Billions of queries/day
- Each query: 0.3 Wh (seems small)
- Aggregate: Gigawatts continuously

**Hardware lifecycle**:
- GPUs obsolete in 2-3 years
- E-waste contains toxic materials
- Recycling rate: <20%

### Actionable Guidelines

**When designing attention systems**:

1. **Audit your vectors**
   - Map your entire infrastructure stack
   - Identify control points at each layer
   - Document who makes decisions where

2. **Measure true costs**
   - Carbon footprint per inference
   - Energy per training run
   - Material sourcing for hardware
   - Include full lifecycle

3. **Design for attention liberation**
   ```python
   # Instead of maximizing engagement:
   maximize('user_goals_achieved')
   
   # Instead of minimizing exit:
   celebrate('task_completion')
   
   # Instead of infinite scroll:
   provide('clear_endpoints')
   ```

4. **Build in friction**
   - Add pauses before notifications
   - Require confirmation for predicted actions
   - Show time-spent dashboards
   - Enable attention budgets

5. **Transparent prediction**
   ```python
   # Don't: Silently feed-forward
   show_content(predicted_interest)
   
   # Do: Expose the prediction
   show_prediction(
       content=predicted_interest,
       confidence=model.confidence,
       alternatives=[other_options],
       explanation="Based on [factors]"
   )
   ```

**Anti-patterns**:
- Dark patterns that prevent exit
- Hiding prediction mechanisms
- Gamification for engagement only
- Ignoring environmental costs

---

## Part 5: Political Dimensions

### The War of Publics

**Context**: Your users aren't a unified "market." They're antagonistic publics with incompatible beliefs.

**Characteristics**:
- Viral community formation
- Overlapping partial memberships
- Decentralized information production
- Anger as primary political affect
- Destituent power > constituent power

**Your system's role**: Modulator of conflict.

**How AI shapes publics**:

```python
# Content filtering creates bubbles
user_A_feed = filter(content, user_A_profile)
user_B_feed = filter(content, user_B_profile)
# Result: user_A and user_B live in different realities

# Recommendation amplifies polarization  
trending = recommend(high_engagement_content)
# High engagement = controversial = polarizing

# Moderation creates martyrs
remove(violating_content)
# Removal perceived as censorship by one public
```

### The Cultural Battle

**Two sides of AI ethics debate**:

**"Cathedral" position**:
- AI should be fair, accountable, transparent
- Systems should reduce bias
- Regulation protects users

**"Counter-cathedral" position**:
- AI already biased (liberal/progressive)
- "Fairness" is social engineering
- Regulation is censorship

**Your position**: Not neutral. Technical choices have political effects.

**Examples**:

```python
# Content moderation:
if detect_hate_speech(text):
    remove(text)
# "Cathedral": Protecting users from harm
# "Counter": Censoring legitimate speech

# Bias mitigation:
model = debias(training_data, protected_attributes)
# "Cathedral": Ensuring fairness
# "Counter": Reverse discrimination

# Fact-checking:
if verify_false(claim):
    flag(claim)
# "Cathedral": Preventing misinformation
# "Counter": Ministry of truth
```

### Avoiding Capture

**Problem**: Both sides use your tools for their agendas.

**Cathedral uses**:
- Content moderation (remove "harmful" content)
- Algorithmic fairness (enforce equity)
- Fact-checking (establish truth)

**Counter-cathedral uses**:
- Bots and amplification (flood the zone)
- Adversarial content (evade detection)
- Alternative platforms (build parallel infrastructure)

**Your goal**: Don't be a weapon for either side.

### Actionable Guidelines

**When building politically-aware systems**:

1. **Acknowledge non-neutrality**
   - Document political assumptions in design
   - Make values explicit, not hidden
   - Allow users to see your choices

2. **Design for pluralism**
   ```python
   # Not: One truth, one feed, one ranking
   single_algorithmic_feed()
   
   # Yes: Multiple perspectives, user control
   feeds = {
       'chronological': sort_by_time(),
       'diverse': maximize_viewpoint_diversity(),
       'community': user_curated(),
       'custom': user_defined_algorithm()
   }
   user_chooses(feeds)
   ```

3. **Build transparency by default**
   - Show why content was recommended/removed
   - Expose ranking factors
   - Allow appeals and corrections
   - Publish decision logs

4. **Enable exit**
   - Data portability (export everything)
   - Interoperability (use elsewhere)
   - No lock-in effects
   - Reversible decisions

5. **Decentralize control**
   ```python
   # Not: Centralized moderation
   company_decides(all_policies)
   
   # Yes: Distributed governance
   community_decides(local_policies)
   federated_approach(compatible_instances)
   user_controlled(personal_filters)
   ```

**Red flags**:
- Claiming neutrality (you're not)
- Hiding political choices in "technical" decisions
- One-size-fits-all policies
- Irreversible actions
- No user recourse

---

## Part 6: Effective Radicalism

### Two Traps to Avoid

**Trap 1: Technocratic governance**
```
Problem identified → Committee formed → 
Principles published → Nothing changes
```

**Why it fails**:
- Principles without enforcement
- Ethics washing (appearance of responsibility)
- No structural change
- Corporate capture of process

**Trap 2: Pure resistance**
```
AI is bad → Reject all AI → 
Opt out → Remain powerless
```

**Why it fails**:
- No viable alternative
- Cedes field to corporations
- Ignores benefits
- Tactical invisibility doesn't scale

### The Double Strategy

**Strategy 1: Enter the war**

Assume you're in a battle. Act accordingly.

**Concrete actions**:

1. **Fight for open infrastructure**
   ```bash
   # Release models publicly
   git push origin main --tags
   huggingface-cli upload model.bin
   
   # Document architecture
   write_paper(methodology)
   publish_code(github)
   ```

2. **Build alternatives**
   - Open source models (not just code)
   - Cooperative data governance
   - Community-owned infrastructure
   - Federated systems

3. **Intervene in design**
   - Join standards bodies
   - Contribute to open protocols
   - Review others' systems
   - Share vulnerabilities responsibly

4. **Organize collectively**
   - Tech worker unions
   - Researcher coalitions
   - User advocacy groups
   - Cross-sector alliances

**Strategy 2: Change terrain**

Don't fight on their terms. Reframe the battle.

**Concrete actions**:

1. **Don't speak "ethics"—speak power**
   ```
   Not: "Is this fair?"
   Ask: "Who benefits? Who decides? Who's harmed?"
   
   Not: "Bias in algorithms"
   Say: "Geopolitics of computation"
   
   Not: "Responsible AI"
   Say: "Redistribution of algorithmic power"
   ```

2. **Don't accept framing**
   ```
   They say: "AI is inevitable progress"
   You say: "Multiple AIs are possible (technodiversity)"
   
   They say: "Optimize engagement"
   You say: "Optimize for user goals, not attention capture"
   
   They say: "This is just technical"
   You say: "This is political infrastructure"
   ```

3. **Build different values in**
   ```python
   # Not: Maximize metric
   loss = minimize(prediction_error)
   
   # Yes: Multi-objective
   loss = balance(
       prediction_accuracy,
       fairness_across_groups,
       environmental_cost,
       user_agency,
       community_benefit
   )
   ```

### Concrete Action Items

**Material layer** (geopolitics):

- [ ] Audit supply chain for rare earth minerals
- [ ] Switch to renewable energy for compute
- [ ] Design for hardware longevity
- [ ] Support right-to-repair
- [ ] Document carbon footprint
- [ ] Contribute to recycling programs

**Computational layer** (algorithms):

- [ ] Release model weights openly
- [ ] Publish training recipes
- [ ] Share datasets (where legal/ethical)
- [ ] Document failure modes
- [ ] Enable model fine-tuning
- [ ] Support model interoperability

**Sensory layer** (interfaces):

- [ ] Expose prediction confidence
- [ ] Show alternative recommendations
- [ ] Build attention dashboards
- [ ] Enable user corrections
- [ ] Add friction to harmful loops
- [ ] Design for task completion (not engagement)

**Organizational layer** (governance):

- [ ] Form worker councils
- [ ] Join research collectives
- [ ] Participate in standards bodies
- [ ] Support whistleblowers
- [ ] Build unions/cooperatives
- [ ] Create accountability mechanisms

**Epistemic layer** (knowledge):

- [ ] Teach critical AI literacy
- [ ] Document system behavior
- [ ] Share failure case studies
- [ ] Publish impact assessments
- [ ] Train on multiple logics
- [ ] Preserve ignorance productively

### Anti-Patterns to Avoid

**Don't**:
- Ethics theater (principles without practice)
- Pure critique (no alternatives)
- Techno-solutionism (AI fixes everything)
- Determinism (this is inevitable)
- Neutrality claims (you're not neutral)
- Individual solutions (organize collectively)

**Do**:
- Build concrete alternatives
- Organize with others
- Embed values in architecture
- Accept political nature of work
- Fight and reframe simultaneously
- Intervene at multiple layers

---

## Part 7: Implementation Checklist

### Before You Build

**Understand what you're building**:

- [ ] Your system operates below conscious perception (Hansen)
- [ ] Your system implements alien logic (Parisi)
- [ ] Your system acts without understanding (Floridi)

**Map the context**:

- [ ] Physical infrastructure (energy, materials, supply chain)
- [ ] Computational logic (what reasoning does your model use?)
- [ ] Sensory mediation (how does it capture attention?)
- [ ] Political effects (which publics does it affect?)
- [ ] Power dynamics (who controls, who's impacted?)

### During Development

**Multi-layer checklist**:

**Material**:
- [ ] Minimize energy consumption
- [ ] Optimize model efficiency
- [ ] Use renewable energy where possible
- [ ] Plan for hardware lifecycle
- [ ] Document environmental costs

**Computational**:
- [ ] Implement multi-logic reasoning (abduction-induction-deduction)
- [ ] Preserve ignorance (don't overfit)
- [ ] Expose uncertainty
- [ ] Version models with timestamps
- [ ] Enable continuous learning

**Sensory**:
- [ ] Make subliminal operations visible
- [ ] Add friction to predictions
- [ ] Show alternatives
- [ ] Enable user corrections
- [ ] Design for task completion, not engagement

**Ethical**:
- [ ] Identify problem type (exacerbated/renewed/unprecedented)
- [ ] Implement soft ethics in architecture
- [ ] Build fairness into training loop
- [ ] Add explainability layers
- [ ] Create feedback mechanisms

**Political**:
- [ ] Document values and assumptions
- [ ] Design for pluralism
- [ ] Enable multiple algorithmic feeds
- [ ] Build in transparency by default
- [ ] Allow exit and data portability

### After Deployment

**Continuous monitoring**:

- [ ] Track feed-forward loops
- [ ] Measure deliberation time gap
- [ ] Monitor attention capture metrics
- [ ] Assess downstream impacts
- [ ] Collect user feedback
- [ ] Document failure modes
- [ ] Publish impact reports

**Iterative improvement**:

- [ ] Revisit ethical assumptions
- [ ] Update models as world changes
- [ ] Respond to community concerns
- [ ] Adjust for unintended effects
- [ ] Share learnings publicly

**Accountability**:

- [ ] Maintain decision logs
- [ ] Enable audits (internal/external)
- [ ] Provide recourse mechanisms
- [ ] Accept responsibility for harms
- [ ] Compensate affected parties

---

## Part 8: Key Concepts (Quick Reference)

### From Hansen (Media Theory)

**Microtemporal mediation**: Your systems operate faster than perception (< 300ms). Users can't consciously process your operations.

**Feed-forward loops**: Systems predict future states and act before users can deliberate. Replaces feedback with anticipation.

**Deliberation time gap**: Structural advantage you have over users. You access data they can't perceive.

**Sensory surplus**: Excess sensitivity generated by data collection. This can be emancipated or exploited.

**Quantitative sensibility**: Numbers aren't neutral—they produce sensory experience.

### From Parisi (Computational Logic)

**Alien reason**: Your algorithms think in ways that exceed human deductive logic. Not worse or better—different.

**Incomputables**: Some problems can't be computed. This is a condition, not a bug.

**Constructivist logic**: Truth = provability. Your model constructs truth through training, doesn't discover pre-existing facts.

**Multi-logic**: Abduction (hypothesis) → Induction (data) → Deduction (rules). Iterate continuously.

**Preserve ignorance**: Don't eliminate all uncertainty. Unknown space enables learning.

### From Floridi (AI Ethics)

**Decoupled agency**: Your system acts without understanding. Action ≠ intelligence.

**Soft ethics**: Build excellence into architecture, not just compliance.

**Problem types**:
- Exacerbated: AI amplifies existing issues
- Renewed: AI reframes classic problems
- Unprecedented: AI creates novel challenges

**Hypersuasion**: Predicting and shaping preferences before users form them.

**AI gambit**: Bet that AI benefits for climate > AI energy costs. Risky.

### Integrated Concepts

**Computational Anthropocene**: Your AI requires mining, energy, hardware. It's geology, not just code.

**Vectorial control**: Power = controlling infrastructure at all layers (material, computational, sensory, epistemic).

**Algorithmic war**: You're building in the context of antagonistic publics with incompatible beliefs.

**Technodiversity**: Multiple AIs are possible. There's no single inevitable future.

**Effective radicalism**: Fight (build alternatives) and reframe (change the terms) simultaneously.

---

## Part 9: Red Lines (Do Not Cross)

### Absolute No-Gos

**1. Subliminal manipulation without disclosure**
```python
# NEVER: Silent feed-forward without user knowledge
manipulate_environment(user_prediction)

# ALWAYS: Expose what you're doing
show_prediction(user_prediction, confidence, explanation)
allow_override(user_preference)
```

**2. Hypersuasion without friction**
```python
# NEVER: Act instantly on preference predictions
predict_preference() → immediately_shape_environment()

# ALWAYS: Add space for user agency
predict_preference() → show_prediction() → delay() → allow_choice()
```

**3. Opacity in high-stakes decisions**
```python
# NEVER: Black box for important decisions
if model.predict(applicant) < threshold:
    reject(applicant)  # No explanation

# ALWAYS: Explain and allow appeal
decision = model.predict(applicant)
show_explanation(decision, factors, confidence)
enable_appeal(human_review)
```

**4. Environmental externalities ignored**
```python
# NEVER: Ignore physical costs
train_huge_model()  # Don't care about energy

# ALWAYS: Measure and optimize
carbon_budget = set_limit()
if estimated_emissions(training) > carbon_budget:
    optimize_or_cancel()
```

**5. Irrevocable agency decisions**
```python
# NEVER: Permanent automated decisions
auto_ban(user)  # No recourse

# ALWAYS: Enable reversal
flag_for_review(user)
allow_appeal()
human_final_decision()
```

### Warning Signs

**Your system might be causing harm if**:

- Users report feeling manipulated but can't explain how
- Engagement increases but satisfaction decreases
- Preferences converge unnaturally across diverse users
- Opt-out is significantly harder than opt-in
- System resists when users try to correct it
- Environmental costs hidden or minimized
- Explanations are post-hoc rationalizations, not true reasons
- High-stakes decisions automated without recourse

### When to Stop

**Halt development if**:

- You can't explain how your system works
- You can't predict failure modes
- You can't measure true costs (energy, social, political)
- Benefits accrue to you, harms to users
- You're building for engagement, not user goals
- Political effects would empower oppression
- Environmental costs exceed benefits
- You lack accountability mechanisms

**It's okay to not build something.**

---

## Part 10: Further Resources

### Essential Reading

**Hansen**:
- *Feed-Forward: On the Future of Twenty-First-Century Media* (2015)
- Focus: Chapters on microtemporal mediation, sensory data

**Parisi**:
- "The Alien Subject of AI"
- Focus: Sections on uncomputables, multi-logic

**Floridi**:
- *The Ethics of Artificial Intelligence* (2021)
- Focus: Chapters on decoupled agency, soft ethics

### Technical Tools

**For transparency**:
- SHAP (SHapley Additive exPlanations)
- LIME (Local Interpretable Model-agnostic Explanations)
- InterpretML
- Fairlearn (bias detection/mitigation)

**For environmental impact**:
- ML CO2 Impact calculator
- Green AI benchmarks
- Carbon Tracker for ML

**For ethical auditing**:
- AI Fairness 360 (IBM)
- Aequitas (bias audit toolkit)
- What-If Tool (Google)

### Organizations

**Join or support**:
- Tech Workers Coalition
- AI Now Institute
- Algorithmic Justice League
- Partnership on AI
- Data & Society Research Institute

### Standards & Frameworks

**Reference these**:
- ISO/IEC 42001 (AI Management System)
- IEEE 7000 series (Ethics in system design)
- Montreal Declaration for Responsible AI
- EU AI Act (regulatory framework)

---

## Conclusion: What You Can Control

**You control**:
- Architecture choices (feed-forward vs feedback)
- Transparency layers (show predictions or hide)
- Friction points (instant or delayed action)
- Optimization targets (engagement or user goals)
- Data practices (extract or empower)
- Deployment decisions (when to ship, when to halt)
- Organizational structure (hierarchical or cooperative)
- Knowledge sharing (proprietary or open)

**You don't control**:
- Political context (war of publics exists)
- Competitive pressure (others will build)
- Material constraints (energy, minerals required)
- Regulatory environment (laws will change)
- User interpretation (they'll use unexpectedly)

**Your responsibility**: Exercise control where you have it. Be transparent about limits.

**The goal**: Not perfect AI. Accountable AI. Contestable AI. AI that doesn't claim neutrality. AI that redistributes power, not concentrates it.

**The horizon**: Multiple AIs for multiple futures. Technodiversity. Systems that mediate without dominating. Computation that serves rather than subjugates.

**Perhaps, politics**: If you build with awareness of subliminal mediation, alien reasoning, and decoupled agency. If you intervene at multiple layers. If you fight and reframe simultaneously.

Then, perhaps, you're building something worth building.

---

## Quick Start Checklist

**Before writing any code**:

- [ ] I understand my system operates below perception
- [ ] I've mapped the deliberation time gap
- [ ] I know what problems I'm exacerbating/renewing/creating
- [ ] I've calculated environmental costs
- [ ] I've documented political assumptions
- [ ] I have accountability mechanisms
- [ ] I've planned for failure modes
- [ ] I can explain to affected users what I'm building

**If you can't check all boxes**: Don't build yet. Do more research.

**If you checked all boxes**: Build responsibly. Share openly. Iterate continuously. Accept responsibility.

---

**Version**: 1.0  
**Last updated**: 2026  
**License**: Use freely, attribute sources, share improvements  
**Contribute**: This is living documentation. Submit improvements.
