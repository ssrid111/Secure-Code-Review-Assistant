🔐 Agentic Secure Code Review Assistant

An AI-powered autonomous secure code review system that monitors GitHub pull requests, detects vulnerabilities, analyzes code risks, enforces architectural standards, and automates intelligent merge decisions using multi-agent AI workflows.

🚀 Overview

Secure Code Review Assistant acts like an AI Security Engineer + Tech Lead for your repositories.
Instead of relying only on static analysis tools, this platform uses LLM-powered reasoning agents to understand:
* What changed
* Why it changed
* How risky the change is
* Whether it could break production or introduce vulnerabilities

The system continuously monitors pull requests, performs intelligent code reviews, explains risks in natural language, and can even automate security actions such as blocking merges or generating fixes.

✨ Features

🔍 Intelligent Pull Request Monitoring
* Watches GitHub/GitLab pull requests in real time
* Analyzes commits, diffs, and changed files
* Generates AI-powered review summaries

🛡️ Security Vulnerability Detection

Detects:
* SQL Injection
* Cross-Site Scripting (XSS)
* Hardcoded secrets
* Authentication flaws
* Dependency vulnerabilities
* Misconfigured APIs
* Insecure file handling
* JWT/OAuth mistakes

🤖 Multi-Agent AI Architecture

The platform uses specialized AI agents:
Agent	Responsibility
Security Agent	Vulnerability analysis
Logic Agent	Bug & edge-case detection
Architecture Agent	Design & structure validation
DevOps Agent	CI/CD, Docker, Kubernetes checks
Compliance Agent	GDPR/HIPAA/license checks


📊 Pull Request Risk Scoring

Every PR receives a dynamic risk score:

Risk Score: 8.7/10
Reasons:
- Authentication middleware modified
- Unsafe SQL query detected
- Critical dependency updated

💡 AI-Powered Explanations

Instead of vague warnings, the assistant explains issues clearly:
The password reset token validation no longer checks expiration timestamps,
which may allow replay attacks.
Suggested Fix:
Validate token expiration before issuing session tokens.

🔧 Automated Patch Suggestions

Example:
- const query = "SELECT * FROM users WHERE id=" + userId
+ const query = "SELECT * FROM users WHERE id=?"

⚡ Autonomous Actions

The assistant can:
* Block risky merges
* Request additional reviewers
* Trigger Slack/Teams alerts
* Create Jira incidents
* Generate security reports
* Auto-create remediation pull requests

🧠 Context-Aware Repository Learning

The system learns:
* Repository coding standards
* Existing architecture patterns
* Team review history
* Security conventions

🏗️ System Architecture

GitHub Webhook
       ↓
Webhook Listener (FastAPI)
       ↓
Event Queue (Redis/Kafka)
       ↓
AI Orchestration Engine
       ↓
┌──────────────────────────┐
│ Multi-Agent Review Layer │
└──────────────────────────┘
 ↓       ↓       ↓
Security Logic Architecture
 Agent    Agent     Agent
       ↓
Decision Engine
       ↓
GitHub PR Comments / Alerts
       ↓
Approve • Reject • Escalate

🛠️ Tech Stack

Backend
* Python
* FastAPI
* Celery
* Redis / Kafka

AI & Agents
* OpenAI API
* LangChain / LangGraph
* CrewAI
* Ollama (Local LLMs)

Static Analysis
* Semgrep
* CodeQL
* Bandit
* ESLint
* SonarQube

Integrations
* GitHub API
* GitHub Webhooks
* GitLab API
* Slack API
* Jira API


📂 Project Structure
secure-code-review-assistant/
│
├── agents/
│   ├── security_agent.py
│   ├── logic_agent.py
│   ├── architecture_agent.py
│   └── compliance_agent.py
│
├── api/
│   ├── github_webhook.py
│   └── routes.py
│
├── scanners/
│   ├── semgrep_runner.py
│   ├── codeql_runner.py
│   └── dependency_scanner.py
│
├── orchestration/
│   ├── agent_manager.py
│   └── decision_engine.py
│
├── integrations/
│   ├── github_client.py
│   ├── slack_notifier.py
│   └── jira_client.py
│
├── database/
│
├── tests/
│
├── requirements.txt
└── README.md

⚙️ Installation

Clone Repository

git clone https://github.com/yourusername/secure-code-review-assistant.git
cd secure-code-review-assistant

Create Virtual Environment
python -m venv venv
Windows
venv\Scripts\activate
macOS/Linux
source venv/bin/activate

Install Dependencies

pip install -r requirements.txt


🔑 Environment Variables

Create a .env file:

OPENAI_API_KEY=your_api_key
GITHUB_TOKEN=your_github_token
SLACK_WEBHOOK=your_slack_webhook
JIRA_API_KEY=your_jira_key

▶️ Running the Project

uvicorn api.github_webhook:app --reload

🔗 GitHub Webhook Setup

1. Open your GitHub repository
2. Navigate to:
    * Settings → Webhooks
3. Add webhook URL:

http://your-server-url/webhook

4. Select events:
* Pull Requests
* Push Events
* Issue Comments

📸 Example Workflow

PR Created

Developer opens PR
       ↓
Webhook triggered
       ↓
AI agents analyze changes
       ↓
Risk score generated
       ↓
Security vulnerabilities detected
       ↓
AI comments on PR
       ↓
Merge blocked if critical

🧪 Example AI Review Comment

⚠️ Security Alert
Potential SQL Injection detected in:
src/user/auth.js
Reason:
User input is directly concatenated into SQL query strings.
Recommendation:
Use parameterized queries or ORM methods.

📈 Future Enhancements

* AI-powered threat modeling
* Behavioral sandbox execution
* Repository knowledge graph
* Merge failure prediction
* Self-healing remediation PRs
* Kubernetes runtime security monitoring
* Multi-repository intelligence sharing

🌟 Why This Project Matters

Traditional static analyzers generate noisy alerts and lack contextual understanding.

This project introduces:

* Autonomous reasoning
* Context-aware security analysis
* Multi-agent collaboration
* Intelligent developer workflows

It represents the next generation of AI-driven DevSecOps systems.

🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create your feature branch

git checkout -b feature/new-feature

3. Commit changes

git commit -m "Added new feature"

4. Push to branch

git push origin feature/new-feature

5. Open a Pull Request


👩‍💻 Author

Swetha Sridharan
M.S. Software Engineering — Arizona State University

GitHub:  ssrid111￼
LinkedIn:  Swetha Sridharan￼

Based on experience in AI systems, security-focused applications, full-stack engineering, and intelligent automation.  ￼

Ashuwanthh Ravichandran
M.Sc. Cyber Security - PSG College Of Technology

GitHub: Ashu-1505
LinkedIn: Ashuwanthh Ravichandran

Based on experience in security automation, full-stack engineering and threat hunting.
