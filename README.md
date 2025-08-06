# 🚀 OSM Admin API - Complete Odoo Server Management Solution

> **Professional Odoo Server Management Made Simple**

A comprehensive API solution for managing multiple Odoo instances, users, domains, backups, and more - all from a single, powerful interface.

---

## ✨ **What Can You Do?**

### 🏗️ **Instance Management**
- **Create** new Odoo instances with custom configurations
- **Clone** existing instances with all addons and data
- **Start/Stop/Restart** instances with simple commands
- **Delete** instances safely with database options
- **List** all instances with detailed status information

### 👥 **User Management**
- **Create** Odoo users with custom permissions
- **Suspend/Activate** user accounts
- **Reset** passwords securely
- **Manage** Linux system users
- **Impersonate** users for support purposes

### 🌐 **Domain & SSL Management**
- **Add/Remove** custom domains for your instances
- **Automatic SSL** certificate generation (Let's Encrypt)
- **Proxy** configuration (Nginx/Traefik)
- **DNS** management integration

### 💾 **Backup & Recovery**
- **Automated** backup scheduling
- **Manual** backup creation and download
- **Database** restoration with target options
- **Remote** backup storage (Google Drive, OneDrive)
- **Cron-based** automated backups

### 🔧 **Development Tools**
- **Python package** management (pip)
- **GitHub addon** integration
- **Webhook-based** automatic updates
- **Custom addon** installation

### 📊 **Monitoring & Analytics**
- **System metrics** and performance monitoring
- **Installation logs** and service status
- **PostgreSQL** connection monitoring
- **Real-time** server health checks

### 🧩 **Odoo Apps Management**
- **List** all Odoo apps (base, custom, GitHub addons)
- **Install/Upgrade/Uninstall** apps for any instance
- **Filter** apps by state (installed, uninstalled, to_upgrade)
- **View** detailed metadata and dependencies

### 🤖 **AI-Powered Chatbot**
- **Natural language** instance management
- **Intelligent** conversation with context awareness
- **Automatic** parameter extraction from user messages
- **Smart** action execution based on AI understanding

---

## 🎯 **Key Benefits**

### **Multi-Tenant Architecture**
- Manage multiple Odoo instances on a single server
- Each instance is isolated with its own user and domain
- Unified API for all instances

### **Enterprise Security**
- API key authentication for all endpoints
- Secure user impersonation for support
- SSL certificate management
- Comprehensive audit logging

### **Automation & Efficiency**
- Automated backup scheduling
- Webhook-based updates
- AI-powered natural language interface
- Bulk operations support

### **Professional Support**
- Detailed logging for troubleshooting
- Health monitoring endpoints
- Performance metrics
- Error tracking and reporting

---

## 🔑 **Getting Started**

### **1. API Authentication**
All requests require an API key for security. Your system administrator will provide you with:
- **OSM API Key** - For accessing all endpoints
- **Google Gemini API Key** - For AI chatbot functionality (optional)

### **2. Making Your First Request**
```bash
# Check if the API is running
curl -X GET http://your-server:8000/health \
  -H "X-API-Key: your-api-key"

# List all Odoo instances
curl -X GET http://your-server:8000/api/instances \
  -H "X-API-Key: your-api-key"
```

### **3. Using the AI Chatbot**
```bash
# Create a new instance using natural language
curl -X POST http://your-server:8000/api/chatbot/chat \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "message": "Create a new Odoo instance for user john with website example.com"
  }'
```

---

## 📚 **API Endpoints Overview**

### **🏢 Instance Management**
- `GET /api/instances` - List all instances
- `POST /api/instances` - Create new instance
- `PUT /api/instances/{user}/{website}` - Update instance
- `DELETE /api/instances/{user}/{website}` - Delete instance
- `POST /api/instances/{user}/{website}/start` - Start instance
- `POST /api/instances/{user}/{website}/stop` - Stop instance
- `POST /api/instances/{user}/{website}/restart` - Restart instance

### **👤 User Management**
- `GET /api/users` - List all users
- `POST /api/users` - Create new user
- `PUT /api/users/{user_id}` - Update user
- `DELETE /api/users/{user_id}` - Delete user
- `POST /api/users/{user_id}/suspend` - Suspend user
- `POST /api/users/{user_id}/activate` - Activate user
- `POST /api/users/{user_id}/reset-password` - Reset password

### **💾 Backup Management**
- `GET /api/backups` - List all backups
- `POST /api/backups` - Create manual backup
- `GET /api/backups/{backup_id}/download` - Download backup
- `POST /api/backups/{backup_id}/restore` - Restore backup
- `GET /api/backups/schedule` - Get backup schedule
- `POST /api/backups/schedule` - Set backup schedule

### **🌐 Domain Management**
- `GET /api/domains` - List all domains
- `POST /api/domains` - Add new domain
- `DELETE /api/domains/{domain}` - Remove domain
- `POST /api/domains/{domain}/ssl` - Generate SSL certificate

### **🧩 Apps Management**
- `GET /api/apps/{user}/{website}` - List instance apps
- `POST /api/apps/{user}/{website}/install` - Install app
- `POST /api/apps/{user}/{website}/uninstall` - Uninstall app
- `POST /api/apps/{user}/{website}/upgrade` - Upgrade app

### **🤖 AI Chatbot**
- `POST /api/chatbot/chat` - Send message to AI
- `GET /api/chatbot/status` - Get chatbot status
- `POST /api/chatbot/test` - Test AI connection

### **📊 Monitoring**
- `GET /api/metrics` - Get system metrics
- `GET /api/logs` - Get installation logs
- `GET /health` - Health check

---

## 🎨 **Usage Examples**

### **Creating a New Odoo Instance**
```bash
curl -X POST http://your-server:8000/api/instances \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "user": "john",
    "website": "example.com",
    "odoo_version": "16.0",
    "email": "admin@example.com"
  }'
```

### **Starting an Instance**
```bash
curl -X POST http://your-server:8000/api/instances/john/example.com/start \
  -H "X-API-Key: your-api-key"
```

### **Creating a Backup**
```bash
curl -X POST http://your-server:8000/api/backups \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "user": "john",
    "website": "example.com",
    "description": "Monthly backup"
  }'
```

### **Adding a Custom Domain**
```bash
curl -X POST http://your-server:8000/api/domains \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "domain": "myapp.example.com",
    "user": "john",
    "website": "example.com"
  }'
```

### **Using the AI Chatbot**
```bash
# Natural language instance creation
curl -X POST http://your-server:8000/api/chatbot/chat \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "message": "Create a test Odoo instance with any version for user demo"
  }'

# Natural language instance management
curl -X POST http://your-server:8000/api/chatbot/chat \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "message": "Start the instance for user john and website example.com"
  }'
```

---

## 🔧 **Advanced Features**

### **Automated Backups**
Set up automated backup schedules that run daily, weekly, or monthly:
```bash
curl -X POST http://your-server:8000/api/backups/schedule \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "user": "john",
    "website": "example.com",
    "frequency": "daily",
    "time": "02:00",
    "retention_days": 30
  }'
```

### **Remote Backup Storage**
Configure backups to be stored in Google Drive or OneDrive:
```bash
# Google Drive backup
curl -X POST http://your-server:8000/api/backups \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "user": "john",
    "website": "example.com",
    "remote_storage": "gdrive",
    "folder_id": "your-gdrive-folder-id"
  }'
```

### **GitHub Integration**
Install addons directly from GitHub repositories:
```bash
curl -X POST http://your-server:8000/api/github/install \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your-api-key" \
  -d '{
    "user": "john",
    "website": "example.com",
    "repo": "OCA/partner-contact",
    "branch": "16.0"
  }'
```

### **SSL Certificate Management**
Automatically generate SSL certificates for your domains:
```bash
curl -X POST http://your-server:8000/api/domains/myapp.example.com/ssl \
  -H "X-API-Key: your-api-key"
```

---

## 📊 **Monitoring & Health**

### **System Health Check**
```bash
curl -X GET http://your-server:8000/health \
  -H "X-API-Key: your-api-key"
```

### **Performance Metrics**
```bash
curl -X GET http://your-server:8000/api/metrics \
  -H "X-API-Key: your-api-key"
```

### **Installation Logs**
```bash
curl -X GET http://your-server:8000/api/logs \
  -H "X-API-Key: your-api-key"
```

---

## 🛡️ **Security Features**

### **API Key Authentication**
- All endpoints require a valid API key
- Keys are validated on every request
- Failed attempts are logged for security monitoring

### **User Impersonation**
- Secure user impersonation for support purposes
- Session-based authentication
- Audit logging for all impersonation activities

### **SSL Certificate Management**
- Automatic Let's Encrypt certificate generation
- DNS challenge validation
- Certificate renewal monitoring

### **Data Protection**
- Encrypted backup storage
- Secure password reset procedures
- Comprehensive audit logging

---

## 🚀 **Performance & Scalability**

### **Multi-Tenant Architecture**
- Isolated instances per user/domain
- Resource sharing across instances
- Efficient resource utilization

### **Automated Operations**
- Background backup processing
- Scheduled maintenance tasks
- Asynchronous operation handling

### **Monitoring & Alerts**
- Real-time performance monitoring
- Automated health checks
- Proactive issue detection

---


## 📞 **Support & Documentation**

### **Interactive API Documentation**
- Swagger UI available at `/docs`
- Complete endpoint documentation
- Request/response examples
- Interactive testing interface

### **AI-Powered Assistance**
- Natural language interface for common tasks
- Intelligent error handling
- Context-aware suggestions

### **Comprehensive Logging**
- Detailed operation logs
- Error tracking and reporting
- Performance monitoring

---

## 🎯 **Perfect For**

- **Hosting Providers** - Manage multiple client instances
- **Enterprise IT** - Centralized Odoo management
- **Development Teams** - Automated deployment and testing
- **System Administrators** - Efficient server management
- **Support Teams** - Quick issue resolution and user assistance

---

## 📈 **Why Choose OSM Admin API?**

✅ **Complete Solution** - Everything you need in one API  
✅ **Multi-Tenant** - Manage unlimited instances efficiently  
✅ **AI-Powered** - Natural language interface for easy use  
✅ **Enterprise Security** - Professional-grade security features  
✅ **Automated Operations** - Set it up and let it run  
✅ **Comprehensive Monitoring** - Always know what's happening  
✅ **Professional Support** - Detailed logging and error handling  

---


*Ready to transform your Odoo server management? Get started today! 🚀* 

