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

    Get notified when a goverment regulation forces change to your policy.

    Compare policies side‑by‑side to spot differences that actually matter and for better price.

    Chat with the policy itself to ask follow‑up questions (like “does this cover water damage from a burst pipe?”).

Behind the scenes, a LangGraph supervisor orchestrates seven specialized agents, turning hours of dense legal/insurance reading into a few clicks. The result is faster, more transparent policy understanding for consumers, advocates, and small businesses.

    Important: This is an educational MVP and not for legal or financial advice. Always verify AI output against your original policy and consult a qualified professional before making coverage or claim decisions.

## 8. Conclusion

I learned alot from working on this project my favorite part is being able to build and itlerate faster than you could previously do. What took months to build a MVP now take weeks or even couple of days to build an MVP, but of course it depends on how complex it is. Insurance is a boring industry, most people are not really trying to disrupt the boring industry because it not exciting to most people. Most are going for tech and mabby finaical adjacent but mostly in the HFT or stocks on trying to build  AI Agents for that sector. After this project I plan to make an idea list again and build somthing either AI Agents for boring Industries or somthing that may be useful to people in anyhow.

