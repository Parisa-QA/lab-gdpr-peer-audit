**PHASE 3**

**Clarifying Questions- ASYNC Debrief**  

**Important Note: The peer's GDPR asuding done with eu ai act together. I copied that file here and kept only GDPR section.**  

Independent peer audit — Previously On: Love Is Blind

| Project owner | Louise Plessis |
| :---- | :---- |
| **Information requested** | 19 August 2026 |
| **Response status** | Awaiting written response |
| **Audit treatment** | Provisional assumptions apply until written evidence is received. |

**GDPR**

## **Question 1**

| Exactly which personal-data fields from YouTube comments, public web sources, contestants, and user inputs enter the pipeline, and are identifiers or sensitive inferences removed before processing? |
| :---- |
| **Why it matters:** A precise data inventory is required for purpose limitation, data minimisation and assessing whether identifiable or potentially special-category data is processed. |
| **Provisional assumption:** Comment and web text may contain personal data, while recaps discuss identifiable contestants and relationships; no complete field-level inventory or documented pre-processing control has been provided. |

### **Written response**

| *Response:  The pipeline processes four main categories of potentially personal data: YouTube comments: comment text used for fan-reaction analysis. The content can contain opinions about identifiable contestants and may occasionally include personal or sensitive claims made by commenters. I do not intentionally need usernames or other commenter identifiers for the analysis; the useful input is the comment text itself. Public web sources: recap/review text, episode information and other publicly available content discussing identifiable Love Is Blind contestants, their actions, relationships and events shown in the programme. Contestant information: names and information about contestants derived from the programme and public sources. Because the product reconstructs storylines and relationships, this can include personal information and potentially sensitive claims contained in source material. User input: primarily the selected show/season and episode cutoff plus the user's query/request. The product does not require users to provide personal information about themselves. Updated conclusion: The pipeline primarily requires content rather than source-user identity, which limits the need for commenter identifiers. However, identifiable contestant information is intrinsic to the product, and no systematic pre-processing control currently removes identifiers or potentially sensitive information contained in free-text sources before processing.*  |  |
| :---- | :---- |
| *Evidence supplied / link:*  |  |
| **Response date** | 19/08/26 |
| **Effect on audit** | *No change / Finding updated / Classification updated* |

**GDPR**

## **Question 2**

| What data is sent to OpenAI, Pinecone, Tavily, YouTube or other vendors; where is it hosted; and what lawful basis, processor terms and international-transfer safeguards apply? |
| :---- |
| **Why it matters:** This establishes the controller/processor map and determines whether processing and transfers outside the EEA have an appropriate legal basis and contractual safeguards. |
| **Provisional assumption:** Source text is sent to OpenAI and selected chunks and metadata are stored in Pinecone us-east-1; the complete vendor map, DPAs, lawful-basis assessment and transfer safeguards are not documented. |

### **Written response**

| *Response: The pipeline uses several external vendors, but they receive different data: YouTube Data API: receives the video/channel identifiers and API query parameters needed to retrieve public comments and metadata. The project then processes returned public comment text for fan-reaction analysis. YouTube's API terms require API clients to comply with privacy laws and maintain a privacy policy describing what information is accessed, collected, stored, used and shared. OpenAI API: receives the text/context necessary for LLM tasks such as extraction, synthesis, classification or report generation. Depending on the workflow, this can include public-source text, YouTube comment text, contestant names/information and the user's query or episode context. OpenAI offers a DPA and, for EEA customers, its current DPA provides for OpenAI Ireland and SCCs or an adequacy decision for relevant onward transfers. European API data residency is available for eligible configurations, but I have not verified that my current project/API configuration uses it. Pinecone: stores/retrieves embeddings for the project's indexed content. The indexed material is primarily source/plot content used for retrieval rather than a deliberate user-profile database. However, because source material can discuss identifiable contestants, embeddings/chunks may still represent personal data. The exact Pinecone region and contractual/transfer configuration should be verified from the project's account configuration. Tavily: receives search queries when external web research is required and returns web-search results. Queries can include show, season, episode, contestant or storyline information. Tavily states that it acts as a processor when processing personal information on behalf of a corporate client, but the exact contractual terms and international-transfer mechanism applicable to this project have not yet been documented. Other public-web sources: pages are retrieved as research sources. Their content may contain personal data about identifiable contestants, but the pipeline is not intentionally collecting private contestant data. Lawful basis: My provisional GDPR basis for processing publicly available contestant information and public comments is Article 6(1)(f), legitimate interests, because the processing serves the product's purpose of providing episode-aware summaries, storyline context and aggregated fan reactions. This would still require a documented legitimate-interests assessment covering necessity, proportionality and the reasonable expectations/rights of the people concerned. The system does not intentionally require Article 9 special-category data. However, comments and public sources can contain sensitive claims or inferences about identifiable contestants. Those should not automatically be treated as safe to process merely because they are publicly available; unnecessary sensitive information should be filtered or excluded. Current compliance gap: I have not yet documented, vendor by vendor, the exact hosting region, processor/DPA status, retention configuration and international-transfer mechanism. Therefore I would mark those elements as “Cannot determine / requires verification” rather than claiming they are compliant. OpenAI has documented DPA and transfer mechanisms available, but whether the project's actual configuration uses the relevant options still needs to be evidenced*  |  |
| :---- | :---- |
| *Evidence supplied / link:*  |  |
| **Response date** | 19/08/26 |
| **Effect on audit** | *No change / Finding updated / Classification updated* |

**GDPR**

## **Question 3**

| How long are source text, embeddings, logs and generated recaps retained, how are they deleted, and how can a commenter or contestant request access, correction, objection or erasure? |
| :---- |
| **Why it matters:** This determines compliance with storage limitation, data-subject rights, accuracy and privacy-by-design requirements. |
| **Provisional assumption:** No production retention schedule, deletion workflow, data-subject request process or correction route for generated claims has been documented. |

### **Written response**

| *Response: There is currently no formally documented retention schedule or data-subject-rights workflow for the project. Source text and embeddings: Source material used for retrieval, including public recaps and other indexed content, can remain in the knowledge base/Pinecone until the index is manually updated or deleted. I have not yet implemented an automatic retention period or deletion mechanism for individual records. Where indexed chunks contain personal data about identifiable contestants, this therefore represents a retention-control gap. YouTube comments: Comments are retrieved from YouTube for fan-reaction analysis. The product does not need to maintain a persistent profile of individual commenters, but I have not documented a specific retention/deletion period for retrieved comment text or any cached/processed version of it. Generated recaps/reports: Generated outputs may contain contestant names and information derived from public sources. There is currently no documented retention period or automated deletion policy for these outputs. Logs/vendor retention: Retention in application logs and by external vendors such as OpenAI, Pinecone, Tavily or YouTube has not yet been mapped and documented. Vendor-side retention therefore needs to be verified separately rather than assumed. Data-subject requests: There is currently no dedicated process through which a YouTube commenter or contestant can request access, correction, objection or erasure. If the project were deployed publicly, I would need to provide a privacy contact/request mechanism, identify where information relating to that person exists across stored source text, embeddings and generated outputs, and establish a process for correcting, restricting or deleting it where the GDPR requires this. This is therefore a clear GDPR governance gap: retention periods, deletion procedures and a data-subject-rights workflow need to be defined and documented before production use.*  |  |
| :---- | :---- |
| *Evidence supplied / link:*  |  |
| **Response date** | 19/08/26 |
| **Effect on audit** | *No change / Finding updated / Classification updated* |

# **Audit-trail closing note**

Retain the written answers and evidence with the final submission. Record any changed conclusion in Phase 5 of the peer audit and explain which new evidence caused the change.

| Answers received |  |
| :---- | :---- |
| **Audit updated** |  |
| **Debrief date** |  |
| **Auditor sign-off** |  |

