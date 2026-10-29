<div align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img src="assets/banner.svg" alt="Faizan Reza: AI engineer for pharma commercial and real-world evidence analytics" width="100%">
</picture>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-faizanreza-0A66C2)](https://www.linkedin.com/in/faizanreza)
[![X](https://img.shields.io/badge/@cs__faizan-000000?logo=x&logoColor=white)](https://x.com/cs_faizan)
[![Email](https://img.shields.io/badge/Email-faizanreza01%40gmail.com-EA4335?logo=gmail&logoColor=white)](mailto:faizanreza01@gmail.com)
![Delhi](https://img.shields.io/badge/Based_in-Delhi-6E7781)

</div>

I build AI systems for pharma commercial teams: market access, brand analytics and drug safety.
Each one is scored against a known answer before I trust it, cites where every number came
from, and sends what it isn't sure about to a person.

**Open to** AI engineering roles and collaborations in pharma commercial, market access and RWE
analytics.

## Featured work

<a href="https://github.com/faizanreza-cs/PDLwatch">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logos/pdlwatch-dark.svg">
  <img src="assets/logos/pdlwatch.svg" alt="PDLwatch" height="64">
</picture>
</a>

**State Medicaid preferred drug lists, read from PDFs and tracked over time.** A market access
team needs to know, for every brand and state, whether a drug is preferred, needs prior
authorization or step therapy, and what changed this quarter. Every state publishes that in its
own PDF layout. PDLwatch reads them all into one table, with a page citation and a confidence
score on every row.

- **Runs every morning on real state PDLs:** 28 files from 14 states, 56,014 rows. 58% are
  accepted automatically, and the status was right in all 60 accepted rows checked at random.
- **Scored on a 106-PDF test corpus** covering 50 states and DC, with a known answer: 82% of
  rows accepted automatically, 2 of 5,112 wrong (0.04%), and 95% of 260 quarterly changes found.
- Reads ruled tables, preferred / non-preferred lists, tiered formularies, prior authorization
  prose (LLM with structured output) and scanned pages (OCR).

<a href="https://github.com/faizanreza-cs/PDLwatch#what-it-found"><img src="assets/pdlwatch-where-rows-go.png" alt="Held-out test states: tables and lists are accepted automatically with no errors; prior authorization prose and damaged scans go to a reviewer" width="100%"></a>

<br>

<a href="https://github.com/faizanreza-cs/Pharma-MCP">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logos/pharma-mcp-dark.svg">
  <img src="assets/logos/pharma-mcp.svg" alt="Pharma MCP" height="64">
</picture>
</a>

**FDA drug labels, adverse event reports, recalls and ClinicalTrials.gov for any AI assistant,
plus pharmacovigilance signal detection.** Ask *"Is pancreatitis disproportionately reported
for semaglutide?"* and the assistant answers with sources linked back to the FDA.

- Six MCP tools over openFDA and ClinicalTrials.gov v2, plus a prompt that writes a one-page
  drug safety brief.
- `signal_check` computes PRR and ROR with 95% confidence intervals and a Yates χ² from FAERS
  counts, and flags a drug–reaction pair with the Evans criteria used in pharmacovigilance
  practice.
- Caches responses, retries with backoff and honours `Retry-After`. 21 offline tests, including
  the signal math checked against hand-computed values.

<br>

<a href="https://github.com/faizanreza-cs/PharmaPulse">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logos/pharmapulse-dark.svg">
  <img src="assets/logos/pharmapulse.svg" alt="PharmaPulse" height="64">
</picture>
</a>

**An AI analytics copilot for pharma brand teams.** It answers the questions a brand director
asks: *are we gaining share, what will TRx look like next quarter, why are patients dropping
off, which prescribers should reps call next?*

- An LLM agent with 12 tools calls the same tested analytics as the dashboard, so every figure
  in an answer comes from a tool, never from the model.
- Demand forecasts picked by holdout error (ETS: 3.1% mean WAPE over 13 weeks), Kaplan-Meier
  persistence, PDC adherence, HCP segmentation and promotional response.
- Model-written SQL is parsed and limited to one read-only `SELECT`. Runs on a synthetic US type
  2 diabetes market, so no real patient or sales data is used.

## More projects

- <img src="assets/marks/shelfsense.svg" width="14" alt=""> **[ShelfSense](https://github.com/faizanreza-cs/Shelfsense)**:
  recommendations, review sentiment by aspect, and drift monitoring for a consumer health store.
  In a simulated store it flagged a reformulated product the month it changed; on 91,227 real
  Amazon reviews the hybrid recommender beat the best single model by 28%.
- <img src="assets/marks/retail-media-lab.svg" width="14" alt=""> **[Retail Media Lab](https://github.com/faizanreza-cs/Retail-Media-Lab)**:
  Amazon Ads analytics scored against a simulator that knows the true effect of every channel.
  Click attribution over-credits ads 1.8x; a geo holdout estimates iROAS at 2.03 against a true
  1.90.
- <img src="assets/marks/ragdesk.svg" width="14" alt=""> **[RAGdesk](https://github.com/faizanreza-cs/Ragdesk)**:
  answers from company documents with a citation for every sentence, and "I don't know" instead
  of a guess. 95% retrieval hit@5 and answer accuracy on its 24-question eval.
- <img src="assets/marks/docflow-agent.svg" width="14" alt=""> **[DocFlow Agent](https://github.com/faizanreza-cs/Docflow-agent)**:
  invoices, receipts and contracts turned into validated data. Totals that don't add up and
  duplicate invoices go to a review queue instead of being exported.
- <img src="assets/marks/agentkit-enterprise.svg" width="14" alt=""> **[AgentKit Enterprise](https://github.com/faizanreza-cs/agentkit-enterprise)**:
  a starter kit for internal agents that security teams can sign off: role policies, human
  approvals, PII redaction and a tamper-evident audit log, checked by an eval of what actually ran.

## Pharma commercial data

The syndicated, channel and field data a US brand team runs on, and what I use each for:

| Area | Data | Used for |
|---|---|---|
| **Prescriptions** | IQVIA Xponent, Xponent PlanTrak, NPA | TRx/NRx and market share by prescriber, payer plan and nation |
| **Sales** | IQVIA NSP, IntegriChain subnational | National and territory sales, in units and dollars |
| **Patients** | IQVIA LAAD, APLD | Patient journeys, persistence, switching, claim rejections and abandonment |
| **Trade and channel** | IntegriChain 867 and 852, chargebacks | Distributor sell-through and inventory, contract sales by account |
| **Field** | Calls, samples, non-personal promotion (NPP), roster management | Rep reach and frequency, promotional response, territory alignment |

## How I build

- **Scored against the truth.** Real data rarely comes with an answer key, so I build a
  simulator or a test corpus that has one, and report how each method does against it.
- **Every number traced to its source.** Agents call tested analytics as tools; rows cite their
  document and page; answers cite their section.
- **A person where the model isn't sure.** Confidence scores with a named reason send uncertain
  rows, documents and high-risk actions to a reviewer or an approver.
- **Runs without an API key.** Rules or a mock model stand in for the LLM, so CI tests the whole
  pipeline. Anthropic and OpenAI are interchangeable when a key is set.
- **Shipped like a product.** CI, tests and a Dockerfile in every repo.

## Toolbox

| | |
|---|---|
| **Languages** | Python, SQL |
| **AI** | Claude (Anthropic API), OpenAI, LangChain, MCP, tool use, structured outputs, RAG, evals |
| **Data** | pandas, DuckDB, Snowflake, sqlglot, pyarrow |
| **Models** | scikit-learn, statsmodels, lifelines, SciPy |
| **Documents** | pdfplumber, pypdfium2, Tesseract OCR |
| **Apps and BI** | Power BI, Streamlit, FastAPI |
| **Shipping** | Docker, GitHub Actions |
| **Analytics** | Medicaid PDLs and formularies, prior authorization, FAERS signal detection, TRx/NRx share, persistence and adherence, HCP targeting, marketing mix models, geo incrementality |
