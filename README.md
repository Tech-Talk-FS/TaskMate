# TaskMate

App used by contractors to automate communication between clients, keep track of invoices, and send location and estimated arrival time.

### Technologies Used

This project will rely on a Restful API.

### Database Models

**Customer** 👨🏼

```json
{
  "customerModel": {
    "Id": "Number",
    "client_name": "String",
    "location": "String",
    "quoted_amount": "Number",
    "project_description": "String",
    "priority": "Number",
    "created_at": "String"
  }
}
```

**Jobs**

```json
{
  "jobs": {
    "Id": "Number",
    "job_type": "String",
    "is_recurring": "Boolean",
    "clocked_time": "Number",
    "description": "Number",
    "create_at": "Number"
  }
}
```

**User/Contractor** 👷🏼

```json
{
  "userModel": {
    "Id": "Number",
    "user_name": "String",
    "password": "String",
    "job_title": "String",
    "company_logo": "url",
    "invoices": ["InvoiceModel[Array]"],
    "company_address": "String",
    "created_at": "Number",
    "_comment": "Password not required if using OAuth. Company logo is optional."
  }
}
```

**Invoices**

```json
{
  "invoiceModel": {
    "Id": "Number",
    "invoice_title": "String",
    "customer_address": "String",
    "contractor_address": ["userModel.company_address"],
    "work_completed": ["Array"],
    "created_at": "Number"
  }
}
```
