# SMU Hackathon Prep: AI Workshop & Track Coaching Notebooks

Hands-on Google Colab notebooks for hackathon participants. Start with the core RAG workshop, then join the coaching session for your track. Every notebook builds a working prototype with a Gradio web UI that you can demo to judges.

## Notebooks

Each track notebook answers that track's sponsor problem statement from the Singapore-India Hackathon 2026 Industry Track brief.

| Session | Sponsor | Notebook | You will build | Key techniques |
|---|---|---|---|---|
| Core workshop | | [workshop.ipynb](workshop.ipynb) | **TechGadget support bot**: a customer-service chatbot that answers from a company policy document | RAG, embeddings, ChromaDB vector search |
| Track 1 · Emerging Technology | Singtel | [track1_emerging_tech_accountscout.ipynb](track1_emerging_tech_accountscout.ipynb) | **AccountScout**: a sales-intelligence agent that finds buying signals, scores opportunities and recommends the next action, for existing accounts (farming) and new prospects in India (hunting) | Structured output with citation checks, function calling (agents), transparent scoring, human-in-the-loop |
| Track 2 · Social Innovation | raiSE | [track2_social_innovation_silverpurpose.ipynb](track2_social_innovation_silverpurpose.ipynb) | **SilverPurpose**: seniors in Singapore and India describe themselves in any language and are matched to meaningful ways to contribute, run as a self-sustaining social enterprise | Multilingual structured extraction, explainable matching, cross-lingual search, pilot validation, social-enterprise unit economics |
| Track 3 · Fintech / InsurTech | Income Insurance | [track3_fintech_weathershield.ipynb](track3_fintech_weathershield.ipynb) | **WeatherShield**: parametric heat, rain and haze income cover for outdoor workers, hawkers and renters, back-tested, priced and explained in one SMS | pandas back-testing, pricing and unit economics, multilingual SMS with say-back test (LLM-as-judge), insurable-interest check |
| Track 4 · Sustainability | METI | [track4_sustainability_agrilink.ipynb](track4_sustainability_agrilink.ipynb) | **AgriLink**: helps an Indian farmer producer organisation meet a Singapore buyer's quality and supply requirements | Vectorless tree-index RAG over standards, photo grading (multimodal), weather-driven supply planning, Hindi/English advisories |

Each track notebook is a **~60-minute coaching session** and ends with:
- 🤔 discussion questions for the coach,
- 🎯 what the sponsor wants after 36 hours, with a template to fill in,
- ✅ a checklist of the sponsor's constraints,
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

- **Gemini API** via the `google-genai` SDK (model `gemini-3.5-flash-lite`, set in one `MODEL` constant per notebook)
- **ChromaDB 1.5.9**: vector database (core workshop)
- **Optional live data** (no key needed, with a built-in fallback): data.gov.sg weather and haze feeds (Track 3), Open-Meteo forecasts (Track 4)
- **Gradio 6.29.1**: web UI
- **pandas, scikit-learn, matplotlib, Pillow, pydantic**: already installed in Colab

The install cell keeps Colab's own versions of `google-auth` and `opentelemetry` so it doesn't break the Colab environment.

## Tips for the Day

- **Rate limits:** the free tier allows only a few requests per minute. The notebooks retry automatically on `429` errors, but avoid re-running cells in a tight loop, and keep a spare API key ready.
- **Restart cleanly:** if packages get into a bad state, use **Runtime ▸ Disconnect and delete runtime**, then run again from the top.
- **Pick one extension:** a polished demo of one idea beats a half-working demo of five.

## Data & Responsible Use

- All companies, people, customer records, weather histories, standards documents and pilot results in these notebooks are **fictional or synthetic**. Sponsors and public bodies (Singtel, raiSE, Income, METI, NEA, SFA, APEDA) are named only as context.
- **Never use real personal, medical or bank data** with the free Gemini tier, which may use inputs to improve Google's products.
- If your project uses real public information (e.g. government schemes), take it from official sources and show the source in your app.

## For Organisers

Before sharing:
- Run each notebook once in a fresh Colab runtime with a real API key to confirm the model outputs.
