# AI MODEL BY USING CLUADE + MCP + MYSQL DB
---

### Step1: Install the cluade by downloading by using following link:
 Link  : https://claude.ai/download

### Step2: Configure the mcp_datbase server by using following link:
Link : https://github.com/executeautomation/mcp-database-server

```
{
  "mcpServers": {
    "sqlite": {
      "command": "npx",
      "args": [
        "-y",
        "@executeautomation/database-server",
        "/path/to/your/database.db"
      ]
    },
    "sqlserver": {
      "command": "npx",
      "args": [
        "-y",
        "@executeautomation/database-server",
        "--sqlserver",
        "--server", "your-server-name",
        "--database", "your-database-name",
        "--user", "your-username",
        "--password", "your-password"
      ]
    },
    "postgresql": {
      "command": "npx",
      "args": [
        "-y",
        "@executeautomation/database-server",
        "--postgresql",
        "--host", "your-host-name",
        "--database", "your-database-name",
        "--user", "your-username",
        "--password", "your-password"
      ]
    },
    "mysql": {
      "command": "npx",
      "args": [
        "-y",
        "@executeautomation/database-server",
        "--mysql",
        "--host", "your-host-name",
        "--database", "your-database-name",
        "--port", "3306",
        "--user", "your-username",
        "--password", "your-password"
      ]
    },
    "mysql-aws": {
      "command": "npx",
      "args": [
        "-y",
        "@executeautomation/database-server",
        "--mysql",
        "--aws-iam-auth",
        "--host", "your-rds-endpoint.region.rds.amazonaws.com",
        "--database", "your-database-name",
        "--user", "your-aws-username",
        "--aws-region", "us-east-1"
      ]
    }
  }
}

```
---


### Step3: Once we install the clude desktop 
```
open it and configure the inside the File-> Settings-> Developer -> Edit Config -> claude_desktop_config.json (open in notepad and configure the above mysql)
```
<img width="1876" height="1000" alt="image" src="https://github.com/user-attachments/assets/09b77b96-f151-413f-8072-24a38704440e" />

----

### Step4: Restart teh Claude app

### Step5: Now we can use it 
<img width="1808" height="928" alt="image" src="https://github.com/user-attachments/assets/61605654-28da-4946-8651-3549a2628e11" />


### Step6: Now we can write the prompts it will generate the data.

<img width="1470" height="600" alt="image" src="https://github.com/user-attachments/assets/7d00a510-9d48-49a1-b348-3a805dd56c88" />






 
