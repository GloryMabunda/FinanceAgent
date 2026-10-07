# Finance AI Agent 💰🤖

> **An AI financial accountability agent that continuously analyses actual spending against a user's budget and financial goals, detects financial drift, and provides actionable guidance.**

The **Finance AI Agent** is an AI-powered personal finance management and guidance platform built with **C#, ASP.NET Core, SQL Server, and AI agent technologies**.

Unlike traditional budgeting applications that primarily display historical financial information, this project focuses on **understanding what is happening financially and helping the user decide what to do next**.

The system combines deterministic financial calculations with AI reasoning to provide grounded, explainable financial guidance.

---

## 🎯 Product Vision

Traditional budgeting software might tell you:

```text
Groceries

Budget:  R3,000
Actual:  R4,500
Variance: +R1,500
```

The Finance AI Agent goes further.

It should be able to explain:

> **"You've exceeded your grocery budget by R1,500. Based on your current spending rate and the remaining days in the month, you're projected to exceed the budget further. If you want to remain on track with your savings goal, reducing discretionary spending for the remainder of the month would help."**

The goal is not simply to display financial information.

> **Don't just tell me where my money went. Help me decide what to do next.**

---

# ✨ Key Features

## 📊 Budget Management

Create and manage monthly budgets across categories such as:

- Housing
- Transportation
- Groceries
- Restaurants
- Family
- Entertainment
- Subscriptions
- Savings
- Investments
- Debt repayments
- Custom categories

The system compares planned spending with actual transactions.

```text
Budget:          R3,000
Actual:          R2,450
Remaining:         R550
Percentage Used: 81.7%
Status:          On Track
```

---

## 🏦 Bank Statement Import

Import financial transactions from:

- CSV
- Excel

The import pipeline normalises different bank statement formats into a consistent transaction model.

```text
Bank Statement
      ↓
Import
      ↓
Validation
      ↓
Normalisation
      ↓
Duplicate Detection
      ↓
Categorisation
      ↓
Financial Analysis
```

Future versions may support:

- PDF statements
- Open Banking
- Bank APIs
- Automatic transaction synchronisation

---

## 🧠 Intelligent Transaction Categorisation

Transactions can be categorised using multiple layers:

1. Deterministic rules
2. Merchant mappings
3. Historical categorisation
4. AI classification

For example:

```text
"CHECKERS SANDTON"

        ↓

Merchant
Checkers

        ↓

Category
Groceries
```

Users can override incorrect classifications, allowing the system to improve its merchant/category mappings over time.

---

# 🚨 Financial Drift Detection

One of the core features of the application is detecting when actual financial behaviour begins moving away from the user's plan.

For example:

```text
Groceries Budget:      R3,000
Current Spending:     R2,700
Days Remaining:            10
```

The system can identify that **90% of the budget has already been used** and calculate a projected month-end amount.

Possible insight:

> "You've used 90% of your grocery budget with 10 days remaining. At your current spending rate, you're projected to exceed your budget."

Drift can be detected at multiple levels:

### Budget Drift

Actual spending exceeds the planned budget.

### Category Drift

A specific category is significantly above its normal spending level.

### Behaviour Drift

Spending patterns change consistently over multiple months.

---

# 🔮 Spending Forecasting

The Finance Engine can estimate expected month-end spending.

The initial forecasting model can use:

```text
Projected Spending =
Current Spending
+
Average Daily Spending × Days Remaining
```

Future versions may incorporate:

- Historical spending patterns
- Salary dates
- Recurring expenses
- Upcoming commitments
- Seasonal behaviour
- Category-specific trends

Financial calculations are performed by deterministic application logic.

The AI explains the results rather than inventing financial figures.

---

# 🎯 Financial Goals

Users can define financial goals such as:

- Emergency fund
- Debt repayment
- Investments
- Home improvements
- Holiday
- Vehicle deposit
- Education
- Large purchases

Example:

```yaml
Goal:
  Emergency Fund

Target:
  R50,000

Current:
  R12,000

Remaining:
  R38,000

Monthly Contribution:
  R2,500

Target Date:
  December 2027
```

The system calculates:

- Progress
- Percentage completed
- Remaining amount
- Required contribution
- Projected completion date
- Whether the user is ahead or behind

---

# 🤖 AI Financial Agent

The AI agent provides a natural-language interface to the user's financial information.

Users can ask questions such as:

```text
How am I doing this month?

Where am I overspending?

Why did my expenses increase?

Can I afford R3,000 for a new appliance?

How much should I save this month?

Am I still on track for my emergency fund?

What changed compared with last month?

What bills are coming up?

What should I cut if I need to save another R1,000?
```

The agent uses controlled financial tools to retrieve application data.

---

# 🔧 AI Tool Calling

The AI does **not** directly access the database.

Instead, it interacts with controlled application tools.

Example:

```text
User
  ↓
AI Agent
  ↓
Financial Tool
  ↓
Application Service
  ↓
Finance Engine
  ↓
SQL Server
  ↓
Verified Result
  ↓
AI Agent
  ↓
User
```

Potential tools include:

```text
GetFinancialSummary()
GetCurrentBudget()
GetBudgetVariance()
GetCategorySpending()
GetUpcomingExpenses()
GetRecurringExpenses()
GetFinancialGoals()
GetGoalProgress()
GetRecentTransactions()
SearchTransactions()
ForecastMonthEndSpending()
CalculateAffordableSpend()
GetSpendingTrends()
GetFinancialAlerts()
CreateFinancialGoal()
UpdateBudget()
CategoriseTransaction()
```

This architecture helps keep the AI **grounded in real application data**.

---

# 💡 Example

### User

> Can I afford to spend R2,000 this weekend?

### Agent

The agent retrieves information such as:

```text
Current Available Funds
Upcoming Commitments
Remaining Budget
Current Spending Rate
Savings Contributions
Financial Goals
```

The Finance Engine performs the relevant calculations.

The AI then explains the result:

> "Based on your current financial position, spending R2,000 would put your discretionary spending above your planned amount for this month. You currently have approximately R1,200 available for discretionary spending while maintaining your existing savings commitment."

The exact figures come from the application's financial engine rather than being generated by the AI.

---

# 🔔 Proactive Financial Alerts

The system can identify important financial events without waiting for the user to ask.

Examples:

### Budget Alert

> Your dining budget is 85% used with 9 days remaining.

### Subscription Alert

> Your monthly subscriptions have increased by R350 compared with last month.

### Goal Alert

> Your emergency fund contribution is R500 below the amount required to stay on target.

### Spending Alert

> Your grocery spending is 31% higher than your three-month average.

---

# 📈 Financial Health

The application provides a transparent financial health overview based on application calculations.

Potential indicators include:

```text
Budget Health
Goal Progress
Savings Rate
Spending Drift
Upcoming Commitments
Cash Flow Risk
```

The health indicators are based on **explicit rules and calculations**, rather than an unexplained AI-generated score.

---

# 🖥️ Application Dashboard

The dashboard provides a high-level overview of the user's current financial position.

### This Month

```text
Income
Expenses
Available
Savings
```

### Budget

```text
Budget
Used
Remaining
Projected
```

### Goals

```text
Goal Progress
Monthly Target
Current Progress
```

### Alerts

```text
Budget Drift
Upcoming Expense
Goal Risk
Unusual Spending
```

### AI Agent

A conversational interface allows users to ask questions about their finances.

```text
┌───────────────────────────────────────────────┐
│ Ask me about your finances...                 │
│                                               │
│ "Why am I overspending this month?"           │
│                                               │
│                         [ Ask Agent ]         │
└───────────────────────────────────────────────┘
```

---

# 🏗️ Architecture

The application follows a layered architecture designed to separate financial calculations, application logic, infrastructure, and AI orchestration.

```text
                         ┌─────────────────┐
                         │      User       │
                         └────────┬────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │   Web Client    │
                         └────────┬────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │ ASP.NET Core API│
                         └────────┬────────┘
                                  │
              ┌───────────────────┼───────────────────┐
              │                   │                   │
              ▼                   ▼                   ▼
      ┌───────────────┐   ┌───────────────┐   ┌───────────────┐
      │ Finance Engine│   │  Agent Engine  │   │ Import Engine │
      └───────┬───────┘   └───────┬───────┘   └───────┬───────┘
              │                   │                   │
              │                   ▼                   │
              │            ┌───────────────┐          │
              │            │  AI Provider  │          │
              │            └───────────────┘          │
              │                                       │
              └───────────────────┬───────────────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │   SQL Server    │
                         └─────────────────┘
```

---

# 🧱 Project Structure

```text
FinanceAgent/
│
├── src/
│   ├── FinanceAgent.Api/
│   ├── FinanceAgent.Application/
│   ├── FinanceAgent.Domain/
│   ├── FinanceAgent.Infrastructure/
│   └── FinanceAgent.Agent/
│
├── database/
│   ├── Tables/
│   ├── Views/
│   ├── StoredProcedures/
│   ├── Functions/
│   └── Seed/
│
├── tests/
│   ├── FinanceAgent.UnitTests/
│   ├── FinanceAgent.IntegrationTests/
│   └── FinanceAgent.AgentTests/
│
├── docs/
│   ├── architecture/
│   ├── ai/
│   └── database/
│
├── samples/
│   └── bank-statements/
│
├── .github/
│   └── workflows/
│
├── docker-compose.yml
├── FinanceAgent.sln
└── README.md
```

---

# 🗄️ Database

The initial data model includes:

```text
User
Account
Transaction
TransactionCategory
Budget
BudgetItem
FinancialGoal
GoalContribution
RecurringExpense
FinancialAlert
StatementImport
Merchant
AgentConversation
AgentMessage
```

Core relationships:

```text
User
 |
 ├── Accounts
 │     └── Transactions
 │            └── Category
 │
 ├── Budgets
 │     └── Budget Items
 │
 ├── Financial Goals
 │     └── Goal Contributions
 │
 ├── Recurring Expenses
 │
 └── Alerts
```

SQL Server is intentionally used as the primary database to provide strong control over:

- T-SQL
- Stored Procedures
- Data modelling
- Query optimisation
- Financial calculations
- Reporting queries

The application does not rely on Entity Framework for database access.

ADO.NET/Dapper and explicit SQL are used where appropriate.

---

# 🌐 API

Initial API areas include:

### Accounts

```http
GET /api/accounts
GET /api/accounts/{id}
```

### Transactions

```http
GET /api/transactions
GET /api/transactions/{id}
POST /api/transactions/import
PUT /api/transactions/{id}/category
```

### Budgets

```http
GET /api/budgets/current
POST /api/budgets
PUT /api/budgets/{id}
GET /api/budgets/{id}/variance
```

### Goals

```http
GET /api/goals
POST /api/goals
GET /api/goals/{id}
GET /api/goals/{id}/progress
```

### Agent

```http
POST /api/agent/chat
GET /api/agent/insights
GET /api/agent/alerts
```

---

# 🧪 Testing

The project includes multiple testing layers.

## Unit Tests

Testing deterministic financial logic such as:

- Budget calculations
- Variance calculations
- Goal calculations
- Forecasting
- Categorisation rules
- Duplicate detection
- Financial health rules

## Integration Tests

Testing:

- API endpoints
- SQL queries
- Statement imports
- Authentication
- Financial tools
- Database interactions

## AI Evaluation

AI behaviour is evaluated for:

- Hallucinations
- Incorrect calculations
- Unsupported claims
- Incorrect tool selection
- Financial-data grounding
- Response consistency

---

# 🔐 Security & Privacy

Because the application handles financial information, security is treated as a core requirement.

The system is designed to support:

- Authentication
- Authorisation
- Secure password handling
- HTTPS
- API authentication
- Input validation
- SQL injection prevention
- Audit logging
- Secret management
- Secure AI API key storage

Financial information should never be committed to source control or exposed through application logs unnecessarily.

The application should also minimise financial information sent to external AI providers.

Where possible, the agent receives only the information necessary to answer a user's request.

---

# 🔌 MCP Integration

A future version will expose selected Finance Agent capabilities through the **Model Context Protocol (MCP)**.

Potential MCP tools include:

```text
get_budget
get_transactions
get_spending_summary
get_goal_progress
get_financial_alerts
forecast_spending
calculate_affordable_spend
```

This would allow the Finance Agent to act as a reusable financial data and tool provider for compatible AI clients.

---

# ☁️ Deployment

### Local Development

```text
Visual Studio
ASP.NET Core
SQL Server
AI Provider
Docker
```

### Future Cloud Architecture

```text
┌────────────────────┐
│    Azure App       │
│     Service        │
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│   ASP.NET Core API │
└─────────┬──────────┘
          │
     ┌────┴────┐
     ▼         ▼
┌─────────┐ ┌────────────┐
│ Azure   │ │ AI Provider│
│ SQL     │ └────────────┘
└─────────┘
```

Future deployment capabilities:

- Docker
- GitHub Actions
- Azure App Service
- Azure SQL
- Application monitoring
- CI/CD

---

# 🗺️ Roadmap

## Phase 1 — Foundation

- [ ] Solution architecture
- [ ] SQL database
- [ ] Authentication
- [ ] User profile
- [ ] Budget management
- [ ] Goal management
- [ ] Transaction management

## Phase 2 — Bank Statement Intelligence

- [ ] CSV import
- [ ] Excel import
- [ ] Transaction validation
- [ ] Transaction normalisation
- [ ] Duplicate detection
- [ ] Merchant mapping
- [ ] Transaction categorisation

## Phase 3 — Financial Intelligence

- [ ] Budget variance
- [ ] Spending trends
- [ ] Month-end forecasting
- [ ] Financial drift detection
- [ ] Financial alerts
- [ ] Goal forecasting
- [ ] Financial health indicators

## Phase 4 — AI Agent

- [ ] Agent orchestration
- [ ] Financial tools
- [ ] Tool calling
- [ ] Grounded responses
- [ ] Conversational interface
- [ ] Proactive insights
- [ ] AI evaluation

## Phase 5 — MCP & Cloud

- [ ] MCP server
- [ ] Docker
- [ ] GitHub Actions
- [ ] Azure deployment
- [ ] Azure SQL
- [ ] Application monitoring

## Phase 6 — Advanced Features

- [ ] PDF statement extraction
- [ ] Open Banking integrations
- [ ] Bank APIs
- [ ] Receipt scanning
- [ ] Recurring expense detection
- [ ] Advanced forecasting
- [ ] Multi-account support
- [ ] Multi-user support
- [ ] Mobile experience

---

# 🛠️ Technology Stack

| Area | Technology |
|---|---|
| Language | C# |
| Backend | ASP.NET Core |
| API | REST / OpenAPI |
| Database | SQL Server |
| Database Access | ADO.NET / Dapper |
| Database Logic | T-SQL / Stored Procedures |
| AI | LLM + Tool Calling |
| Agent | AI Agent Orchestration |
| Protocol | MCP |
| Authentication | ASP.NET Core Authentication |
| Testing | .NET Testing Framework |
| Containers | Docker |
| CI/CD | GitHub Actions |
| Cloud | Microsoft Azure |
| Hosting | Azure App Service |
| Database Hosting | Azure SQL |

---

# 🎓 Engineering Concepts Demonstrated

This project is designed to demonstrate practical software engineering rather than simply AI integration.

### Backend

- C#
- ASP.NET Core
- REST APIs
- Dependency Injection
- Layered Architecture
- Authentication
- API design

### Database

- SQL Server
- T-SQL
- Stored Procedures
- Relational modelling
- Query optimisation
- Data validation

### AI

- AI agents
- Tool calling
- Grounded AI
- Agent orchestration
- AI evaluation
- MCP

### Data Engineering

- File ingestion
- Data normalisation
- Transaction categorisation
- Duplicate detection
- Financial calculations
- Forecasting

### DevOps

- Git
- GitHub
- GitHub Actions
- Docker
- CI/CD

### Cloud

- Azure App Service
- Azure SQL
- Cloud architecture
- Monitoring

---

# 🧠 Core Design Principle

The most important architectural principle in this project is:

```text
┌─────────────────────────────────────┐
│       SOFTWARE CALCULATES           │
│                                     │
│ Budgets • Variance • Forecasts      │
│ Goals • Spending • Financial Rules  │
└──────────────────┬──────────────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│            AI EXPLAINS              │
│                                     │
│ Context • Insights • Recommendations│
│ Natural-language interaction        │
└──────────────────┬──────────────────┘
                   │
                   ▼
┌─────────────────────────────────────┐
│            USER DECIDES              │
│                                     │
│ The user remains responsible for    │
│ financial decisions and actions.    │
└─────────────────────────────────────┘
```

> **Numbers are calculated by software. Meaning is explained by AI. Decisions remain with the user.**

---

# ⚠️ Disclaimer

This application is a personal finance analysis and planning project.

It is not intended to:

- Execute financial transactions
- Manage investments
- Replace a qualified financial advisor
- Provide regulated financial advice
- Guarantee financial outcomes

AI-generated recommendations should be treated as informational guidance and reviewed by the user before making financial decisions.

---

# 🚀 Project Status

**Status:** 🚧 In Development

This project is being developed as a portfolio demonstration of modern **.NET backend engineering, SQL Server development, financial data processing, AI agents, tool calling, MCP, testing, and cloud deployment**.

---

# 📌 Portfolio Positioning

The Finance AI Agent is intentionally positioned as more than:

> ❌ "A budgeting dashboard with AI."

Instead:

> ✅ **An AI financial accountability agent that continuously analyses actual spending against a user's budget and financial goals, detects financial drift, and provides actionable guidance.**

The objective is to demonstrate how AI can be integrated into a real software system while maintaining **deterministic calculations, controlled data access, explainability, security, and user control.**

---

## 📄 Documentation

Additional project documentation will cover:

- Product specification
- System architecture
- Database design
- API documentation
- AI agent architecture
- Tool definitions
- Prompt design
- MCP architecture
- Testing strategy
- AI evaluation
- Deployment architecture
- Security and privacy

---

## 👨‍💻 Author

**Glory Masuluke**

Software Developer | C# / .NET | SQL Server | AI

This project forms part of my software engineering portfolio and demonstrates the integration of traditional enterprise application development with modern AI capabilities.
