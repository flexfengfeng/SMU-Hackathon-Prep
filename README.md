# SMU Hackathon Prep: AI Workshop & Track Coaching Notebooks

Hands-on Google Colab notebooks for hackathon participants. Start with the core RAG workshop, then join the coaching session for your track. Every notebook builds a working prototype with a Gradio web UI that you can demo to judges.

## Notebooks

| Session | Notebook | You will build | Key techniques |
|---|---|---|---|
| Core workshop | [workshop.ipynb](workshop.ipynb) | **TechGadget support bot**: a customer-service chatbot that answers from a company policy document | RAG, embeddings, ChromaDB vector search |
| Track 1 · Emerging Technology | [track1_emerging_tech_fixit_agent.ipynb](track1_emerging_tech_fixit_agent.ipynb) | **FixIt**: a photo and message about a building fault are triaged, then an AI agent checks asset history, spare parts and technicians, and raises a work order | Multimodal input, structured output, function calling (agents), human-in-the-loop |
| Track 2 · Social Innovation | [track2_social_innovation_carecompass.ipynb](track2_social_innovation_carecompass.ipynb) | **CareCompass**: people describe their situation in any language and find out which support schemes they may qualify for, and why | Structured extraction, a transparent rule engine, cross-lingual RAG, plain-language replies |
| Track 3 · Fintech | [track3_fintech_moneymate.ipynb](track3_fintech_moneymate.ipynb) | **MoneyMate**: spending categorised, fraud detected and explained, and a chat money coach | Batch LLM calls, Isolation Forest and rules, LLM explanations, "pandas calculates, LLM narrates" |
| Track 4 · Sustainability | [track4_sustainability_greenlens.ipynb](track4_sustainability_greenlens.ipynb) | **GreenLens**: an ESG report analyst that checks headline claims against the report's own data | Vectorless tree-index RAG (PageIndex-style), data extraction with validation, LLM-as-judge with evidence |

Each track notebook is a **~60-minute coaching session** and ends with:
- 🤔 discussion questions for the coach,
- 🚀 extension ideas to make the project your own,
- 🎤 tips for pitching to judges, and
- 🛡️ a responsible-AI checklist.

## Getting Started

1. **Open a notebook in Colab.** Click the "Open in Colab" badge at the top of the notebook, or go to [colab.research.google.com](https://colab.research.google.com) and choose **File ▸ Upload notebook**.
2. **Get a free Gemini API key** from [Google AI Studio](https://aistudio.google.com/) by clicking **Get API key**.
3. **Add the key to Colab.** Open the 🔑 **Secrets** panel on the left, add a secret named `GEMINI_API_KEY`, and turn on **Notebook access**.
4. **Run the cells from top to bottom.** If Colab asks you to restart the session after Step 1, restart and continue from Step 2.
5. **Launch the demo.** The last cell starts a Gradio app with a public `*.gradio.live` link that you can share with your team and the judges.

## Tech Stack

- **Gemini API** via the `google-genai` SDK (model `gemini-2.5-flash`, set in one `MODEL` constant per notebook)
- **ChromaDB 1.5.9**: vector database (core workshop and Track 2)
- **Gradio 6.29.1**: web UI
- **pandas, scikit-learn, matplotlib, Pillow, pydantic**: already installed in Colab

The install cell keeps Colab's own versions of `google-auth` and `opentelemetry` so it doesn't break the Colab environment.

## Tips for the Day

- **Rate limits:** the free tier allows only a few requests per minute. The notebooks retry automatically on `429` errors, but avoid re-running cells in a tight loop, and keep a spare API key ready.
- **Restart cleanly:** if packages get into a bad state, use **Runtime ▸ Disconnect and delete runtime**, then run again from the top.
- **Pick one extension:** a polished demo of one idea beats a half-working demo of five.

## Data & Responsible Use

- All companies, schemes, transactions and reports in these notebooks are **fictional or synthetic**.
- **Never use real personal, medical or bank data** with the free Gemini tier, which may use inputs to improve Google's products.
- If your project uses real public information (e.g. government schemes), take it from official sources and show the source in your app.

## For Organisers

Before sharing:
- Replace `YOUR_GITHUB_USER/YOUR_REPO` in each notebook's Colab badge with the real repository path.
- Run each notebook once in a fresh Colab runtime with a real API key to confirm the model outputs.
