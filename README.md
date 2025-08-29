# Please credit Mohammad Ahsan Hummayoun when using, sharing, or adapting this workflow

This n8n workflow automates the creation of a professional LinkedIn post to promote a new YouTube video.  
It solves the problem of manually drafting social media content for every video upload, which saves time and ensures a consistent content pipeline.

The workflow is triggered when a new video is published on your YouTube channel.  
It fetches key video details, passes them to a Large Language Model (LLM) to generate an engaging LinkedIn post, and then automatically publishes the post.  
It also includes error handling and notification features to keep you informed.

# ⚙️ How it Works

**Trigger on New Video**  
The workflow is initiated by an RSS Feed Trigger that monitors your YouTube channel for new video uploads.

**Merge Data**  
Video details from the trigger are combined with other necessary information using a Merge node, ensuring the LLM has all the context it needs.

**LLM Chain**  
The core of the workflow is the Basic LLM Chain node. It takes the video details and prompts the LLM to generate a compelling LinkedIn post draft.  
The workflow uses two separate LLM models (Model1 and Model2) to potentially compare outputs or provide fallbacks.

**Publishing**  
The generated post is sent to a LinkedIn "Create a Post" node to be published to your account.

**Notifications & Error Handling**  
The workflow includes logic to send a notification message via email (e.g., using a Gmail node) upon completion or in case of an error.  
This ensures you are alerted to any issues, such as a failed post or a problem with the LLM request.

# 🚀 Setup and Requirements

**YouTube Credentials**  
An n8n credential for YouTube to allow the RSS Feed Trigger to monitor your channel.

**LinkedIn Credentials**  
An n8n credential for LinkedIn to permit the workflow to publish posts.

**LLM API Key**  
A credential for your chosen Large Language Model provider (e.g., Groq Cloud, OpenAI, or other providers used in the workflow).

**Email Credentials (Optional)**  
If you're using the notification feature, an n8n credential for your email service (e.g., Gmail).

These API keys and credentials are to be configured directly within their respective n8n nodes for security.
