# **Dutchie Integration Engine (Container Edition)**
*“Because moving dispensary data around shouldn’t feel like foraging in the woods after dark.”*

This repo contains the containerized Dutchie integration engine that powers automated syncs, incoming webhooks, and all the magical plumbing that makes accounting systems behave. It’s built for the cloud, runs lean, and tries its best not to cost you more than a cup of coffee when you don’t have clients yet.

---

## **What This Repo Is**

A few things you should know before entering:

- You’re allowed to look around.  
- You’re allowed to poke at the architecture and think, “Hey, that’s clever.”  
- You’re allowed to run the container locally and watch it go *bloop* when a webhook hits.

This repo is basically a guided museum tour of how the container works. No rope barriers, but please don’t touch the exhibits.

---

## **What This Repo Is Not**

Let’s get this out of the way:

- This is **not** open source.  
- You can’t deploy it in production.  
- You can’t fork it, resell it, or use it to launch your own Dutchie-powered crime syndicate.  
- You *may* admire it from a respectful distance.

If you actually want to run this thing for real, you’ll need a commercial license or SaaS access. Don’t worry — licenses are cheaper than lawsuits.

---

## **Features**

Things it does on purpose:

- Listens for Dutchie webhooks instead of you hammering refresh  
- Runs scheduled syncs without needing an always-on server  
- Scales to zero so you don’t get surprise cloud bills  
- Speaks fluent .NET 8  
- Behaves nicely in Azure Container Apps  
- Uses environment variables so config isn’t a scavenger hunt  

---

## **Local Development**

For the brave:

```bash
docker build -t dutchie-integrator .
docker run -p 8080:8080 dutchie-integrator
```

Check that it’s alive:

```
http://localhost:8080/health
```

If it says “OK,” your container is alive and probably hungry for API keys.

---

### **Environment Variables**

```text
DUTCHIE_API_KEY=your_key_here
DUTCHIE_WEBHOOK_SECRET=shh_its_a_secret
DB_CONNECTION_STRING=please_not_in_plain_text
TARGET_ENV=Local
```

---

## **Azure Deployment Overview**

Designed specifically for:

- **Azure Container Apps (Consumption)** — the “I don’t want to pay for idle time” special  
- A tiny Container App for webhooks  
- A scheduled Job to run syncs  
- Secrets stored somewhere safe (not your repo)  
- Zero cost unless something happens, which in Dutchie land it always does at 3 AM  

You get cloud hosting that basically naps until needed. Like a cat, but cheaper.

---

## **Licensing**

**All rights reserved.**  
(Yes, really. The lawyer version is in the LICENSE file.)

- You may look  
- You may learn  
- You may not “borrow” the code and launch DutchieSyncr.io  
- You may talk to me if you want to use this professionally  

---

## **Commercial Licensing or SaaS Access**

If you want this engine running your dispensary or ERP sync life:

**Acadia Logic LLC**  
info@acadialogic.io  

I promise licensing is painless and does *not* require selling your soul. Only a small portion of your monthly revenue.

