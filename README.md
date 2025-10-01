<img width="710" height="190" alt="image" src="https://github.com/user-attachments/assets/3676593d-b2db-47e6-87d0-8047a70308e1" />

# 📱 Google Play Review Intelligence with Bright Data & Telegram Alerts

An **n8n-powered automation** that scrapes **Google Play Store reviews**, analyzes app performance, and instantly sends **Telegram alerts 🚨** for apps with **low ratings (<4⭐)**.  
Data is stored in **Google Sheets 📊** for long-term tracking and analysis.

---

## 📋 Overview
This workflow helps developers, marketers, and product teams stay on top of **user sentiment** and **app performance** with minimal effort.  
It integrates **Bright Data (scraping)** → **Google Sheets (storage)** → **Telegram (alerts)**.

---

## 🔗 Workflow Components

1. ✅ **Trigger Input Form** → User enters Play Store app URL + review count  
2. 🚀 **Start Scraping Request** → Send scrape request to Bright Data API  
3. 🔄 **Check Scrape Status** → Poll scraping job progress  
4. ⏱️ **Wait (45s)** → Efficient API usage while waiting  
5. 🧩 **Verify Completion** → IF status = `"ready"`, move ahead  
6. 📥 **Fetch Scraped Data** → Retrieve reviews + app info (JSON)  
7. 📊 **Save to Google Sheets** → Append structured review data  
8. ⚠️ **Check Low Ratings** → Identify apps/reviews < 4⭐  
9. 📣 **Send Telegram Alert** → Notify team of performance issues  

**Workflow Flow:**  
`Form Input → Scrape → Check Status → Wait → Verify → Fetch Data → Save → Check Ratings → Telegram Alert`

---

## ⚙️ Configuration Requirements

### 🔑 API Keys & Credentials
- **Bright Data API Key** → Required for scraping  
- **Google Sheets OAuth2** → Data storage  
- **Telegram Bot Token** → Notifications  

### 📝 Setup Parameters
- Google Sheet ID → Target spreadsheet  
- Telegram Chat ID → Destination channel/group  
- Dataset ID → `gd_m6zagkt024uwvvwuyu` (Google Play reviews dataset)  

---

## 🚀 Setup Instructions

### Step 1: Import Workflow
- Copy JSON config → `n8n → Workflows → Import from JSON`  
- Paste & save  

### Step 2: Configure Bright Data
- Add **Bright Data credentials** in n8n  
- Replace `BRIGHT_DATA_API_KEY` in HTTP nodes  
- Ensure dataset access: `gd_m6zagkt024uwvvwuyu`  

### Step 3: Configure Google Sheets
- Create sheet (e.g., **App Review Data**)  
- Copy **Sheet ID** from URL  
- Add Google Sheets OAuth2 in n8n  
- Replace `YOUR_GOOGLE_SHEET_ID` in workflow  

### Step 4: Configure Telegram Alerts
- Create Telegram Bot with **@BotFather**  
- Get **Bot Token** + **Chat ID**  
- Add credentials in n8n  

### Step 5: Test & Activate
- Submit a Play Store app URL + review count  
- Verify reviews populate in Google Sheets  
- Check if Telegram alerts trigger for ratings < 4⭐  

---

## 📊 Key Features

✅ **Comprehensive Data Collection**  
- App Title, Developer, Country  
- Ratings, Reviews, Sentiment Data  
- What’s New, App Metadata  

✅ **Quality Monitoring**  
- Detects reviews < 4⭐  
- Auto Telegram alerts for underperforming apps  
- Early-warning system for QA teams  

✅ **Seamless Integrations**  
- Bright Data → Scraping  
- Google Sheets → Storage & analysis  
- Telegram → Instant notifications  

---

## 🎯 Use Cases

📈 **App Performance Monitoring**  
- Track rating trends over time  
- Monitor competitor reviews  
- Benchmark market positioning  

🛠️ **Quality Assurance**  
- Detect sudden drops in ratings  
- Analyze recurring negative feedback  
- Improve customer satisfaction  

📊 **Business Intelligence**  
- Review sentiment tracking  
- Strategic decision-making support  
- Product improvement insights  

---

## 📑 Data Output Fields

| Field                | Description                  | Example                              |
|-----------------------|------------------------------|--------------------------------------|
| **App Title**         | Name of the app             | WhatsApp Messenger                   |
| **Developer**         | App publisher               | Meta Platforms, Inc.                 |
| **Review ID**         | Unique review identifier    | gp:AOqpTOGRi123456                   |
| **Reviewer Name**     | User who posted review      | John Doe                             |
| **Review Date**       | Date posted                 | 2025-09-20                           |
| **Review Rating**     | Star rating (1–5)           | 3                                    |
| **Review Text**       | Full review content         | "Crashes often after latest update." |
| **App Rating**        | Overall rating              | 4.2                                  |
| **App # of Reviews**  | Total reviews               | 1,254,389                            |
| **Country**           | App country availability    | US                                   |

---

## 🔍 Troubleshooting

⚠️ **Invalid URL** → Make sure Play Store app URL is valid  
⚠️ **Rate Limiting** → Check Bright Data API usage  
⚠️ **Credential Issues** → Verify all API keys & tokens  
⚠️ **No Telegram Alerts** → Ensure chat ID & bot token are correct  

---

## ⚡ Performance Specs
- ⏱️ Processing Time → 2–6 mins per request  
- ⭐ Rating Threshold → Alerts for < 4⭐  
- 📊 Storage → Unlimited via Google Sheets  
- 🔁 Polling Interval → 45s for scraping progress  

---

## 🎉 Final Note
This workflow gives **real-time insights** into Google Play app performance, with **automatic monitoring & instant alerts 🚨**. Perfect for:  
- 👨‍💻 Developers  
- 📱 App marketers  
- 🏢 Product managers  

---

👨‍💻 **Built with n8n + Bright Data + Google Sheets + Telegram**
