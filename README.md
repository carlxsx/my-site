Project Documentation: Cyber-Terminal Portfolio
Overview
A minimalist, high-performance developer portfolio featuring a monochromatic terminal aesthetic. The project focuses on clean typography, responsive grid layouts, and a secure communication relay system.

Technical Architecture
Frontend Composition
Typography: Space Mono (Google Fonts) for a monospaced, data-driven feel.

Layout: CSS Grid and Flexbox for a split-pane interface that adapts to mobile devices via media query overrides.

Icons: Lucide Icons library for lightweight, vector-based interface elements.

Communication System (EmailJS)
The contact form utilizes a dual-relay logic to handle incoming inquiries.

Admin Notification: Alerts the site owner of a new submission, including sender details and message content.

Auto-Reply Receipt: Automatically transmits a confirmation to the sender to verify receipt of their data.

Configuration Requirements
To maintain security, the API keys and Template IDs in the source code have been replaced with placeholders. To enable the contact form, you must configure your own EmailJS environment.

1. Template Variables
Ensure your EmailJS templates are configured with the following variable keys:

{{from_name}}: The name of the sender.

{{reply_to}}: The sender's email address (used for the "Reply-To" header).

{{message}}: The body text of the inquiry.

{{date}}: Timestamp of the transmission.

2. Implementation
Replace the following placeholders in index.html and script.js:

JavaScript

/* index.html */
emailjs.init("YOUR_PUBLIC_KEY");

/* script.js */
const SERVICE_ID = "YOUR_SERVICE_ID";
const ADMIN_TEMPLATE_ID = "YOUR_ADMIN_TEMPLATE_ID";
const AUTO_REPLY_TEMPLATE_ID = "YOUR_AUTOREPLY_TEMPLATE_ID";
Security Protocols
Bot Mitigation
The form implements a Honeypot field. This hidden input is invisible to human users but is typically filled by automated spam bots. The JavaScript validation logic checks this field; if it contains any data, the submission is silently rejected to preserve the EmailJS monthly request quota.

Attribute-Based Selection
The JavaScript utilizes name-attribute selectors rather than index-based selection. This ensures the script remains stable even if additional HTML elements are added or the form structure is reorganized.

Deployment
This project is optimized for deployment via GitHub Pages.

Push the repository to GitHub.

Navigate to Settings > Pages.

Select the main branch as the deployment source.

Author
@carlxsx

Availability: Professional Inquiries Welcome
