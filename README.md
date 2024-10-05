# AutoMailPDF2Wordpress

**AutoMailPDF2Wordpress** is a Python script that automates the process of checking your Gmail inbox for specific emails containing PDF attachments and then posts those PDFs directly to your WordPress website.

## Features

- Periodically checks your Gmail inbox for emails from a specific sender.
- Downloads PDF attachments from the emails.
- Automatically posts the downloaded PDFs to a WordPress website.
- Can be configured to run as a background task.

## Prerequisites

Before using the script, ensure you have the following:

1. **Python 3.x**
2. Required Python packages (see installation section).
3. A **Gmail API** setup with OAuth credentials.
4. A **WordPress** site with REST API enabled and authentication details (username, password, application password, or token).

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/GmailToWordpressPDF.git
    cd GmailToWordpressPDF
    ```

2. Install the required Python packages:

    ```bash
    pip install -r requirements.txt
    ```

3. Set up Gmail API credentials:
   - Go to the [Gmail API](https://developers.google.com/gmail/api) and follow the instructions to enable the API and download `credentials.json`.
   - Place `credentials.json` in the root directory of the project.

4. Configure WordPress credentials:
   - Set up WordPress REST API access, and ensure you have a user with appropriate permissions to upload media.
   - Add your WordPress credentials and the API endpoint to the script.

## Usage

1. **Gmail Configuration:**
   - Modify the script to specify the email address of the sender you want to monitor.
   
   ```python
   SENDER_EMAIL = "sender@example.com"  # Email address you want to monitor
   ```

2. **WordPress Configuration:**
   - Specify your WordPress site's URL, along with authentication details:
   
   ```python
   WORDPRESS_URL = "https://your-wordpress-site.com/wp-json/wp/v2/media"
   WORDPRESS_USER = "your_username"
   WORDPRESS_PASSWORD = "your_application_password"
   ```

3. **Running the Script:**
   - To run the script and continuously check for new emails, simply run:
   
   ```bash
   python gmail_to_wordpress.py
   ```

   The script will periodically check your Gmail inbox, download PDF attachments from specific emails, and upload them to your WordPress site.

## Customization

- **Email Sender Filter:** You can change the email address filter in the script to monitor different email addresses.
- **Check Interval:** The default check interval can be modified to check your Gmail inbox more or less frequently.

## Contributing

If you’d like to contribute to this project, feel free to submit a pull request or open an issue to discuss new features, bug fixes, or improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgments

- This script utilizes the [Gmail API](https://developers.google.com/gmail/api) for email handling.
- The [WordPress REST API](https://developer.wordpress.org/rest-api/) is used for posting PDFs to your site.
