# 🤖 AI-Powered Email Classification using UiPath REFramework & Generative AI

## 📖 Project Overview

AI-Powered Email Classification is an intelligent automation solution developed using **UiPath REFramework**, **UiPath Orchestrator Queues**, **Gmail Integration**, and **Generative AI (GPT-5.1)**.

The objective of this project is to automate the process of reading incoming emails, classifying them into business departments using AI, extracting meaningful insights, and generating department-wise reports for business users.

Traditional email processing solutions rely on keyword matching and predefined rules, which become difficult to maintain as business requirements grow. This project leverages Large Language Models (LLMs) to understand the actual meaning and context of emails before categorizing them.

The solution demonstrates how Robotic Process Automation (RPA) and Artificial Intelligence can work together to create intelligent enterprise automation.

---

# 🎯 Business Problem

Organizations receive hundreds of emails every day from employees and customers.

These emails may contain:

- HR Requests
- Salary Revision Requests
- Leave Requests
- IT Support Issues
- Finance Queries
- General Enquiries

Traditionally, employees manually read every email and decide which department should handle it.

This approach is:

- Time consuming
- Error prone
- Difficult to scale
- Requires significant manual effort

This project automates the complete classification process using AI.

---

# 💡 Solution

The automation performs the following tasks:

- Connects to Gmail
- Reads unread emails
- Downloads email attachments
- Stores each email as a Queue Item in UiPath Orchestrator
- Processes each transaction using REFramework
- Sends email details to GPT-5.1
- AI classifies the email
- AI returns structured JSON response
- UiPath deserializes the JSON
- Creates department-wise reports
- Stores reports into department-specific folders

---

# 🏗 Solution Architecture

```
                Gmail Inbox
                     │
                     ▼
          Read Unread Emails
                     │
                     ▼
          Download Attachments
                     │
                     ▼
              Producer Process
                     │
                     ▼
         UiPath Orchestrator Queue
                     │
                     ▼
              Consumer Process
             (REFramework)
                     │
                     ▼
      Build Prompt for AI Model
                     │
                     ▼
     GPT-5.1 Content Generation
                     │
                     ▼
        Structured JSON Response
                     │
                     ▼
          Deserialize JSON
                     │
                     ▼
       Extract Classification
       • Category
       • Priority
       • Summary
       • Suggested Action
                     │
                     ▼
       Department-wise Reports
                     │
                     ▼
      HR / Finance / IT / Leave /
          General Report Files
```

---

# ⚙ Technologies Used

### RPA

- UiPath Studio
- UiPath REFramework
- UiPath Orchestrator
- Queue Based Processing

### Artificial Intelligence

- GPT-5.1
- Prompt Engineering
- JSON Response Generation

### Email Automation

- Gmail Integration
- Email Processing
- Attachment Handling

### Data Processing

- JSON Parsing
- Deserialize JSON
- Queue Transactions

### Reporting

- Text Report Generation
- Department-wise Report Creation

### Development Tools

- Git
- GitHub

---

# 📂 Project Structure

```
AI_Email_Classification

│
├── Framework
│
├── Producer.xaml
│
├── Process.xaml
│
├── Main.xaml
│
├── Config.xlsx
│
├── HR_MAIL
│
├── FINANCE_MAIL
│
├── IT_MAIL
│
├── LEAVE_MAIL
│
└── GENERAL_MAIL
```

---

# 🔄 Workflow

## 1. Initialization

- Loads configuration from Config.xlsx
- Initializes Gmail connection
- Creates report paths
- Loads required settings

---

## 2. Producer

The Producer performs the following tasks:

- Reads unread Gmail emails
- Downloads attachments
- Extracts

  - Sender
  - Subject
  - Body
  - Attachment Path

- Creates Queue Items
- Pushes each email into UiPath Orchestrator Queue

---

## 3. Consumer

Consumer uses REFramework.

Each Queue Item is processed individually.

The consumer:

- Reads Queue Item
- Builds AI Prompt
- Sends Email Details to GPT-5.1
- Receives JSON Response
- Deserializes JSON
- Extracts

  - Category
  - Priority
  - Summary
  - Suggested Action

---

# 🤖 AI Prompt Engineering

The AI receives:

- Sender
- Subject
- Email Body
- Attachment Information

The model analyzes the complete email and returns structured JSON.

Example:

```json
{
  "Category":"HR",
  "Priority":"Medium",
  "Summary":"Employee requesting salary revision.",
  "SuggestedAction":"Forward request to HR Team."
}
```

---

# 📋 Email Categories

The AI classifies emails into:

- HR
- Finance
- IT
- Leave
- General

---

# 📄 Report Generation

Instead of generating a single report, the solution generates department-specific reports.

Example:

```
HR_MAIL

HR_Report_20260714.txt
```

```
FINANCE_MAIL

Finance_Report_20260714.txt
```

```
IT_MAIL

IT_Report_20260714.txt
```

```
LEAVE_MAIL

Leave_Report_20260714.txt
```

```
GENERAL_MAIL

General_Report_20260714.txt
```

Each report contains:

- Processed Time
- Sender
- Subject
- Priority
- AI Summary
- Suggested Action
- Attachment Details

---

# ⭐ Features

- Queue Based Processing
- REFramework Architecture
- Gmail Integration
- AI Powered Email Classification
- JSON Response Handling
- Attachment Processing
- Department-wise Report Generation
- Exception Handling
- Retry Mechanism
- Modular Workflow Design

---

# 🔒 Exception Handling

The project follows UiPath REFramework best practices.

- Business Exceptions
- System Exceptions
- Retry Logic
- Queue Transaction Status Update
- Detailed Logging

---

# 🚀 Future Enhancements

- Power BI Dashboard
- SharePoint Integration
- SQL Database Storage
- Email Notifications
- Sentiment Analysis
- Confidence Score
- AI-based Auto Reply
- ServiceNow Ticket Creation
- Automatic Case Assignment
- Multi-language Email Support

---

# 📈 Business Benefits

- Reduces manual email processing
- Faster email triaging
- Improves operational efficiency
- Consistent AI-based classification
- Department-specific reporting
- Scalable enterprise solution
- Demonstrates RPA + AI integration

---

# 👨‍💻 Author

**Kaviyanjali V**

Software Engineer | UiPath RPA Developer

Skills:

- UiPath
- REFramework
- Orchestrator
- Queue Processing
- Gmail Automation
- Generative AI
- Prompt Engineering
- JSON Handling
- Intelligent Automation

---

# 📜 License

This project is created for learning, demonstration, and portfolio purposes.
