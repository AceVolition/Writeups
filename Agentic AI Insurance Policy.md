## 1. Info

This is my first vibe coded AI Agent, I started this inintialy in response to one of my classmate that has vibe coded an OSINT tool that use AI along with python to scrap though to get a summarized detail profiled person of the person on reddit. So in response I took the time to research and learn how to vibe code and wanted to learn how AI agents work and in how I can build it. I made a list of ideas and got down on deciding to make an AI Agent for Insurance Policy. My reason for choosing it was I think AI for boring industries are ripe for disruption. Around May I started building this AI Agent for Insurance Policy and it took me around 1 week of researching and idea listing and 2 weeks of building the AI Agent, from doing this it help put me ahead on those who don't know how to vibe code and on building AI Agents. I also believe that like how building websites were the thing of the early 1990s and 2000s is what is to building AI Agents in 2026.

## 2. Goals & Requirements
Goals:

o Saves you time on understanding insurance policy and checks and notify you of regulation that change your policy.

o Saves you time on Appealing claims that been denied and filing a claim.

o Saves you time on comparing policy to get better price.

## 3. The Tools

The following is what I used and how I used them to help make my AI Agent.

o Chatgpt (PRD & System Design) & Codex 5.5 (High Reasoning)

o VSCode (Editor)

o LangGraph (AI Agent Framework)

o Vercel (Frontend hosting)

o Supabase (Postgres SQL Database hosting)

o Render (Backend hosting)
   
I started by drafting up and making the PRD in Chatgpt after I finalized it I moved it to making the System Design based off the PRD. After finishing those two I then hand off the PRD and System Design DOCs to Codex which will tkae in the PRD and System Design and asked it to build it based off the PRD and System Design Docs. Now I am not a computer science major and I am coming up and learning there is Production and Local. In that you would test your application localy before pushing it into production. Vercel (Frontend), Supabase (Database), Render (Backend) are what I am using to host my applications on. I am aware that the standard for hosting your applications is AWS but For small projects, MVPs, or teams with limited DevOps experience the trio is far faster and easier. AWS becomes necessary when you outgrow the simplicity, need lower long-term cost at scale, require compliance/control, or want to consolidate infrastructure under one provider.

## 4. The Blueprint

This is the PRD template that was generated from Chatgpt I then filled this out and hand it back to chatgpt to make the system design before handing over the PRD and System Design to Codex to build the MVP.

    1.Product Overview  

       a.What the product is  

       b.The problem it solves  

       c.Who it is for  

    2.Goals and Success Metrics  

       a.Desired outcomes  

       b.KPIs or measurable targets  

    3.Target Users  

       a.Personas and user needs  

    4.Core Features  

       a.Functional requirements  

       b.Priority levels (Must Have, Should Have, Nice to Have)  

    5.User Stories  

       a.Example: “As a user, I want to save my progress so that I can continue later.”  

    6.Technical Requirements  

       a.Platforms (web, mobile, desktop)  

       b.Integrations and APIs  

       c.Performance and security expectations  

    7.UX Requirements  

       a.Navigation and workflows  

       b.Design references  

    8.Constraints and Assumptions  

       a.Budget, timeline, technology choices  

    9.Milestones  

       a.MVP scope  

       b.Future phases  

    10.Open Questions  

       a.Areas needing further decisions 
d

From t


   Agentic AI Insurance Policy Analyzer - System Design Document (SDD) 

   Version 1.0 

   Default LLM Provider: DeepSeek (Pluggable Architecture) 

   1.System Overview 

   The system is an AI-powered SaaS platform that allows users to upload insurance policy PDFs and receive: 
   • Plain-English summaries 
   • Exclusion and risk detection 
   • Claim denial explanations 
   • Appeal recommendations 
   • Policy comparisons 
 
   The platform combines PDF parsing, OCR, agent orchestration, pluggable LLM providers, secure cloud storage, and web/mobile frontends. 

   2. Core Architectural Principle: Pluggable LLM Provider Layer 

   The application will use an abstraction layer so any large language model can be swapped without changing business logic. 
 
   Default MVP Model: 
   • DeepSeek (to minimize costs) 
 
   Supported Providers: 
   • DeepSeek 
   • Claude 
   • OpenAI 
   • Gemini 
 
   Recommended Strategy: 
   • Start with DeepSeek for the MVP 
   • Switch to Claude for more complex legal reasoning if needed 
   • Use multiple providers in production based on task complexity 

   3. High-Level Architecture 
   
   Web/Mobile UI (Next.js/React) 
           ↓ HTTPS 
   API Gateway (FastAPI) 
           ↓ 
   Authentication (Supabase Auth) 
           ↓ 
   Document Storage (Supabase Storage) 
           ↓ 
   Agent Orchestrator (LangGraph) 
           ↓ 
   PDF Parser Agent 
   Policy Summary Agent 
   Exclusion Detection Agent 
   Risk Detection Agent 
   Claim Denial Agent 
   Appeal Recommendation Agent 
   Policy Comparison Agent 
           ↓ 
   LLM Provider Layer (DeepSeek default; Claude/OpenAI/Gemini interchangeable) 
           ↓ 
   PostgreSQL Database 

   4.Technology Stack 

Frontend: 
• Next.js 
• React 
• Tailwind CSS 
• shadcn/ui 
 
Backend: 
• Python 
• FastAPI 
 
AI Orchestration: 
• LangGraph 
 
LLM Providers: 
• DeepSeek (default) 
• Claude 
• OpenAI 
• Gemini 
 
Database and Storage: 
• Supabase (PostgreSQL + Storage) 
 
Deployment: 
• Vercel (frontend) 
• Railway or Render (backend) 

5. Core Components 

Frontend Application: 
• Authentication 
• PDF upload 
• Dashboard 
• Chat interface 
 
API Backend: 
• REST API endpoints 
• Job orchestration 
• Security 
 
Agent Orchestrator: 
• Coordinates specialized agents 
 
LLM Provider Layer: 
• Standard interface for all model providers 
 
Database: 
• Users, policies, analyses, chats 
 
Storage: 
• Secure PDF storage 

6. Agent Architecture 

Policy Analysis Supervisor 
• PDF Parsing Agent 
• Policy Summary Agent 
• Exclusion Detection Agent 
• Risk Detection Agent 
• Claim Denial Explanation Agent 
• Appeal Recommendation Agent 
• Policy Comparison Agent 

7. Data Flow 

1. User uploads a PDF. 
2. File is stored securely. 
3. Text is extracted using OCR/PDF parsing. 
4. LangGraph starts the workflow. 
5. Specialized agents analyze the document. 
6. Agents call the configured LLM provider. 
7. Results are stored in PostgreSQL. 
8. Dashboard displays findings. 
9. User asks follow-up questions via chat. 

8. LLM Provider Interface 

Example Python Interface: 
 
class LLMProvider: 
    def analyze(self, prompt: str) -> str: 
        pass 
 
Implementations: 
• DeepSeekProvider 
• ClaudeProvider 
• OpenAIProvider 
• GeminiProvider 
 
The active provider is selected through environment variables or configuration. 

9. Database Schema 

users 
• id 
• email 
• created_at 
 
policies 
• id 
• user_id 
• file_url 
• insurance_type 
• uploaded_at 
 
analyses 
• id 
• policy_id 
• summary 
• exclusions 
• risks 
• denial_explanations 
• created_at 
 
chats 
• id 
• user_id 
• policy_id 
• message 
• response 
• created_at 

10. API Endpoints 

Authentication: 
• POST /auth/signup 
• POST /auth/login 
 
Policies: 
• POST /policies/upload 
• GET /policies/{id} 
 
Analysis: 
• POST /analysis/run/{policy_id} 
• GET /analysis/{policy_id} 
 
Chat: 
• POST /chat/{policy_id} 

11. Security Design 

• HTTPS/TLS encryption 
• Encryption at rest 
• Role-based access control 
• Audit logging 
• Signed URLs for document access 

12. Deployment Architecture 

Frontend: 
• Vercel 
 
Backend: 
• Railway or Render 
 
Database and Storage: 
• Supabase 
 
CI/CD: 
• GitHub Actions 

13. MVP Build Order 

1. Authentication 
2. PDF upload 
3. PDF parsing and OCR 
4. LLM provider abstraction 
5. DeepSeek integration 
6. Policy summary 
7. Risk and exclusion detection 
8. Dashboard 
9. Chat interface 
10. Claim denial analysis 




   
## 5. Tech Stack
### Frontend

#### Next.js App Router; React ; TypeScript ; Tailwind CSS ; shadcn/ui-style components ; Lucide React icons ; Supabase JS client for browser auth


### Backend

#### Python ; FastAPI ; Uvicorn ; Pydantic / Pydantic Settings ; HTTPX for Supabase and LLM API calls ; AI / Agents ; LangGraph for orchestration

### Supervisor agent workflow

#### Specialized agents: PDF Parsing Agent ; Policy Summary Agent ; Exclusion Detection Agent ; Risk Detection Agent ; Claim Denial Explanation Agent ; Appeal Recommendation Agent ; Policy Comparison Agent ; LLM Layer


### Pluggable AI API provider interface
#### DeepSeek as the default provider Stub providers for: Claude, OpenAI, Gemini

### PDF
#### pdfplumber for PDF text extraction, pytesseract OCR fallback, Pillow for image handling

### Database / Storage / Auth
#### Supabase Auth, Supabase PostgreSQL, Supabase Storage for private PDF uploads, Supabase signed URLs, Row Level Security Policies, Deployment Targets

### Hosting in PROD
#### Vercel for frontend, Render for backend, Supabase for auth, database, and storage



## 6. The Journey

It all started with me learning java (I really do not like that language it ugly to read and it hurts my eyes, I like python better) Java was where I learned the foundational stuff and then I moved to python in which I found it much easier to work with and learn and this was when Chatgpt came around and this is when
I started using chatgpt to build simple functions but I never thought one day AI could soon build an MVP as I thought it was only good at just building functions or correcting your code but then again this was around Chatgpt 3. Now we are in the phase that the AI can build a fully working MVP and I didnt think it would have gotten this far and so this was my experiment on vibe coding this MVP for the first time but this was after hours of research.

## 7. The Payoff

Stop guessing what your insurance policy actually covers and start getting AI‑powered, structured answers in minutes.

With this MVP, you can:

    Upload a policy PDF → get a plain‑English summary of what’s covered, what’s not, and where the risks hide.

    Uncover exclusions, gotchas, and potential claim denials before you file.

    Receive appeal recommendations and claim denial explanations tailored to your policy language.

    Compare policies side‑by‑side to spot differences that actually matter.

    Chat with the policy itself to ask follow‑up questions (like “does this cover water damage from a burst pipe?”).

Behind the scenes, a LangGraph supervisor orchestrates seven specialized agents, turning hours of dense legal/insurance reading into a few clicks. The result is faster, more transparent policy understanding for consumers, advocates, and small businesses.

    Important: This is an educational MVP and not for legal or financial advice. Always verify AI output against your original policy and consult a qualified professional before making coverage or claim decisions.

## 8. Conclusion

I learned alot from working on this project my favorite part is being able to build and itlerate faster than you could previously do. What took months to build a MVP now take weeks or even couple of days to build an MVP, but of course it depends on how complex it is. Insurance is a boring industry, most people are not really trying to disrupt the boring industry because it not exciting to most people especially tech people. Most are going for tech and mabby finaical adjacent but mostly in the HFT or stocks on trying to build  AI Agents for that sector. After this project I plan to make an idea list again and build somthing either AI Agents for boring Industries or somthing that may be useful to people in anyhow.

