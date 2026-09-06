# Enrico Roncuzzi

AI/ML Engineer · MSc Computer Science @ Politecnico di Milano

I build production LLM and ML systems: pipelines that keep a model's output structured, grounded, and honest instead of trusting it to behave.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/enricoroncuzzi/)

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white) ![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white) ![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black) ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![MLflow](https://img.shields.io/badge/MLflow-%230194E2.svg?style=for-the-badge&logo=mlflow&logoColor=white)

### [Unmasking Synthetic Images](https://github.com/enricoroncuzzi/unmasking-synthetic-images)

A detector that tells you an image is synthetic is only half the answer, the useful question is which generator made it, and most detection work doesn't touch that at all. My thesis builds a Mixture-of-Experts framework that does both: five specialized ResNet50 detectors feed a gating network, recovering 45 percentage points of cross-distribution accuracy (50% baseline to 94.1% balanced accuracy), with a 1K-parameter gate matching a 10.5M-parameter one on detection while uniquely solving attribution. The synthetic fingerprint it exploits lives sub-pixel, introduced by the VAE roundtrip every diffusion model performs, which is why it survives across generators. Backing it is a self-built, published 6,000-image forensic dataset spanning five Stable Diffusion variants from SD1.5 to FLUX. Shipped as a full stack: PyTorch Lightning, MLflow-tracked, served through FastAPI and Docker.

Try it: [Hugging Face Space demo](https://huggingface.co/spaces/enricoroncuzzi/unmasking-synthetic-images-demo)

### [jd-scraper](https://github.com/enricoroncuzzi/jd-scraper)

The hard part of using an LLM in a pipeline isn't getting it to respond, it's getting it to stop making things up. jd-scraper scrapes AI/ML postings daily across four region-scoped tiers (Italy full-remote, Switzerland and San Marino at any work mode, EU/EEA full-remote, and UK full-remote), runs each one through an LLM remote-eligibility verification stage on Groq before it ever reaches scoring, then scores fit with a second LLM on OpenRouter and stores the result in a growing Postgres corpus. Every LLM touchpoint in the pipeline, verification, scoring, CV tailoring, returns structured Pydantic output rather than parsed free text. The part I'd actually defend in an interview: the CV and cover letter it tailors per posting never let the model invent content, it selects and reorders verbatim bullets from a canonical CV and a runtime validation gate byte-checks the result against required claims before anything reaches a PDF, so hallucination is closed off in code, not hoped away by prompt wording.

### Also

[The FlanGELVS](https://github.com/enricoroncuzzi/The-FlanGELVS) (JUCE flanger plugin, real-time DSP in C++) and [CPAC22-Project](https://github.com/enricoroncuzzi/CPAC22-Project).
