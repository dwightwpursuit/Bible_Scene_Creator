📖 Bible Story Scene Creator ✨
Visualize scripture like never before! The Bible Story Scene Creator is a web application that allows users to generate unique AI-powered visual interpretations of Bible verses, perfect for Sunday School teachers, content creators, and anyone looking for a fresh perspective on scripture.

About This Project
This project provides an interactive tool to:

Look Up Bible Verses: Easily retrieve full verse text from a specified book, chapter, and optional verse range.

Generate AI Scenes: Transform Bible verse text into custom visual scenes using a powerful text-to-image AI model, with various artistic styles to choose from.

Save & Manage Favorites: Store your favorite generated scenes (including the verse, image, and style) directly within the app for quick future reference. Saved scenes persist even after closing the browser.

Download Images: Save your generated scenes as image files to your device.

View Verse Online: Instantly open the looked-up verse on an external online Bible website (BibleGateway.com) for additional context or translations.

User-Friendly Interface: A clean, responsive design built with Tailwind CSS for an intuitive experience.

How It Works
The application operates through a seamless workflow powered by external APIs:

Verse Retrieval:

When a user inputs a Bible reference (Book, Chapter, Verse) and clicks "Look Up Verse," the app constructs a query.

This query is sent to the bible-api.com (a public API for Bible text retrieval).

The returned verse text is then displayed in the application.

Image Generation (AI Magic):

After a verse is retrieved, the user can select an optional artistic style (e.g., "oil painting," "realistic photography").

The app combines the verse text and the chosen style into a detailed prompt.

This prompt is then sent to Google's imagen-3.0-generate-002 API (part of the Generative Language API) for text-to-image generation.

Upon successful generation, the AI returns a base64-encoded image, which the app displays to the user.

Data Persistence:

Users can click "Save to Favorites" after generating an image.

The application stores a record for each saved scene (which includes the verse reference, full text, image data URL, style, and timestamp) in the browser's localStorage. This ensures that saved scenes are retained even if the user closes the browser tab or restarts their computer.

How to Run It
You can run this project in two ways: via a live demo on GitHub Pages, or by setting it up locally for development.

🚀 Live Demo (Recommended for Users)
The easiest way to experience the Bible Story Scene Creator is through its live deployment on GitHub Pages:

Visit the live app: https://dwightwpursuit.github.io/Bible-Scene-Creator/ (Replace dwightwpursuit with your actual GitHub username if you're using your own fork/repo).

Enter a Book (e.g., John), Chapter (e.g., 3), and optionally Verse(s) (e.g., 16).

Click "Look Up Verse."

(Optional) Select a Style from the dropdown.

Click "Generate Image."

Once the image appears, you can "Download Image" or "Save to Favorites."

Explore your saved scenes below!

💻 Local Development Setup (for Developers)
To run and modify the project on your local machine:

Clone the Repository:

git clone https://github.com/dwightwpursuit/Bible-Scene-Creator.git
cd Bible-Scene-Creator

(Replace dwightwpursuit with your GitHub username if necessary.)

Open in Your Code Editor:
Open the Bible-Scene-Creator folder in your preferred code editor (e.g., Cursor, VS Code).

Obtain Google Cloud API Key (Crucial):
The image generation feature requires a Google Cloud API Key for the Generative Language API (which provides access to imagen-3.0-generate-002).

Go to Google Cloud Console.

Create a new project or select an existing one.

Go to APIs & Services > Library, search for Generative Language API, and ENABLE it for your project.

Go to APIs & Services > Credentials, click + CREATE CREDENTIALS > API Key.

RESTRICT YOUR API KEY (HIGHLY RECOMMENDED):

Click "Restrict Key" on your new API key.

Under "Application restrictions," select "HTTP referrers (web sites)."

Under "Website restrictions," add your development URL(s). If you plan to run it from file:// (directly opening index.html), you might need to leave this unrestricted during development, but this is less secure. For your GitHub Pages deployment, ensure https://yourgithubusername.github.io/* is added here.

Under "API restrictions," select "Restrict key" and choose "Generative Language API."

Save your restrictions.

Enable Billing: Go to Billing in the Google Cloud Console and ensure billing is enabled for your project. (You may have free credits.)

Insert API Key into index.html:

Open index.html in your code editor.

Locate the callImagenAPI function.

Replace "YOUR_ACTUAL_GOOGLE_CLOUD_API_KEY_HERE" with the API key you copied from Google Cloud Console:

const apiKey = "YOUR_ACTUAL_GOOGLE_CLOUD_API_KEY_HERE"; // PASTE YOUR KEY HERE

Run the Application:

Option A (Simplest, may encounter CORS locally):
Simply open the index.html file directly in your web browser (e.g., file:///path/to/your/Bible-Scene-Creator/index.html).

Note: Running from file:// protocol can sometimes cause CORS (Cross-Origin Resource Sharing) issues with bible-api.com or other APIs, as browsers restrict requests from local files. If you encounter "Failed to fetch" errors for the Bible API locally, this is the reason. It will work correctly on GitHub Pages.

Option B (Recommended for Local Dev):
Use a simple local web server. For example, with Python installed:

python -m http.server 8000

Then, open your browser to http://localhost:8000/index.html. This will often resolve local CORS issues.

Now you have a comprehensive README.md file that explains your project, how it works, and how others can run it.