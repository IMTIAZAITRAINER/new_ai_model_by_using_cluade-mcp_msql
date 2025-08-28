## Working With Claude + Angular + db.json

---

Step1: Create the new Angular Application

```
ng new my-app
cd my-app
ng g c employee
```

## Create the db.json file inside the public folder

## The following is the code of employee.component.ts
```
import { CommonModule } from '@angular/common';
import { HttpClient } from '@angular/common/http';
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-employee',
  imports: [FormsModule,CommonModule],
  templateUrl: './employee.component.html',
  styleUrl: './employee.component.css'
})
export class EmployeeComponent {
employee = {
    eid: '',
    ename: '',
    esalary: '',
    address: ''
  };

  constructor(private http: HttpClient) {}

  storeEmployee() {
    // Send data to Claude MCP endpoint
    this.http.post('http://localhost:3000/employees', {
      action: "store_employee",
      data: this.employee
    }).subscribe({
      next: res => alert("Employee stored successfully!"),
      error: err => alert("Error: " + err.message)
    });
  }
}

```
## The following is the code inside the employee.component.html

```
<form (ngSubmit)="storeEmployee()" #empForm="ngForm">
  <input type="text" placeholder="Employee ID" [(ngModel)]="employee.eid" name="eid" required>
  <input type="text" placeholder="Employee Name" [(ngModel)]="employee.ename" name="ename" required>
  <input type="number" placeholder="Salary" [(ngModel)]="employee.esalary" name="esalary" required>
  <input type="text" placeholder="Address" [(ngModel)]="employee.address" name="address" required>
  <button type="submit">Store</button>
</form>

```
## Now start the angular application and json

```
npm start
json-server --watch db.json
```
## Now configure the playwrite and mysql into an claude_desktop_config.json

```
{
  "mcpServers": {
    "mysql": {
      "command": "npx",
      "args": [
        "-y",
        "@executeautomation/database-server",
        "--mysql",
        "--host", "localhost",
        "--database", "ai_db",
        "--port", "3306",
        "--user", "root",
        "--password", "root"
      ]
    },
   "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest"]
    }
  },
  "prompts": {
    "add_employee_ui": "Open http://localhost:4200, fill the employee form with {{data}}, and submit it"
  }
}

```

## Now open the claude and type the prompt

<img width="882" height="77" alt="image" src="https://github.com/user-attachments/assets/3871aac2-6a01-4341-a2ad-0bba4eb12b99" />




## Now u can see the final flow












