📟 Cyber-Terminal Portfolio v1.0
A high-performance, minimalist portfolio with a "Terminal/Hacker" aesthetic. Built with a focus on clean typography, CSS grid layouts, and a secure communication relay via EmailJS.

🚀 Features
Cyberpunk UI: Custom CSS grid background with a monochromatic high-contrast theme.

Dual-Template Relay: Automated logic that sends an admin notification to you and an instant receipt to the sender.

Anti-Bot Protection: Implementation of a "Honeypot" trap to prevent automated spam submissions from consuming your quota.

Responsive Architecture: Fully fluid layout that shifts from a split-pane desktop view to a stacked mobile interface.

🛠 Tech Stack
Frontend: HTML5, CSS3 (Flexbox/Grid), JavaScript (ES6)

Icons: Lucide Icons

Email Engine: EmailJS

📧 EmailJS Setup (Manual Configuration)
To get the contact form working, you must create your own EmailJS account and templates. Do not use the project's original keys.

1. The Templates
You need to create two templates in your EmailJS dashboard:

Template A: Admin Notification

Recipient: Your own email.

Reply-To Field: {{reply_to}}

Body: Includes {{from_name}}, {{reply_to}}, and {{message}}.

Template B: User Auto-Reply

To Email Field: {{reply_to}}

Body: A confirmation message thanking them for reaching out.

2. The Keys
In script.js and index.html, fill in your own credentials:

JavaScript

// In index.html
emailjs.init("YOUR_PUBLIC_KEY");

// In script.js
const serviceID = "YOUR_SERVICE_ID";
const adminTemplateID = "YOUR_ADMIN_TEMPLATE_ID";
const autoReplyTemplateID = "YOUR_AUTOREPLY_TEMPLATE_ID";
🛡 Security & Anti-Spam
This project uses a Honeypot technique. Any input detected in the hidden field _honey will cause the script to terminate the send request immediately. This ensures that only human users can trigger the EmailJS API.

JavaScript

if (formData.get('_honey')) {
    console.warn("BOT_DETECTED: TERMINATING_TRANSMISSION");
    return;
}
📂 Installation
Clone the repository:

Bash

git clone https://github.com/carlxsx/your-repo-name.git
Open index.html in any modern browser.

Replace the EmailJS placeholders with your own keys.

👤 Author
Carlos Miguel

Status: [ OPEN_FOR_PROJECTS ]
