# Short Response Questions

Answer each question below in your own words. Aim for 3–5 sentences per answer. Be specific — use the exact terms and concepts from the lesson.

Your responses will each be evaluated out of 6 points. You can earn 3 points for writing quality and 3 points for the accuracy and precision of the technical content per question.

---

## Question 1:

Why is it unsafe to make requests to a third-party API (like Giphy) directly from frontend JavaScript code? What specific risk does this create, and how can a malicious user exploit it?

**Your answer here**:

Making direct third-party API calls from frontend JavaScript exposes any API keys in your source code, which anyone can inspect through their browser.

Since an API key grants authenticated access, a malicious user can steal it and make requests on your behalf, exhausting your quota or running up costs charged to your account.

## Question 2:

What is the proxy server strategy? How does it help avoid exposing API Keys in client-side code while still providing access to APIs that require keys?

**Your answer here**:

The proxy server strategy routes API requests through your own backend instead of calling the third-party API directly from the frontend. The frontend calls your server, your server attaches the API key and forwards the request, then returns the response back to the client.

This keeps the API key safe because server-side code is never sent to the browser, only the response data is, meaning the key is never exposed to the client at any point.

## Question 3:

What is an environment variable, and why do we store API keys in a .env file instead of directly in source code? What role does .gitignore play in this setup, and what could go wrong if the .env file were accidentally committed to GitHub?

**Your answer here**:


An **environment variable** is a value stored outside of your source code, declared in a separate `.env` file, that your application reads at runtime.

We store API keys there instead of directly in code so the .env file can be added to `.gitignore`, which prevents it from ever being pushed to GitHub. This keeps sensitive values out of version control entirely.

If `.env` were accidentally committed, the API keys would be publicly visible to anyone browsing the repository, making them just as exposed as if they were hardcoded in the source.


