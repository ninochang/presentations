footer: nino.chang@**swag**.live
slidenumbers: true
build-lists: true

![fit](https://storage.googleapis.com/gweb-cloudblog-publish/images/GCN23_GE_BlogHeader_2436x1200_10.max-2500x2500.png)
# [fit] Google Next 23'

---
[.build-lists: false]

# Outline
- *Duet AI* integration to GCP products
- *VertexAI* updates
- *Infrustructures* updates
- Sessions sharing
    1. Build an *AIOps* platform at enterprise scale with Google Cloud
    2. Best practices for *DevOps velocity* and *security* on Google Cloud
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

[^1]: [vscode integration document](https://cloud.google.com/code/docs/vscode/install)

[^2]: [chat with Duet AI document](https://cloud.google.com/code/docs/vscode/write-code-duet-ai)

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
- -- Find Nino's salary
- -- Find Nino's salary from `playground.employees`
- -- Find all employee from `playground.employees` who's salary higher than 10
- -- Use query above filter out member come from department_id 4

---
# Assisted no code development
- with App sheet[^3]
- Build app conversationally

[^3]: [app sheet](https://www.appsheet.com/home/apps)

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

# [fit] **Infrustructures** updates

---
# Infra
- A3 VMs + Nvidia H100 GPU [^4]
    - Deploy A3 on VertexAI or GKE
    - 10x more network bandwidth compared to our A2 VM (GPU-to-GPU data transfer)
- Cloud TPU v5e
- GKE enterprise [^5]

[^4]: [A3](https://cloud.google.com/blog/products/compute/introducing-a3-supercomputers-with-nvidia-h100-gpus)

[^5]: [GKE version Comparison](https://cloud.google.com/kubernetes-engine/docs/concepts/gke-editions#edition_features)

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
- How to reduce finger-pointing and need for war rooms to solve the issue

---
The application of AI capabilities, 
such as natural language processing 
and machine learning models, 
to *automate* and streamline operational workflows.

![left fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/ai_ops_difination.png)

---
# Data from inside
- Machine: The logging of performance statistics, storage, CPU, memory.
- Application: Applications logs
- Network / Traffic: Is traffic spiking from established norms?
- Security: Access logs, Change logs, firewall events.
- Synthetic: Are synthetic transactions responding as expcted ?

---
# Data from outside
- Human Sentiment: Customers express particular service is down as a tweet on twitter.
- Incident Tickets: How do miscategorized tickets impack *Actual Business Impack*
- Weather / Seismic Alerts: Area infrastructure been impacked.

---
![](https://storage.googleapis.com/nino-public/presentations/google-next-23/AIOps-archi.png)

---
![](https://storage.googleapis.com/nino-public/presentations/google-next-23/ai_ops_active_assists.png)

---
Uber's 3 use case of **Active Assist**[^6]

[^6]: [Active assist](https://console.cloud.google.com/home/recommendations?hl=zh-tw&project=swag-nino-chang)

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/unattended-projects-recommender-1.png)

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/iam-recommender-1.png)

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/compute-engine-recommender.png)

---
GitOps tools come in 2024.

---
# [fit] Best practices for 
# [fit] **DevOps velocity** and 
# [fit] **security** on Google Cloud

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/dora-matrix.png)

---
- Improve anything except for recover time (since roll back is easy in cloud)
- Use canary deployment gke stragety
- Work on stability first and then speed.
- Run unit test in cloud deploy, if test filed don’t merge prs.
- Cloud deploy do port forward for you

---

# Demo cloud build increase
- velocity
- security

---
# **Gitlab** x Google Cloud [^7]
![fit original](https://about.gitlab.com/images/blogimages/gitlabgooglecloud.png)

[^7]: [Google partner with GitLab](https://about.gitlab.com/blog/2023/08/29/gitlab-google-partnership-s3c/)

---
# [fit] Running large-scale
# [fit] **machine learning (ML)** 
# [fit] on Google Kubernetes Engine (GKE)

---
# [fit] > %200 

^workload training inference
workload tunning traing on gke

---
![](https://storage.googleapis.com/nino-public/presentations/google-next-23/Large-scall-gpu.png)

---
# Training
- TPU v4 and v5e (preview) available in GKE
- A3 available on GKE
- Use kueue manage jobs with in pods for different teams

---
# Serve large models affordably
- smaller container size using FasterTransformer
- splitting a model across many smaller GPUs
- Spot vs on-demand VMs

---
# Rapid pod startup saves money
- 3x faster application startup with *image streaming*
- Smaller containers using FasterTransformer and NVIDIA Triton
- Using GCS FUSE for pod startup latency (data intensive)

---
# Improve GPU utilization
- GPU time sharing up to 48 containers [^8]
- Partition large GPU to many instance, reduce serving latency.
- Nvdia MPS, let application share GPU concurrently.

[^8]: [Time sharing GPU](https://cloud.google.com/kubernetes-engine/docs/concepts/timesharing-gpus)

---
# [fit] **Prompt engineering**: 
# [fit] Getting the skill 
# [fit] your team needs next

---
# [fit] What's the most popular 
# [fit] programing language in 2023 ?

---
# [fit] **English**

---

# What kind of gen AI starts to see in 2023
- Use gen AI go through complex documents.
- Try to make data conversational, increase efficiency.
- Unstructured data, language, text, conversation.
- Audio/video other type of data.

---
[.build-lists: false]

key of prompt engineering is to provide as much content as you can

# What's propt engineering and myth in it
- People think should talk like real comunication
but there's tricks you can use for talking to LLM.
- But with time, models gets less sensitive to which word you use.
- Try to provide detail information in question 
let model understand your question easier.
- Provide some example is a good idea for model to learn and response correct answer.

---
[.build-lists: false]

# How prompt engineering affect knowledge worker ?
- Emerge of new tool always affect all people
- Marketer used to use only news papaer, now social media.
- Get it sonner, get benefit sonner.
- It kill jobs but also create new ones.
- Everyone need to learn make use of gen AI

^ Example:
    - Meeting notes
    - Summarize email
    - Digest long document

---
[.build-lists: false]
# User should have good understanding on underlying model to be a better prompt engineer ?

- Need leading how to programming in english. 
- Communication skill is more important.
- Context of application is more important than model, you need to evaludate the context in the end.
- How do we test "programming in english" if we treat it as software.
- Models give "believeable" answer, not necessary "correct" answer.
- Get feetback from user create feedback loop.
- Custom model will starts from some base model not from scratch.

^ Treat model as software, end-to-end test, evaluate result needs working on.
Since it's believeable answer, how you test to be confident to your answer.

---
[.build-lists: false]
# How can we better prepare our team for gen AI ?
- If your not starting expermenting / play aournd with gen AI, you're behind
- Don't be afraid, keep experimenting.

---
[.build-lists: false]

# [QA] Copyright ?
- Legal community still working on it.
- Still seek for balance knowledge sharing and keep secret inside.

---
[.build-lists: false]

# [QA] What advice you will give younger age people that help career path to become prompt engineering ?
- Follow your passion, focus on what you like
- Many degree like Linguistic, are not aware it will come to work with engineering.
- Improve your communication skill

---
[.build-lists: false]

# [QA] What modilities are primed for the next big fundational model ?
- video model.
- multi madility model, input and output.

<!-- ---
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

--- -->
