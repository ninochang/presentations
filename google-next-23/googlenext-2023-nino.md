footer: nino.chang@**swag**.live
slidenumbers: true
build-lists: true

![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/firstpage.png)

---

![fit](https://storage.googleapis.com/gweb-cloudblog-publish/images/GCN23_GE_BlogHeader_2436x1200_10.max-2500x2500.png)
# [fit] Google Next 23'

---
[.build-lists: false]
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

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
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Features
- Assisted development
- Assited operations
- Assisted data
- Assisted no code development
- Assisted security

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)
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
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

Demo VScode

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

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
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Assisted Data
- SQL Completion
- SQL Generation
- SQL Generation-Iteration
- SQL Explainability

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

Demo bigquery suggestion.
- -- Find Nino's salary
- -- Find Nino's salary from `playground.employees`
- -- Find all employee from `playground.employees` who's salary higher than 10
- -- Use query above filter out member come from department_id 4

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Assisted no code development
- with App sheet[^3]
- Build app conversationally

[^3]: [app sheet](https://www.appsheet.com/home/apps)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Assisted security
Duet AI integrated with
- Madiant
- Chronicle

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# [fit] **VertexAI**

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Vision - Generation
- Digital watermarking
- image styling traing and apply

---
![inline](https://storage.googleapis.com/nino-public/presentations/google-next-23/vision-generate-truck.png)![inline](https://storage.googleapis.com/nino-public/presentations/google-next-23/vision-generate-golden-style-training.png)
![inline](https://storage.googleapis.com/nino-public/presentations/google-next-23/vision-generate-golden-style-apply.png)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# LLMs
- variaties of model ready to use as fundamantal.
    - Llama2 (2023/7)
    - Code Llama (2023/8)
    - Palm (2023/3)
    - up to 47 basic models.

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# [fit] **Infrustructures** updates

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Infra
- A3 VMs + Nvidia H100 GPU [^4]
    - Deploy A3 on VertexAI or GKE
    - 10x more network bandwidth compared to our A2 VM (GPU-to-GPU data transfer)
- Cloud TPU v5e
- GKE enterprise [^5]

[^4]: [A3](https://cloud.google.com/blog/products/compute/introducing-a3-supercomputers-with-nvidia-h100-gpus)

[^5]: [GKE version Comparison](https://cloud.google.com/kubernetes-engine/docs/concepts/gke-editions#edition_features)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# [fit] Sessions Sharing

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

## Build an **AIOps** platform at enterprise scale with Google Cloud

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Solve *Simple problem* -
# Need to triage an application outage

- Did somthing change recently ?
- What systems are involved ?
- How to reduce finger-pointing and need for war rooms to solve the issue

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

The application of AI capabilities, 
such as natural language processing 
and machine learning models, 
to *automate* and streamline operational workflows.

![left fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/ai_ops_difination.png)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Data from inside
- Machine: The logging of performance statistics, storage, CPU, memory.
- Application: Applications logs
- Network / Traffic: Is traffic spiking from established norms?
- Security: Access logs, Change logs, firewall events.
- Synthetic: Are synthetic transactions responding as expcted ?

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Data from outside
- Human Sentiment: Customers express particular service is down as a tweet on twitter.
- Incident Tickets: How do miscategorized tickets impack *Actual Business Impack*
- Weather / Seismic Alerts: Area infrastructure been impacked.

---
![](https://storage.googleapis.com/nino-public/presentations/google-next-23/AIOps-archi.png)

---
![](https://storage.googleapis.com/nino-public/presentations/google-next-23/ai_ops_active_assists.png)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

Uber's 3 use case of **Active Assist**[^6]

[^6]: [Active assist](https://console.cloud.google.com/home/recommendations?hl=zh-tw&project=swag-nino-chang)

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/unattended-projects-recommender-1.png)

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/iam-recommender-1.png)

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/compute-engine-recommender.png)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

GitOps tools come in 2024.

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

## Best practices for **DevOps velocity** and **security** on Google Cloud

---
![fit](https://storage.googleapis.com/nino-public/presentations/google-next-23/dora-matrix.png)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

- Improve anything except for recover time (since roll back is easy in cloud)
- Use canary deployment gke stragety
- Work on stability first and then speed.
- Run unit test in cloud deploy, if test filed don’t merge prs.
- Cloud deploy do port forward for you

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Demo cloud build increase
- velocity
- security

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

Cloud build trigger build and test on pull request

```yaml
steps:
  # Build and tag using commit sha
  - name: 'gcr.io/cloud-builders/docker'
    args: ['build', '.', '-t', 'asia-east1-docker.pkg.dev/$PROJECT_ID/pop-stats/pop-stats:${COMMIT_SHA}', '-f', 'Dockerfile']
    dir: 'app'
  # Run api tests
  - name: 'asia-east1-docker.pkg.dev/$PROJECT_ID/pop-stats/pop-stats:${COMMIT_SHA}'
    entrypoint: python
    args: ["api_tests.py"]
    dir: 'app'

```

---
[.code-highlight: 8-10]

![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

Cloud build trigger when main been merged

```yaml
apiVersion: deploy.cloud.google.com/v1
kind: DeliveryPipeline
metadata:
  name: pop-stats-pipeline
description: pop-stats application delivery pipeline
serialPipeline:
 stages:
 - targetId: staging
   profiles:
   - staging
 - targetId: prod
   profiles:
   - prod
   strategy:
    canary:
      runtimeConfig:
        kubernetes:
          serviceNetworking:
            service: "pop-stats"
            deployment: "pop-stats"
      canaryDeployment:
        percentages: [5]
        verify: true
```

---
[.code-highlight: 11-23]
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

Cloud build trigger when main been merged

```yaml
apiVersion: deploy.cloud.google.com/v1
kind: DeliveryPipeline
metadata:
  name: pop-stats-pipeline
description: pop-stats application delivery pipeline
serialPipeline:
 stages:
 - targetId: staging
   profiles:
   - staging
 - targetId: prod
   profiles:
   - prod
   strategy:
    canary:
      runtimeConfig:
        kubernetes:
          serviceNetworking:
            service: "pop-stats"
            deployment: "pop-stats"
      canaryDeployment:
        percentages: [5]
        verify: true
```

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

Target `staging`

```yaml
apiVersion: deploy.cloud.google.com/v1
kind: Target
metadata:
  name: staging
description: staging cluster
gke:
  cluster: projects/swag-nino-chang/locations/us-central1/clusters/stagingcluster
```

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

Target `prod`

```yaml
apiVersion: deploy.cloud.google.com/v1
kind: Target
metadata:
  name: prod
description: prod multi-target
requireApproval: true
multiTarget:
  targetIds: [prod1, prod2, prod3]
```

---
[.code-highlight: 6-8]
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

Target `prod`

```yaml
apiVersion: deploy.cloud.google.com/v1
kind: Target
metadata:
  name: prod
description: prod multi-target
requireApproval: true
multiTarget:
  targetIds: [prod1, prod2, prod3]
```

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# **Gitlab** x Google Cloud [^7]
![fit original](https://about.gitlab.com/images/blogimages/gitlabgooglecloud.png)

[^7]: [Google partner with GitLab](https://about.gitlab.com/blog/2023/08/29/gitlab-google-partnership-s3c/)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

## Running large-scale **machine learning (ML)** on Google Kubernetes Engine (GKE)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# [fit] > %200 

^workload training inference
workload tunning traing on gke

---
![](https://storage.googleapis.com/nino-public/presentations/google-next-23/Large-scall-gpu.png)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Training
- TPU v4 and v5e (preview) available in GKE
- A3 available on GKE
- Use kueue manage jobs with in pods for different teams

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Serve large models affordably
- smaller container size using FasterTransformer
- splitting a model across many smaller GPUs
- Spot vs on-demand VMs

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Rapid pod startup saves money
- 3x faster application startup with *image streaming*
- Smaller containers using FasterTransformer and NVIDIA Triton
- Using GCS FUSE for pod startup latency (data intensive)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# Improve GPU utilization
- GPU time sharing up to 48 containers [^8]
- Partition large GPU to many instance, reduce serving latency.
- Nvdia MPS, let application share GPU concurrently.

[^8]: [Time sharing GPU](https://cloud.google.com/kubernetes-engine/docs/concepts/timesharing-gpus)

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

## **Prompt engineering**: Getting the skill your team needs next

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

## What's the most popular programing language in 2023 ?

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# [fit] **English**

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# What kind of gen AI starts to see in 2023
- Use gen AI go through complex documents.
- Try to make data conversational, increase efficiency.
- Unstructured data, language, text, conversation.
- Audio/video other type of data.

---
[.build-lists: false]
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)


# What's propt engineering and myth in it
- People think should talk like real comunication
but there's tricks you can use for talking to LLM.
- But with time, models gets less sensitive to which word you use.
- Try to provide detail information in question 
let model understand your question easier.
- Provide some example is a good idea for model to learn and response correct answer.

---
[.build-lists: false]
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

## How prompt engineering affect knowledge worker ?
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
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

## User should have good understanding on underlying model to be a better prompt engineer ?

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
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

## How can we better prepare our team for gen AI ?
- If your not starting expermenting / play aournd with gen AI, you're behind
- Don't be afraid, keep experimenting.

---
[.build-lists: false]
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)


QA: Copyright ?
- Legal community still working on it.
- Still seek for balance knowledge sharing and keep secret inside.

---
[.build-lists: false]
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)


QA: What advice you will give younger age people that help career path to become prompt engineering ?
- Follow your passion, focus on what you like
- Many degree like Linguistic, are not aware it will come to work with engineering.
- Improve your communication skill

---
[.build-lists: false]
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)


QA: What modilities are primed for the next big fundational model ?

- video model.
- multi madility model, input and output.

---
![original](https://storage.googleapis.com/nino-public/presentations/google-next-23/background.png)

# [fit] Questions ?

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
