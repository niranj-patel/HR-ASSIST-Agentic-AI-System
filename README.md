# HR-ASSIST Agentic AI System

An AI-powered Human Resources Management System built with the Model Context Protocol (MCP) for Claude Desktop integration.

## Features

- **Employee Management**: Add and retrieve employee information
- **Leave Management**: Track balances, apply for leave, view history
- **Meeting Scheduling**: Schedule and manage meetings with conflict detection
- **Ticket System**: Create and manage IT/HR support tickets
- **Email Integration**: Automated email sending capabilities

## Quick Setup

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
2. **Set up environment variables:**
   Create a `.env` file in the project root and add the following variables:
   ```
   CB_EMAIL=your_email@example.com
   CB_EMAIL_PWD=your_app_password
   ```
   Replace `your_email@example.com` with your actual email and `your_app_password` with your email provider's app-specific password.

3. Add to Claude Desktop config:
   - Open `claude_desktop_config.json`
   - Add the following configuration:
   ```json
   {
     "mcpServers": {
       "hr-assist": {
         "command": "python",
         "args": [
           "server.py"
         ],
         "env": {
           "CB_EMAIL": "your_email@example.com",
           "CB_EMAIL_PWD": "your_app_password"
         }
       }
     }
   }
   ```

4. Run the server:
   ```bash
   python server.py
   ```

5. Start Claude Desktop and use the `hr-assist` server.

## Usage
Interact with Claude Desktop using natural language:

- "Add a new employee named John Doe"
- "Schedule a meeting for tomorrow at 2 PM"
- "Check my leave balance"
- "Create a ticket for laptop repair"

## Project Structure
├── server.py          # Main MCP server <br>
├── emails.py          # Email service <br>
├── utils.py           # Utilities and data seeding<br>
├── requirements.txt   # Dependencies <br>
└── hrms/             # HR modules <br>
    ├── schemas.py    # Data models <br>
    ├── employee_manager.py <br>
    ├── leave_manager.py <br>
    ├── meeting_manager.py <br>
    └── ticket_manager.py <br>
    



