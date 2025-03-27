# ⚡ OblivionX - Next-Gen Threat Intelligence Dashboard  



OblivionX is a **cyber threat intelligence dashboard** designed to **track, analyze, and report malicious IPs, domains, and vulnerabilities in real-time**. It provides an intuitive UI, lightning-fast API, and a powerful backend for **cybersecurity analysts, ethical hackers, and SOC teams**.  



## 🚀 Features  

- ✅ **Threat Lookup** - Search & analyze domains, IPs, and URLs using OSINT & security APIs  

- ✅ **Global Threat Feed** - Live-streamed database of flagged threats  

- ✅ **Historical Tracking** - View changes in DNS records, Whois, and security reports over time  

- ✅ **Automated Recon** - Passive and active recon tools built-in  

- ✅ **Real-Time Notifications** - Get alerts for newly detected threats  

- ✅ **Secure & Scalable** - Built with Vue, FastAPI, Redis, and MySQL  



---



## 🏗️ Project Structure  



```

/oblivionx

├── /frontend              # Vue.js Frontend  

│   ├── /src  

│   │   ├── /components    # UI Components  

│   │   ├── /views         # App Pages  

│   │   ├── /store         # Pinia State Management  

│   │   ├── /router        # Vue Router Setup  

│   │   ├── /utils         # API Calls & Helpers  

│   ├── public/index.html  # Main HTML  

│   ├── package.json       # Dependencies  

│   ├── tailwind.config.js # TailwindCSS Config  

├── /backend               # FastAPI Backend  

│   ├── /app  

│   │   ├── /api           # API Endpoints  

│   │   ├── /core          # Core Business Logic  

│   │   ├── /models        # Database Models  

│   │   ├── /tasks         # Async Celery Jobs  

│   │   ├── /utils         # Helper Functions  

│   │   ├── main.py        # FastAPI App Entry  

│   ├── requirements.txt   # Python Dependencies  

│   ├── .env               # Environment Variables  

├── /scripts               # Deployment & Automation Scripts  

├── /nginx                 # Nginx Config for Reverse Proxy  

├── docker-compose.yml     # Dockerized Stack  

└── README.md              # This file  

```



---



## 🛠️ Tech Stack  



### **Frontend**  

- Vue 3 + Vite 🚀  

- Vue Router  

- Pinia (State Management)  

- TailwindCSS  



### **Backend**  

- FastAPI (Python) ⚡  

- Redis (Caching & Async Tasks)  

- Celery (Background Tasks)  

- MySQL (Database)  



### **Other Tools**  

- OSINT APIs (Shodan, VirusTotal, etc.)  

- Docker & Docker Compose  

- Nginx (Reverse Proxy)  



---



## 📦 Installation & Setup  



### **1️⃣ Clone the Repository**  

```bash

git clone https://github.com/yourusername/oblivionx.git

cd oblivionx

```



### **2️⃣ Setup & Run the Backend**  



**Install dependencies:**  

```bash

cd backend

python -m venv venv

source venv/bin/activate  # On Windows: venv\Scripts\activate

pip install -r requirements.txt

```



**Set up environment variables:**  

```bash

cp .env.example .env

```

Fill in the API keys & database credentials inside `.env`.  



**Start FastAPI backend:**  

```bash

uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload

```



**Run Celery workers for async tasks:**  

```bash

celery -A app.tasks.task_processor worker --loglevel=info

```



---



### **3️⃣ Setup & Run the Frontend**  



```bash

cd frontend

npm install

npm run dev

```



The app will be available at `http://localhost:5173/`.  



---



### **4️⃣ Run Everything with Docker**  



```bash

docker-compose up --build

```

This will start:  

- ✅ Backend (FastAPI)  

- ✅ Frontend (Vue)  

- ✅ Redis  

- ✅ MySQL  

- ✅ Celery workers  

- ✅ Nginx (Proxy)  



---



## 🔥 API Endpoints  



| Method | Endpoint               | Description                      |

|--------|------------------------|----------------------------------|

| GET    | `/api/threats`         | Get latest threat reports       |

| GET    | `/api/lookup/{ip}`      | Lookup threat info on an IP     |

| GET    | `/api/lookup/{domain}`  | Lookup threat info on a domain  |

| POST   | `/api/report`           | Submit a new threat report      |



Example API call:  

```bash

curl -X GET "http://localhost:8000/api/lookup/8.8.8.8"

```



---



## 📡 Deployment  



**🚀 Deploy with Docker on a Server**  

1. SSH into your server  

2. Clone the repo & set up `.env`  

3. Run:  

```bash

docker-compose up --build -d

```



**🌍 Exposing to the Internet**  

- Set up an **Nginx reverse proxy** (already included)  

- Use **Let's Encrypt** for SSL/TLS  



Example **Nginx Config (`/nginx/nginx.conf`)**:  

```nginx

server {

    listen 80;

    server_name yourdomain.com;



    location / {

        proxy_pass http://backend:8000;

        proxy_set_header Host $host;

    }

}

```



---



## 🔒 Security Considerations  



- **Rate Limiting**: Protect API from abuse  

- **JWT Authentication**: For user access control  

- **Firewall Rules**: Block suspicious traffic  

- **Encrypt API Keys & Credentials** in `.env`  



---



## ⚡ Future Roadmap  



- ✅ **Live Threat Map** (Visualize threat activity globally)  

- ✅ **User Authentication** (Login system for managing reports)  

- ✅ **More Integrations** (Tor Exit Nodes, Open Threat Exchange, etc.)  

- ✅ **Graph-Based Threat Analysis** (Connect threats in a network graph)  



---



## 🎯 Contributing  



Pull requests are welcome! Open an issue if you find bugs or have suggestions.  



---



## 📜 License  



MIT License - Free to use, modify, and contribute!  



---



## ⭐ Like This Project?  

Give it a star ⭐ on GitHub and spread the word!  



🔥 **OblivionX - Stay Ahead of the Threats.** 🔥




Now, when you paste this into your `README.md` file on GitHub, it should render cleanly and not break. 



Let me know if you need more tweaks! 👌
