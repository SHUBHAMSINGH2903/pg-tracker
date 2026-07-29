# 📱 PG Meals Automated Outreach & Broadcast Guide

> **लक्ष्य**: 100+ सब्सक्राइबर्स को सुबह 10:00 बजे और 2:00 बजे ऑटोमेटिकली मैसेज भेजना ताकि वे एक टैप में "हाँ" या "ना" में उत्तर दे सकें।

---

## 💬 WhatsApp Message Templates

रोज सुबह इन टेम्पलेट्स को सब्सक्राइबर्स की लिस्ट में ब्रॉडकास्ट (Broadcast) करें:

### Morning Message (सुबह 10:00 AM)
```
Ghar Jaisa Khana 🍳

नमस्ते! आज रात के डिनर (डिनर समय: 7:30 PM - 8:30 PM) के लिए क्या आप अपना टिफिन चाहते हैं?

*आज का मेनू:*
🧀 पनीर बटर मसाला, दाल तड़का, जीरा राइस और 4 गरमा-गरम रोटियां।

कृपया नीचे दिए गए लिंक में से किसी एक पर क्लिक करके अपना जवाब दें (सिर्फ एक बार टैप करें):

👉 हाँ, मुझे आज खाना चाहिए (YES):
https://wa.me/918449311016?text=YES_[Name]

👉 नहीं, आज खाना नहीं चाहिए (NO):
https://wa.me/918449311016?text=NO_[Name]

(कृपया दोपहर 3:00 बजे से पहले अपना जवाब दें। धन्यवाद!)
```

*नोट: हर सब्सक्राइबर के लिए लिंक में `[Name]` की जगह उनका नाम बदल दें (जैसे: `YES_Rahul`, `YES_Preeti`).*

---

### Remind Message (दोपहर 02:00 PM)
*(सिर्फ उन लोगों को भेजें जिन्होंने सुबह 10:00 बजे के मैसेज का रिप्लाई नहीं किया था)*

```
Ghar Jaisa Khana 🍳 (रिमाइंडर)

नमस्ते! आज रात के टिफिन की तैयारी शुरू होने वाली है। 

क्या आपको आज डिनर चाहिए? कृपया नीचे टैप करके कन्फर्म करें:

👉 हाँ, मुझे आज खाना चाहिए (YES):
https://wa.me/918449311016?text=YES_[Name]

👉 नहीं, आज खाना नहीं चाहिए (NO):
https://wa.me/918449311016?text=NO_[Name]

(मम्मी शाम 3:00 बजे टिफिन की काउंटिंग बंद कर देंगी। धन्यवाद!)
```

---

## 🛠️ Auto-Counter Automation Setup (100% Free)

जब सब्सक्राइबर्स `YES_Rahul` या `YES_Preeti` लिखकर आपके WhatsApp पर भेजेंगे, तो उसे ऑटोमेटिकली रीड करके आपके काउंटर को अपडेट करने के लिए यह सेटअप करें:

### Step 1: Install Auto-Responder on your Android Phone
1. Google Play Store खोलें और **"AutoResponder for WA"** या **"WhatsAuto"** ऐप इंस्टॉल करें (दोनों फ्री हैं)।
2. ऐप को WhatsApp Notifications रीड करने की परमिशन दें।

### Step 2: Create a Rule in AutoResponder App
1. **Rule type**: Choose `Pattern matching` or `Regex (Regular Expression)`.
2. **Received Message (क्या मैसेज आने पर ट्रिगर हो)**:  
   `YES_(.*)`  
   *(यह किसी भी मैसेज को डिटेक्ट करेगा जो "YES_" से शुरू होता है, जैसे YES_Rahul)*
3. **Action / Reply Message (सामने वाले को क्या रिप्लाई जाए)**:  
   `जी, आपका आज का डिनर कन्फर्म हो गया है! 🍳`
4. **Integration**:  
   - Select **Tasker / Webhook** integration.
   - We will point this webhook to your Google Sheet so that a new row is added automatically.

---

## 📊 Google Sheets setup

1. एक नई Google Sheet बनाएँ।
2. Columns: `Date (तारीख)`, `Name (नाम)`, `Status (YES/NO)`
3. AutoResponder ऐप Google Sheet API के जरिए सीधे शीट में डेटा लिखता रहेगा।
4. Mummy का Dashboard (जो हमने बनाया है) सीधे इस Google Sheet से लाइव काउंट सिंक कर लेगा।

---

## 🚀 deployment

मैं इस `pg-tracker` (मम्मी का डैशबोर्ड) को भी आपके GitHub पर पोस्ट कर देता हूँ ताकि यह ऑनलाइन लाइव हो जाए और मम्मी इसे अपने फ़ोन पर खोल सकें।
