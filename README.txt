Nova PDF Maker Bot
A Telegram bot that converts photos and text into PDF files with watermarking, supports Arabic/Persian text, and includes an admin panel for managing user data and PDFs.
Features

Photo to PDF: Convert multiple photos into a single PDF with a watermark.
Text to PDF: Convert text (including Arabic/Persian) into a PDF with proper RTL support.
Admin Panel: View user stats, retrieve user PDFs, and clear all data (protected by a password).
Database Storage: Tracks user activity and stores PDF paths using SQLite.
Watermarking: Adds a custom watermark to all generated PDFs.
Temporary File Management: Automatically cleans up temporary files after conversion.

Prerequisites

Python 3.8+
A Telegram bot token from BotFather
The Vazirmatn-Regular.ttf font file for Arabic/Persian text support (not included in this repository)

Installation




Install dependencies:
pip install -r requirements.txt


Add the Vazir font:

Download the Vazirmatn-Regular.ttf font file from Vazirmatn GitHub or another trusted source.
Place the font file in the project root directory.


Set up the Telegram bot token:

Replace the bot token in the main() function of novapdfmaker.py with your own:application = Application.builder().token("YOUR_BOT_TOKEN_HERE").build()




Run the bot:
python novapdfmaker.py



Dependencies
The following Python packages are required:
python-telegram-bot==20.7
Pillow==10.0.0
img2pdf==0.4.4
FPDF==1.7.2
arabic-reshaper==3.0.0
python-bidi==0.4.2
reportlab==4.0.4
PyPDF2==3.0.1

Install them using:
pip install python-telegram-bot Pillow img2pdf FPDF arabic-reshaper python-bidi reportlab PyPDF2

Usage

Start the bot by sending /start in Telegram.
Choose an option:
Convert Photos to PDF: Send photos one by one, then type done to generate the PDF.
Convert Text to PDF: Send the text you want to convert.


Provide a filename for the PDF when prompted.
Receive the generated PDF with a watermark.
Admin Access:
Send the admin password (default: walter05) to access the admin panel.
Options include viewing user stats, retrieving user PDFs, or clearing all data.



Project Structure
nova-pdf-maker-bot/
├── novapdfmaker.py         # Main bot script
├── temp_files/             # Temporary directory for storing photos and PDFs
├── user_data.db            # SQLite database (created automatically)
├── Vazirmatn-Regular.ttf   # Font file for Arabic/Persian text (must be added manually)
├── README.md               # This file
└── requirements.txt        # List of dependencies

Database
The bot uses an SQLite database (user_data.db) to store:

User information (user ID, username, PDF count)
PDF paths linked to users

The database is automatically set up when the bot starts.
Notes

The temp_files directory is used for temporary storage and is automatically created.
Ensure the Vazirmatn-Regular.ttf font file is present in the project root for proper Arabic/Persian text rendering.
The admin password is hardcoded as walter05. For production, consider using environment variables for security.
The bot handles timeouts and errors gracefully, but ensure a stable internet connection for file uploads.

Contributing
Contributions are welcome! Please:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature).
Commit your changes (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For issues or suggestions, open an issue on GitHub or contact the repository owner.
