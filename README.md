# 2024-28_Saanvi_Saxena_2410030492_5th_Semester_3CSE3

# AI Deployment & Automation Virtual Internship

**AICTE - EduSkills Virtual Internship Program** | Domain: AI Deployment & Automation

This repository contains my internship report, presentation, and completion credentials for the AI Deployment & Automation track of the AICTE - EduSkills Virtual Internship Program (July 2026 - August 2026), along with the project built during the internship: an **AI Resume Analyzer and Job Compatibility System**.

---

## 👤 Student Details

| Field | Details |
|---|---|
| Name | Saanvi Saxena |
| Roll Number | 2410030492 |
| Institute | IILM University, Greater Noida, U.P. |
| Programme | B.Tech CSE, Batch 2024-2028 |
| Internship Domain | AI Deployment & Automation |
| Duration | 8 Weeks (July 2026 - August 2026) |
| GitHub | @saanvi086 |

---

## 📌 About the Internship

The internship focused on the part of artificial intelligence work that begins *after* a model or a language-model application has been written: how it is served through an API, packaged into a container, connected to other systems through automation workflows, secured, and monitored once it is running.

It followed a structured, week-wise curriculum combining conceptual learning, guided labs and code demonstrations, weekly assessments and project submissions, and concluded with a Final Assessment Test and an Internship Grade Point Assessment.

**Organization:** EduSkills, a non-profit organisation that works with academic institutions and industry partners to run virtual internship programmes for engineering students in India, under the patronage of the AICTE National Internship Portal.

---

## 🎯 Objectives

- Understand the AI deployment lifecycle and what production readiness actually requires
- Serve models and AI applications through APIs built with FastAPI
- Package services and their dependencies using Docker, and understand CI/CD for ML workflows
- Deploy on managed cloud platforms and serve generative AI applications
- Build AI agents and orchestrate them into automation workflows
- Apply retrieval-augmented generation (RAG) with vector databases
- Secure AI systems and handle privacy, threats and bias
- Monitor deployed AI services through logging, observability and drift detection
- Apply all of the above to a complete end-to-end project

---

## 🗓️ Week-wise Curriculum

| Week | Module | Description |
|---|---|---|
| 1 | AI Deployment Foundations & FastAPI Model Serving | AI lifecycle, production readiness, MLOps terminology, environment setup, and API deployment with FastAPI including model integration and asynchronous operations |
| 2 | Containerization & CI/CD for MLOps | Docker architecture, Dockerfiles, networking, volumes, MLOps principles, and CI/CD pipelines for machine learning workflows |
| 3 | Cloud AI Deployment & Generative AI Serving | Deployment on AWS SageMaker, Google Vertex AI and Azure ML, deploying generative AI applications, LLM challenges, vLLM serving and model quantization |
| 4 | AI Agents & Automation Workflows | Building advanced AI agents with LangChain and LlamaIndex, agent orchestration with LangGraph, and AI-powered hyper-automation workflows |
| 5 | AI Integration, Security & Compliance | Integrating AI into web and mobile apps using Streamlit and Gradio, securing AI systems, handling threats, privacy and bias mitigation |
| 6 | Kubernetes & Observability in Production AI | Container orchestration with Kubernetes: Pods, Deployments and Services, plus monitoring and logging with Prometheus and Grafana |
| 7 | Performance Optimization, Drift & Advanced RAG | Performance tuning, cloud cost optimization, drift detection with Evidently AI, retraining strategies, advanced RAG architectures and vector database integration |
| 8 | Applied AI Projects & Capstone Projects | Real-world case studies, full-stack RAG application development, AI agents for business automation, and an end-to-end production AI solution |
| Final | Final Assessment Test | Internship Grade Point Assessment |

> Note: There was no stipend associated with this internship.

---

## 🚀 Project: AI Resume Analyzer and Job Compatibility System

The project built during this internship takes a resume, finds real job listings for it, and returns a clear picture of how well the candidate matches them.

**The problem.** A candidate looking for a job runs into a simple practical limit: there are far more openings than any one person can read. Checking every job description against your own resume, skill by skill, is something you can do for five jobs but not for five hundred. And when an application is rejected, nobody tells you which requirement you failed to meet, so you never learn which skill is actually holding you back.

**What the system does.** The user uploads a resume. The system reads it, scrapes real job listings from the web, works out what each listing requires, and reports which skills match, which are missing, and what is most useful to learn next. It is not restricted to technology roles: the candidate can be a software developer, a data analyst, a chartered accountant, a banker or any other professional, because the system works from whatever the resume states and whatever the listing asks for.

### How it works

| Stage | What happens |
|---|---|
| 1. Upload, extraction and storage | The user uploads a resume. The file type is validated, and the resume is converted into plain text and stored so it can be searched during matching. |
| 2. Resume analysis | The Resume Analysis Agent reads the text and produces a structured profile of the candidate: skills, tools, education, experience, projects and certifications. It records only what the resume actually states. |
| 3. Job retrieval and analysis | Job listings are scraped from the web, guided by the roles the candidate profile points to. The Job Analysis Agent reads each description and lists what it asks for, separating essential skills from preferred ones. |
| 4. Matching and scoring | The candidate profile and the job requirements are compared. A skills knowledge base is used to recognise related technologies. A compatibility score is calculated and matched, missing and related skills are listed. |
| 5. Output | The result is returned as a score, a match band, and a short set of recommendations on what to learn next. |

### Architecture

```
        Resume Upload
              |
   Text Extraction and Storage
              |
     Resume Analysis Agent
              |
      Job Analysis Agent          (scrapes job listings from the web)
              |
     Matching and Scoring
              |
     Compatibility Score
```

### How the score works

A skill that the resume states and the listing requires counts in full. A skill the candidate does not have but for which they have a closely related one, such as Flask against a requirement for FastAPI, counts as half. A requirement not met at all counts as nothing. Essential skills carry most of the weight, with smaller contributions from preferred skills, years of experience and education.

The result is a percentage: **75 and above** is a strong match, **50 to 74** a moderate match, and **below 50** a low match.

> The score describes how closely a resume lines up with what listings ask for. It is **not** a prediction of whether the candidate will be hired, which depends on interviews, competition and other factors the system cannot see.

---

## 🛠️ Technologies & Tools

| Tool | Why it is used |
|---|---|
| **n8n** | Workflow orchestration. The AI workflow is built in n8n: it takes the user's input, runs each stage in order, passes data between the agents and the backend, and returns the final result. |
| **Large Language Model (LLM)** | Reads and interprets text. Resumes and job descriptions are written in ordinary language, and a fixed keyword list cannot tell that "built a REST service in FastAPI" is evidence of a skill. |
| **FastAPI** | Powers the backend service that calculates the score. The score must come out the same every time for the same input, so it is worked out in code rather than by the model. |
| **Retrieval-Augmented Generation (RAG)** | A small knowledge base of skills and related technologies is searched during matching, so a candidate is credited for skills close to what a listing asks for. |
| **Docker** | Packages the backend service with everything it needs, so it runs identically anywhere and sits alongside the workflow as a container. |
| **Apify** | A web scraping platform used to collect job listings from the internet. It runs a scraper against whichever job site is needed and returns the listings with their full job descriptions. |

`Python` · `n8n` · `FastAPI` · `Docker` · `LLM Agents` · `RAG` · `Vector Search` · `REST APIs` · `Workflow Automation`

---

## 🏆 Certification & Credentials

| Field | Details |
|---|---|
| Certificate Title | Internship Credential, AI Deployment & Automation |
| Certificate ID | 2026-595A888026 |
| Date Issued | 27 August 2026 |
| AICTE Student ID | STU699828db808d31771579611 |
| Offer Letter Ref No. | C17Y2026M081524624 |
| Issued By | EduSkills, under the patronage of AICTE and the National Internship Portal |

Certificate authenticity can be verified via the QR code printed on the certificate itself (scan to verify), issued by EduSkills.

---

## 📁 Repository Contents

```
├── Internship_Report_Saanvi_Saxena.docx     # Full internship report (IILM format)
├── AI_Resume_Analyzer_Presentation.pptx     # Presentation deck
├── certificates/
│   ├── Certificate_of_Internship.png        # Internship completion certificate
│   ├── Internship_Offer_Letter.png          # Offer letter
│   └── Completion_Email_Proof.png           # Communication proof from EduSkills
└── README.md                                # This file
```

---

## 📄 Report Structure

1. Candidate's Declaration
2. Acknowledgement
3. Internship Completion Certificate
4. Project Description
   - 4.1 Introduction
   - 4.2 Organization Profile
   - 4.3 Problem Statement
   - 4.4 Project Objectives
   - 4.5 Scope of the Project
   - 4.6 Technologies and Tools Used
   - 4.7 System Architecture
   - 4.8 Methodology
   - 4.9 Expected Outcomes
   - 4.10 Certificates of Completion and Communication Proof
5. Bibliography / References

---

## 🔗 Reference Links

- EduSkills Foundation login and certificate portal: https://eduskillsfoundation.org/login
- AICTE National Internship Portal: https://internship.aicte-india.org/
- n8n Documentation: https://docs.n8n.io/
- FastAPI Documentation: https://fastapi.tiangolo.com/
- Docker Documentation: https://docs.docker.com/
- LangChain Documentation: https://python.langchain.com/
- Apify Documentation: https://docs.apify.com/
- Retrieval-Augmented Generation (Lewis et al., NeurIPS 2020): https://arxiv.org/abs/2005.11401

---

## 🙏 Acknowledgement

Thanks to the AICTE - EduSkills Virtual Internship Program team and EduSkills for the opportunity and the structured learning material, and to the School of Computer Science and Engineering, IILM University, Greater Noida, for their guidance and support throughout the programme.

---

**Saanvi Saxena** · B.Tech CSE · IILM University, Greater Noida
