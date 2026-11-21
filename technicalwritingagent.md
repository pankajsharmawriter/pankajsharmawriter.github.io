---
title: Create a technical writing AI agent on Hugging Face without coding
layout: default
---

# Create a technical writing AI agent on Hugging Face without coding

This article shows you how to build and publish a technical writing AI agent on Hugging Face Spaces. You don't need to write code. You copy a ready-made file, add your API key, and test the agent in your browser.

The agent answers questions about technical writing, such as documentation formats, tools, style guides, and career advice. To see a working example, go to [TechnicalWritingAgent](https://huggingface.co/spaces/pankajsharmawriter/TechnicalWritingAgent).

## Prerequisites

Before you begin, make sure you have:

- A [Hugging Face](https://huggingface.co) account.
- A [GroqCloud](https://console.groq.com) account.
- A web browser.

> [!NOTE]
> Hugging Face documentation states that creating a Gradio Space requires a paid plan for personal accounts, with limited exceptions. Check your account's plan before you start.

## Step 1: Get your API key

An API key lets your agent send questions to a language model hosted by Groq.

1. Sign in to the [GroqCloud console](https://console.groq.com).
1. In the top navigation, select **API Keys**.
1. Select **Create API Key**.
1. Enter a display name, such as `technical-writing-agent`, and then select **Submit**.
1. Select **Copy** to copy the key. The key starts with `gsk_`.

> [!IMPORTANT]
> GroqCloud shows the key only once. Save it in a password manager before you close the dialog box. Don't share the key or paste it into your app file.

## Step 2: Create a Space on Hugging Face

A Space is a web app that Hugging Face hosts for you.

1. Sign in to [Hugging Face](https://huggingface.co).
1. Go to the **Spaces** page, and then select **Create new Space**.
1. For **Space name**, enter `TechnicalWritingAgent`.
1. For **Space SDK**, select **Gradio**.
1. For **Visibility**, select **Public**.
1. Select **Create Space**.

Hugging Face creates the Space with a starter `README.md` file.

## Step 3: Add your API key as a secret

A secret stores your API key outside your code, so no one else can read it.

1. In your Space, select **Settings**.
1. Go to the **Variables and secrets** section, and then select **New secret**.
1. For **Name**, enter `GROQ_API_KEY`.
1. For **Value**, paste the key that you copied in Step 1.
1. Select **Save**.

> [!NOTE]
> Hugging Face restarts your Space whenever you change a secret.

## Step 4: Add the app file

The `app.py` file defines what your agent does. You edit only this file.

1. In your Space, select the **Files** tab.
1. Select **Add file**, and then select **Create a new file**.
1. For the file name, enter `app.py`.
1. Paste the following content into the editor:

    ```python
    import os

    import gradio as gr
    import httpx

    API_URL = "https://api.groq.com/openai/v1/chat/completions"
    API_KEY = os.environ["GROQ_API_KEY"]
    MODEL = "<model-id>"

    SYSTEM_PROMPT = (
        "You are a technical writing assistant. Answer questions about "
        "documentation formats, tools, style guides, and technical writing "
        "careers. Give clear, step-by-step answers."
    )


    def ask(question):
        response = httpx.post(
            API_URL,
            headers={"Authorization": f"Bearer {API_KEY}"},
            json={
                "model": MODEL,
                "messages": [
                    {"role": "system", "content": SYSTEM_PROMPT},
                    {"role": "user", "content": question},
                ],
            },
            timeout=60,
        )
        response.raise_for_status()
        return response.json()["choices"][0]["message"]["content"]


    demo = gr.Interface(
        fn=ask,
        inputs=gr.Textbox(label="Your question", lines=3),
        outputs=gr.Textbox(label="Answer"),
        title="Technical Writing Agent",
        description="Ask any question about technical writing.",
    )

    demo.launch()
    ```

1. Replace `<model-id>` with the ID of a current model from the Models page in the GroqCloud documentation.
1. To change how the agent behaves, edit the text in `SYSTEM_PROMPT`.
1. Select **Commit new file to main**.

## Step 5: Build and launch the Space

Each time you commit a change, Hugging Face rebuilds and restarts your Space automatically.

1. Select the **App** tab.
1. To follow the build, select **Logs** in the Space header.
1. Wait until the status badge next to your Space name changes to **Running**.

## Step 6: Test your agent

1. In the **Your question** box, enter a question, such as `What is the difference between a user guide and a quick start guide?`.
1. Select **Submit**.
1. Check that the answer appears in the **Answer** box.
1. Try questions about documentation formats, tools, style guides, and career advice.

To share your agent, copy the URL of your Space and add it to your portfolio.

## Conclusion

You now have a technical writing AI agent that runs on Hugging Face Spaces. You created it with a Groq API key, one secret, and one app file, and you didn't write any code. Because the agent's behavior comes from the system prompt, you can adapt it to any documentation topic by editing a few lines of text. Use the same steps to build other agents for your portfolio and your day-to-day work.

For any query, contact me at **pankajsharmawriter@gmail.com**.

## Reference

-  [About me](./)