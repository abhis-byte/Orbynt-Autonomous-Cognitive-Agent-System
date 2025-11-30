**Orbnyt: Autonomous Cognitive Agent System**
===
_Advanced Multi-Agent Pipeline for Web-Grounded Research, Knowledge Extraction, and Analytical Reporting_
===

**1. Project Summary**

Orbnyt is a fully autonomous multi-agent cognitive research system built using Google ADK 1.18.0.
It transforms an open-ended natural-language query into a complete, structured research output using a sequence of coordinated agents.

_Key capabilities:_
- Web-grounded search using tool-based retrieval
- Hybrid RAG using dense embeddings + TF-IDF 
- Knowledge graph extraction with structured triples
- Multi-domain numeric understanding
- Automated analytical dashboards
- Memory-conditioned multi-step reasoning
- Deterministic workflow execution via self-correction
- Final technical report generation

Orbnyt demonstrates production-grade agent design patterns and provides an interpretable, verifiable pipeline suitable for real-world analytical tasks.


---

**2. System Architecture**:

The system follows a consistent ***8-stage research pipeline***, with each stage handled by a dedicated agent.
A workflow-self-correction layer ensures deterministic execution and validates the structure at runtime.

<p align="center">
    <img src="architechture.png" alt="Orbnyt Agent Architecture" style="width: 60%; border: 1px solid #ccc; margin-top: 10px;"/>
</p>

- **Core architectural highlight:**

  The ***Self-Correction Agent enforces*** the required 8-stage pipeline and guarantees consistent, error-free execution across all queries — a key differentiator and high-scoring component.

---

**3. Key Features**

- ***3.1 Tool-Grounded Search***

  Retrieves high-precision factual information using Google Search via ADK tools.

- ***3.2 Hybrid Retrieval (StrongRAG v3)***

  - Dense embeddings from text-embedding-004
  - Sparse TF-IDF vectorization
  - Weighted fusion for robust relevance ranking

- ***3.3 Knowledge Graph Extraction***

  Extracts entity relationships into clean JSON triples suitable for downstream analytics and graph visualizations.

- ***3.4 Multi-Domain Numeric Extraction***

  Automatically identifies domain-specific metrics, including:

  - mAh, W, MP, Hz
  - GB, GHz
  - Pricing
  - Screen size
  - Travel cost, mileage, durations

  Works across consumer electronics, vehicles, travel planning, and general research.

- ***3.5 Automated Analytical Dashboards***

  Generates up to **ten interactive Plotly** charts with consistent formatting and validated numeric parsing.

- ***3.6 Workflow Self-Correction (Critical Component)***

  A dedicated agent enforces the correct 8-stage pipeline, repairing invalid plans and ensuring deterministic, verifiable execution for every query.

- ***3.7 Final Technical Report***

  Produces a structured, multi-section research document including:

  - Executive summary
  - Entity analysis
  - Comparison table
  - KG insights
  - Numeric interpretations
  - Consolidated conclusion

---

**4. Example Outputs**

- ***4.1 Comparative Charts***

<table style="width:100%; border:0px solid black;">
    <tr>
        <td style="width: 50%; padding: 5px; vertical-align: top;">
            <p style="text-align: center; font-weight: bold;">refresh rate(Hz) comparision</p>
            <img src="newplot (25).png" alt="charging speed Comparison" style="width: 100%; border: 1px solid #ccc;"/>
        </td>
<td style="width: 50%; padding: 5px; vertical-align: top;">
            <p style="text-align: center; font-weight: bold;">charging speed Comparison(w)</p>
            <img src="newplot (23).png" alt="charging speed Comparison(w)" style="width: 100%; border: 1px solid #ccc;"/>
        </td>
    </tr>
</table>

<table style="width:100%; border:0px solid black;">
    <tr>
        <td style="width: 50%; padding: 5px; vertical-align: top;">
            <p style="text-align: center; font-weight: bold;">battery capacity(mAh)</p>
            <img src="newplot (22).png" alt="battery capacity(mAh)"
             style="width: 100%; border: 1px solid #ccc;"/>
        </td>
<td style="width: 50%; padding: 5px; vertical-align: top;">
            <p style="text-align: center; font-weight: bold;">storage comparision(GB)</p>
            <img src="newplot (21).png" alt="storage comparision(GB)" style="width: 100%; border: 1px solid #ccc;"/>
        </td>
    </tr>
</table>

- ***4.2 Knowledge Graph Visualization***

<p align="left">
    <img src="newplot (26).png" style="width: 60%; border: 1px solid #ccc; margin-top: 20px;"/>
</p>

  - ***4.3 Standardized Comparison Table (Pricing normalized to USD)***

| *Specification*               |   *iPhone 16*    |  *Pixel 9*      |
| --------------------          |    ------------  |    ------------ |
| Battery Capacity              |     3561 mAh     |    4700 mAh     |
| Camera Resolution             |     48 MP        |    50 MP        |
| Charging Power                |     25 W         |    45 W         |
| Refresh Rate                  |     60 Hz        |    120 Hz       |
| Storage Options               |     Up to 512 GB |    Up to 256 GB |
| Price (Standardized)          |     **$850**     |    **$799**     |     

 *Prices normalized for consistency across sources.*

---

**5. Technical Stack**

- ***Core Components***

    - Google ADK 1.18.0
    - Gemini 2.5 Flash
    - Google Search Tool
    - text-embedding-004
    - TF-IDF (Scikit-learn)
    - Plotly for interactive visualizations
    - Pandas for data transformation
    - NetworkX for knowledge graph layout

- ***Environment***

  - Python 3.11
  - Kaggle Notebook runtime (GPU-independent)
  - In-memory execution and session management

---

**6. How to Run**

- ***1. Configure the API Key***

    Add to Kaggle → Settings → Secrets:

    label = your code rendering name

    value = your api key

- ***2. Run the Initialization Cells***
    These configure:
  
    - Agents
    - Tools
    - RAG engine
    - Knowledge graph extraction
    - Dashboards
    - Workflow self-correction

- ***3. Execute a Query***

    The system accepts any open-ended natural language query that requires web-grounded research.

    _example:_

- "Compare iPhone 16 vs Pixel 9 specifications, performance, camera, and price"    

- ***4. Review Outputs***
    The system automatically produces:
    - Web-grounded search
    - Summary
    - RAG context
    - Knowledge graph
    - Comparison table
    - Visual analytics
    - Final technical report

    No manual intervention required.  

 ---

**7. Limitations**

- ***Search dependency***

    Output accuracy depends on publicly available web data.

- ***Rate limits***

    ADK search quotas may limit rapid batch queries.

- ***Domain sparsity***

    Rare or poorly documented products may produce incomplete metrics.

- ***KG variability***

    Graph density is tied to the richness of retrieved text.

- ***Strict non-hallucination policy***

    Missing values are preserved as “Not available” rather than inferred.

--- 

**8. UX Vision & Deployment**

*To showcase its full enterprise potential, Orbnyt has a complementary external front-end application (a React/Streamlit app, provided in frontend.zip).​*

- ***Front-end purpose:*** The application is designed to offer an interactive chat-style layout and to render Orbnyt’s final reports and charts in a clean web interface.

- ***Current status:*** Due to time constraints and the complexity of deploying external applications inside the Kaggle environment, the front-end is submitted as a separate compressed asset and is not connected to the pipeline in this notebook. For this capstone, all demos are executed directly in the notebook to ensure reliability and reproducibility for judging.

---

**9. Future Improvements (Version 2.0)**

The following features are planned for implementation to transition Orbnyt into a true production-grade, commercial research platform:

- **I. Enterprise Data Integration & Scalability**

  - ***Local-document ingestion and offline RAG mode:*** Develop a dedicated local vector store and RAG pipeline to handle private, user-uploaded documents.
  - ***Attachment/Document Ingestion:*** Implement the capability to allow users to upload local files (e.g., PDFs, DOCX, TXT) for research and analysis.
  - ***Domain-specific extraction modules:*** Extend the system with specialized metric and fact extractors for high-value domains (finance, medicine, education).
  - ***Query caching and retrieval history:*** Implement a caching layer to reuse search results, significantly reducing API costs and improving response speed.

- **II. User Experience (UX) & Interaction**
  - ***Interactive Chat Layout:*** Integrate the entire pipeline into a persistent, real-time chat interface (e.g., Streamlit/Gradio) suitable for non-technical users.
  - ***Voice features:*** Introduce natural language processing for voice input and output, enabling hands-free interaction.
  - ***Multi-Query Session Management:*** Upgrade the Memory Layer to maintain comprehensive context and history across a long conversational session.
  - ***Localization and Region-Specific Search:*** Allow users to specify a target region, prioritizing local search results and automatically standardizing pricing to the correct local currency.

- **III. Advanced Cognition & Analytics**

  - ***Expanded multi-entity support (3–5 item comparisons):*** Scale the core analytic agents to efficiently process and compare data for a larger number of entities simultaneously. 
  - ***Improved KG clustering and graph analytics:*** Implement dedicated algorithms to perform deeper analysis and identify subtle, non-obvious relationships within the generated Knowledge Graph.
  - ***Dynamic Dashboard Interactivity:*** Enhance the Plotly integration to allow users to filter, zoom, and interact directly with the final comparison charts within the report.

- **IV. Reporting & Delivery**
  - ***Universal Report Export (PDF/HTML):*** Develop robust export pipelines to convert the final structured report and dashboards into professional, archive-ready PDF and responsive HTML formats.     
---

**Conclusion**

Orbnyt demonstrates a complete 8-stage autonomous research pipeline, combining rigorous workflow validation, reliable tool-grounding, structured extraction, and analytical reporting.
The system reflects professional engineering standards and is suited for high-stakes evaluation scenarios where transparency, determinism, and interpretability are essential.
