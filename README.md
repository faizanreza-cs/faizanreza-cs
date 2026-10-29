<div align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img src="assets/banner.svg" alt="Faizan Reza: AI engineer, LLM agents, document AI and applied machine learning" width="100%">
</picture>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-faizanreza-0A66C2)](https://www.linkedin.com/in/faizanreza)
[![X](https://img.shields.io/badge/@cs__faizan-000000?logo=x&logoColor=white)](https://x.com/cs_faizan)
[![Email](https://img.shields.io/badge/Email-faizanreza01%40gmail.com-EA4335?logo=gmail&logoColor=white)](mailto:faizanreza01@gmail.com)

</div>

I'm an AI engineer in Delhi. I build LLM agents, document pipelines and analytics, and I test
them on data where the right answer is known, so each README can report how often the method is
wrong.

My day job is at a top-10 global pharma company, where I'm an AI analyst: I assess AI use cases
from across the business and build the ones that go ahead. Two of mine: a Dataiku skill that lets
GitHub Copilot do routine Dataiku work, and an agent that writes project documentation. Before
that I worked on analytics for its US brands, from launch analysis to forecasting and dashboards,
and led the build of an LLM text-to-BI tool. Earlier I freelanced for remote clients. My own
projects also cover retail media, e-commerce and internal business tools, and most of the methods
aren't specific to any one industry.

**I take freelance projects** (US and European hours are fine): documenting and cleaning up
Dataiku projects, moving Alteryx workflows to Dataiku, and LLM agents that work on company data.
Email me at [faizanreza01@gmail.com](mailto:faizanreza01@gmail.com).

## Projects

<a href="https://github.com/faizanreza-cs/PDLwatch">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logos/pdlwatch-dark.svg">
  <img src="assets/logos/pdlwatch.svg" alt="PDLwatch" height="64">
</picture>
</a>

Document AI for drug coverage. Every state Medicaid program publishes a preferred drug list,
each in its own PDF layout, and market access teams need to know which brands are preferred,
which need prior authorization and what changed since last quarter. PDLwatch reads those PDFs
into one table, with the page each row came from.

It runs every morning on 28 public files from 14 states (56,014 rows). 58% of rows are accepted
automatically and the rest go to a review queue with a reason. In a random check of 60 accepted
rows the status was right in all 60. Earlier checks are how I found the layouts it misread: New
York's step therapy table was being read as part of the drug list, and Utah's two tables per
drug class as two separate lists. Both are fixed. Prior authorization criteria written as
sentences are still hard, so those rows always go to a person.

I also generated 106 synthetic PDFs for all 50 states and DC, where the right answer is known.
In the 26 states held out for testing, 2 of the 5,112 rows it accepted automatically were wrong:

<a href="https://github.com/faizanreza-cs/PDLwatch#what-it-found"><img src="assets/pdlwatch-where-rows-go.png" alt="Held-out test states: tables and lists are accepted automatically with no errors; prior authorization prose and damaged scans go to a reviewer" width="100%"></a>

<br>

<a href="https://github.com/faizanreza-cs/Retail-Media-Lab">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logos/retail-media-lab-dark.svg">
  <img src="assets/logos/retail-media-lab.svg" alt="Retail Media Lab" height="64">
</picture>
</a>

Amazon Ads measurement for a brand: what did the ads actually cause, and where should the next
dollar go? Real ad data can't be shared, so I simulated two years of advertising where the true
effect of every channel is known, and scored the standard methods against it. Click-based
attribution credited ads with 5,809 purchases when they caused 3,234, an overcount of 1.8x. A
geo holdout estimated the incremental ROAS of Amazon DSP at 2.03 (95% CI 1.87-2.19) against a
true 1.90. A marketing mix model fed a budget optimizer that found 1% more ad-driven sales at
the same spend.

<br>

<a href="https://github.com/faizanreza-cs/Pharma-MCP">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logos/pharma-mcp-dark.svg">
  <img src="assets/logos/pharma-mcp.svg" alt="Pharma MCP" height="64">
</picture>
</a>

An MCP server that gives any MCP client access to openFDA (drug labels, FAERS adverse event
reports, recalls) and ClinicalTrials.gov. The main tool is `signal_check`: give it a drug and a
reaction and it builds the 2×2 table from FAERS counts, then returns PRR and ROR with confidence
intervals and flags the pair using the Evans criteria. FAERS is voluntary reporting, so a flag
means "worth a closer look", not "the drug causes this", and the server tells the model to say so.

### More projects

- <img src="assets/marks/pharmapulse.svg" width="14" alt=""> **[PharmaPulse](https://github.com/faizanreza-cs/PharmaPulse)**:
  brand analytics with an LLM agent on top. Forecasting, market share, patient persistence and
  HCP targeting on a synthetic diabetes market; the agent answers by calling those functions as
  tools, so its numbers come from tested code.
- <img src="assets/marks/shelfsense.svg" width="14" alt=""> **[ShelfSense](https://github.com/faizanreza-cs/Shelfsense)**:
  recommendations and review analysis for an online supplements store. On 91,227 real Amazon
  reviews the hybrid recommender beat the best single model by 28%.
- <img src="assets/marks/ragdesk.svg" width="14" alt=""> **[RAGdesk](https://github.com/faizanreza-cs/Ragdesk)**:
  Q&A over company documents with a citation for each sentence. It says it doesn't know when
  retrieval comes up empty.
- <img src="assets/marks/docflow-agent.svg" width="14" alt=""> **[DocFlow Agent](https://github.com/faizanreza-cs/Docflow-agent)**:
  reads invoices, receipts and contracts into structured data, checks the totals, catches
  duplicate invoices and sends anything off to a review queue.
- <img src="assets/marks/agentkit-enterprise.svg" width="14" alt=""> **[AgentKit Enterprise](https://github.com/faizanreza-cs/agentkit-enterprise)**:
  guardrails for internal agents: tool permissions per role, human approval for risky actions,
  PII masking and a hash-chained audit log.

## Domain knowledge

Pharma commercial is where I know the data best:

| Data | Notes |
|---|---|
| **IQVIA Xponent, PlanTrak, NPA** | Prescriber-level TRx/NRx from Xponent, split by payer plan in PlanTrak; national trend and share from NPA |
| **IQVIA NSP** | Sales into each channel, in units and dollars |
| **IQVIA LAAD, APLD** | Patient-level claims. LAAD includes rejected and reversed claims, which is where abandonment shows up. APLD for journeys, switching and persistence |
| **IntegriChain 867, 852, subnational** | 867 is what wholesalers sold to pharmacies and hospitals, 852 is what they still hold; read together they separate real demand from stocking. Subnational puts those sales at outlet and territory level |
| **Chargebacks** | The difference between WAC and the contract price, claimed back by wholesalers; it shows contract sales by account |
| **GPO roster management** | Which hospitals, clinics and pharmacies belong to each group purchasing organization, and from when, so chargebacks and contract prices only go to eligible members |
| **Calls, samples, NPP** | Rep calls, sample drops and non-personal promotion, for reach, frequency and promotional response |

Outside pharma I've worked with ad platform data (Amazon Ads and AMC-style conversion paths),
e-commerce orders and reviews, and finance documents such as invoices and contracts.

## Tools

| | |
|---|---|
| **Languages** | Python, SQL |
| **LLMs** | Claude (Anthropic API), OpenAI, LangChain, MCP, RAG, evals |
| **Dataiku** | Dataiku DSS, Alteryx, GitHub Copilot skills |
| **Data and BI** | pandas, DuckDB, Snowflake, Power BI |
| **Apps** | FastAPI, Streamlit, Docker, GitHub Actions |
| **Stats and ML** | scikit-learn, statsmodels, lifelines, SciPy |
| **Documents** | pdfplumber, Tesseract OCR |
| **Methods** | Forecasting, recommenders, survival analysis, attribution, diff-in-diff and synthetic control, marketing mix models, signal detection (PRR, ROR) |
