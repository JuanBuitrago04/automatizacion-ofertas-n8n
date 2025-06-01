# Job Offer Automation with n8n

This project automates the searching and notification of relevant job offers in the tech field, using the low-code automation tool n8n. Every day at 8:00 AM, the workflow searches for offers with specific keywords (JavaScript, Node.js, and Full Stack) and sends a summary directly to your email.

## 🚀 Features

* **Daily Search:** Automatically executes a job offer search every morning at 8:00 AM.
* **Customizable Keywords:** Configured to search for offers related to 'JavaScript', 'Node.js', and 'Full Stack'. Easily adaptable for other keywords.
* **Email Notifications:** Sends an email with a list of the found job offers.
* **RemotOK Integration:** Utilizes the RemotOK API to retrieve job offers.
* **Data Processing:** Formats and groups offers for better display in the email.

## 🛠️ Technologies Used

* **n8n:** A low-code workflow automation tool, used to build and execute the process.
* **RemotOK API:** For obtaining job offer data.
* **Gmail:** For sending email notifications.

## ⚙️ Workflow Diagram

The n8n workflow follows these steps:

1.  **Schedule Trigger:** Automatically activates every day at 8:00 AM.
2.  **HTTP Request:** Makes a GET request to the RemotOK API (`https://remotok.io/api`) to fetch job offers.
3.  **Code (Initial Processing):** A code node processes the API response, filtering offers based on the defined keywords.
4.  **GroupOfOffers (Grouping):** Another code or function node can group or format the offers for the email.
5.  **Gmail:** Sends an email with the summary of found offers.

![N8n Workflow Diagram](image_d88e12.png)
*(It is recommended to replace `image_d88e12.png` with the actual path to your image in the repository)*

## 📝 Setup and Usage

To set up and use this project in your own n8n instance, follow these steps:

1.  **Install n8n:** If you don't have it yet, install n8n by following the instructions in the [official n8n documentation](https://docs.n8n.io/getting-started/installation/).
2.  **Import the Workflow:**
    * Download the JSON file of your n8n workflow.
    * In your n8n instance, go to "Workflows" and click "New Workflow" or "Import from JSON".
    * Paste the JSON content of your workflow.
3.  **Configure Credentials:**
    * **Gmail:** You will need to set up a Gmail credential in n8n to allow the workflow to send emails. Follow n8n's instructions to configure [Gmail credentials](https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.gmail/).
    * **RemotOK API:** Currently, the RemotOK API is publicly accessible for basic reading, so it does not require an API key, but it's always good to check their documentation for any changes.
4.  **Customize Keywords:**
    * Inside the "Code" node or an earlier node that performs filtering, locate and modify the keywords (`JavaScript`, `Node.js`, `Full Stack`) according to your preferences.
5.  **Activate the Workflow:** Ensure the workflow is "Active" so that the "Schedule Trigger" runs automatically at 8:00 AM.
6.  **Set Destination Email:** In the Gmail node, make sure the "To" field is configured with the email address where you want to receive notifications.

## 🤝 Contributions

If you have ideas to improve this workflow, feel free to propose them! You can open an "Issue" or submit a "Pull Request" with your suggestions.
