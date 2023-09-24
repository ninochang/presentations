footer: nino.chang@swag.live
slidenumbers: true
build-lists: true

![fit](https://storage.googleapis.com/gweb-cloudblog-publish/images/GCN23_GE_BlogHeader_2436x1200_10.max-2500x2500.png)
# [fit] Google Next 23'

---
[.build-lists: false]

# Outline
- *Duet AI* integration to GCP products
- *VertexAI* updates
- *Infrustructures & Ops tool* update for *ML*
- Sessions sharing
    1. Build an *AIOps* platform at enterprise scale with Google Cloud
    2. What's new in modern *CI/CD* on Google Cloud
    3. Running large-scale *ML* on *GKE*
    4. *Prompt engineering*: Getting the skill your team needs next

---

# [fit] **Duet AI**
---
[.build-lists: false]

# Features
- Assisted development
- Assited operations
- Assisted data
- Assisted no code development
- Assisted security

---
# Assisted Development
- (2023) vscode[^1] / cloudshell 
- (Future) PyCharm / Intel / IntelliJ IDEA / GoLand / WebStorm
- Real time code completion/generation and autofix suggestions.
- Providing code license attribution
- Chat[^2]
    - Explain code
    - Suggest a test plan

[^1]: vscode integration [document](https://cloud.google.com/code/docs/vscode/install)

[^2]: chat with Duet AI [document](https://cloud.google.com/code/docs/vscode/write-code-duet-ai)

---
Demo VScode

---
# Assisted Operations
- Get help where you are
- Transition from your question to cloud shell command
- Contextualize log explanations
- Looker studio insight generation
- meet
    - realtime translate/transcript
    - summarize meet content textually

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/duet-get-help-where-you-are.png)

^ `Get help where you are`.
Suggestion to reduce cost
- cloud shell command
- use commitment discounts

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/duet-contextualize-log-explanations.png)

^ `contextualize log explainations`.
- explain why error happens
- further move to check 

---

# Assisted Data
- SQL Completion
- SQL Generation
- SQL Generation-Iteration
- SQL Explainability

---
Demo bigquery suggestion.
- -- Find Nino's salary from `playground.employees`
- -- Use queryqbove filter out salary higher than 1000
- -- Find all employee of engineering department for join `playground.employees` and `playground.departments`

---
# Assisted no code development
- with App sheet[^1]
- Build app conversationally

[^1]: [app sheet](https://www.appsheet.com/home/apps)

---
# Assisted security
Duet AI integrated with
- Madiant
- Chronicle

---
# [fit] **VertexAI**

---

# Vision - Generation
- Digital watermarking
- image styling traing and apply

---
![inline](https://storage.googleapis.com/nino-public/presentations/google-next-23/vision-generate-truck.png)![inline](https://storage.googleapis.com/nino-public/presentations/google-next-23/vision-generate-golden-style-training.png)
![inline](https://storage.googleapis.com/nino-public/presentations/google-next-23/vision-generate-golden-style-apply.png)

---
# LLMs
- variaties of model ready to use as fundamantal.
    - Llama2 (2023/7)
    - Code Llama (2023/8)
    - Palm (2023/3)
    - up to 47 basic models.

---

# [fit] **Infrustructures & Ops tools**
# [fit] for **ML**

---
# Ops tools
- GKE enterprise[^1]
- Titanium system
- Cross cloud network

[^1]: [Comparison](https://cloud.google.com/kubernetes-engine/docs/concepts/gke-editions#edition_features)

---

# Infra
- A3 VMs + Nvidia H100 GPU[^1]
    - Deploy A3 on VertexAI or GKE
    - 10x more network bandwidth compared to our A2 VM (GPU-to-GPU data transfer)
- Cloud TPU v5e
- Nvidia alliance
    - DGX cloud in google cloud

[^1]: [A3](https://cloud.google.com/blog/products/compute/introducing-a3-supercomputers-with-nvidia-h100-gpus)

---
# [fit] Sessions Sharing

---
# [fit] Build an **AIOps** platform 
# [fit] at enterprise scale 
# [fit] with Google Cloud

---
# Solve *Simple problem* -
# Need to triage an application outage

- Did somthing change recently ?
- What systems are involved ?
- which vendors need to be involved ?
- How to reduce finger-pointing and need for war rooms to solve the issue

---
^ AI ops defination

![](https://storage.googleapis.com/nino-public/presentations/google-next-23/ai_ops_difination.png)

---
# Identify the infrastructure **exhausts**
- Machine: The logging of performance statistics, storage, CPU, memory.
- Application: Applications logs
- Network / Traffic: Is traffic spiking from established norms?
- Security: Access logs, Change logs, firewall events.
- Synthetic: Are synthetic transactions responding as expcted ?

---
# Identify the infrastructure **exhausts** from outside.
- Human Sentiment: Customers express particular solution is down as a tweet on X.
- Incident Tickets: How do miscategorized tickets impack *Actual Business Impack*
- Weather / Seismic Alerts: Area infrastructure been impacked.

---
![](https://storage.googleapis.com/nino-public/presentations/google-next-23/AIOps-archi.png)

---
![](https://storage.googleapis.com/nino-public/presentations/google-next-23/ai_ops_active_assists.png)

---
# [fit] What's new in modern 
# [fit] **CI/CD** on Google Cloud

---

# [DORA.dev](http://dora.dev/)

---
# Challenges with tradissional ci/cd
- elasticity
- portability
- maintainence

---
- SLSA framework
- Transparency: SBOM
software bill of materials

---
# Managed dev environment
cloud workstations

---
Security assistance
- cloud codle source protect

---
Latest from Google
- Provance: Cloud build, SLSA

---
- GKE secureiety posture cloud run secirity insignts
- Cloud build new features
- Artifact Registry

---
# Cloud deploy
- canery deploy
- parallel deploy
- deploy parameters
    - work with parallel
    - eq, zone 1 deploy at 8am, zone 2 deploy at 8 pm
- deploy hook
- in console onboarding

---
# [fit] Running large-scale
# [fit] **machine learning (ML)** 
# [fit] on Google Kubernetes Engine (GKE)

---
# [fit] > %200 

^workload training inference
workload tunning traing on gke

---
Price optimization
- Serve lage models affordably
    - smaller container size using FasterTransformer
    - splitting a model across many smaller GPUs
    - Spot vs on-demand VMs

- Rapid pod startup 
    - 3x faster application startup with image streaming
    - smaller containers using FasterTransformer and NVIDIA Triton
    - using GCS FUSE for pod startup latency (data intensive)

- Improve GPU utilization
    - GPU time sharing up to 48 containers.
    - multi-insance GPU to partition an A100 or H100 into many instances
    - NVIDIA MPS(Multi-Process Service), lets application share a GPU concurrently

---
[QA] Is the container/multiprocess share gpu limited to specific node series? 

---
# [fit] **Prompt engineering**: 
# [fit] Getting the skill 
# [fit] your team needs next

---

# [fit] What's the most popular 
# [fit] programing language in 2023 ?

^English

---

# What kind of gent AI starts to see in 2023
- Use gen AI go through complex documents.
- Try to make data conversational, increase efficiency.
- Unstructured data, language, text, conversation.
- Audio/video other type of data.

---

# What's propt engineering and myth in it
- People think should talk like real comunication
but there's tricks you can use for talking to LLM.
- But with time, models gets less sensitive to which word you use.
- Try to provide detail information in question 
let model understand your question easier.
- Provide some example is a good idea for model to learn and response correct answer.

---

# How prompt engineering affect us ?
- Emerge of new tool always affect all people
- Get it sonner, get benefit sonner.
- It kill jobs but also create new ones.
- Everyone need to lear make use of gen AI

^ Example:
    - Meeting notes
    - Summarize email
    - Digest long document

---
# User should have good understanding on underlying model to be a better prompt engineer ?

- Communication skill is more important.
- Context of application is more important than model, you need to evaludate the context in the end.
- Models give "believeable" answer, not necessary "correct" answer.
- Understand how use use model answer is also important for evaluate model

^ Treat model as software, end-to-end test, evaluate result needs working on.
^ Since it's believeable answer, how you test to be confident to your answer.

---
# How can we better prepare our team for gen AI ?
- If your not starting expermenting / play aournd with gen AI, you're behind
- Don't be afraid, keep experimenting.

---
# [QA] Copyright ?
- Legal stuff still working on it.
- Still seek for balance knowledge sharing and keep secret inside.


---
# [QA] What advice you will give younger age people that help career path to become prompt engineering ?
- Follow your passion, focus on what you like
- Many degree like Linguistic, are not aware it will come to work with engineering.
- Improve your communication skill

---
# [QA] What kind of model will come out in future.
- video model.
- multi madility model, input and output.



---
# [fit] Best practices for 
# [fit] **DevOps velocity** and 
# [fit] **security** on Google Cloud

---

# Measuring sofwtwre delivery performance

- lead tim for changes
- development frequency
- change fail rate
- mean time to resotre servic

---

- Improve anything except for recover time (since roll back is easy in cloud)
- use canary deployment gke stragety
- Work on stability first and then speed.
- run unit test in cloud deploy, if test filed don’t merge prs.
- cloud deploy do port forward for you

---
# DevOps velocity - C-Aligment
- CHRO Principle
- CIO Principle
- CISO Principle

---

# Don’t targt releases/time to market

---

# [fit] What's new for 
# [fit] **real-time intelligence**

---

dataflow dynamic destination to down stream, save money

---
# How Uber use **Active Assist Insights**.
- Unattended Projects Recommender
- IAM Recommender
- Compute Engine Recommender
    - Monitor inactive and underutilized compute VM, Disks and Images.
    - Assigns ticketes to resource owners with metrics-based recomendations.

---
# [fit] AIOps tools Available in
# [fit] 2024

