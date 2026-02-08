# Qualitative Codebooks

## Codebook and Examples of Discussions for Formative Study

We presented two examples, one representing retaining two codes after discussions, and one representing code merging after discussions. For the first example, regarding a participant's statement: *“Categories such as health ... should be flagged for deletion ... In contrast, less sensitive categories ... were often retained”* Coder A labeled this as “Selective Deletion”, whereas Coder B labeled this as “Data Classification”. Through discussion, they agreed that both “Selective Deletion” and “Data Classification” should be reserved, retaining them as 2 separate codes.

Regarding a participant's statement: *“I definitely need the system to provide me with manual modification permission.”* Coder A labeled this as “Error Correction”, Coder B labeled this as “Privacy Redaction”. Through discussion, they agreed that assigning a specific motivation (accuracy vs. privacy) to this specific utterance was speculative. They used a more descriptive code “provactive modification” as the code.

Table 1 details the themes and codes derived from the semi-structured interviews (N=40) regarding users' perceptions of RAG-based memory privacy risks.

### Table 1: Codebook for the formative study: perceptions of memory & privacy, which is derived from semi-structured interviews (N=40).

| **Theme**                                                    | **Sub-theme / Code**                                         | **Description**                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **F1: Passive memory mechanism hinder awareness**            | **Opaqueness of current memory mechanism**                   | Participants lack knowledge that the system retains memories or private memories. |
|                                                              | **Lacked effective means to regulate memory**                | Memory management was difficult to use.                      |
| **F2: Unaware of inference and aggregation in memories**     | **Lack awareness of privacy implications of memory inference** | Fail to recognize inferential privacy.                       |
|                                                              | **Highlight the risk after explained about the inference**   | Inference risk was emphasized by participants (after explanation). |
| **F3: Need for granular control based on sensitivity of private memories** | **Granular control over private memories**                   | Desire to edit, add, or delete memory entries and sources.   |
|                                                              | **Proactive management strategies based on content sensitivity** | Need the system to afford the management differed by sensitivity. |

------

## Codebook For Evaluation Study

Table 2 details the themes and codes derived from the exit interviews (N=36) regarding user strategies and feedback on MemoAnalyzer.

### Table 2: Codebook for evaluation study: user strategies & feedback, which is derived from exit interviews (N=36).

| **Theme**                                | **Sub-theme / Code**            | **Definition**                                               |
| ---------------------------------------- | ------------------------------- | ------------------------------------------------------------ |
| **Balancing privacy and utility**        | **Context-dependent retention** | Retaining information only if it is directly relevant to the immediate task context. |
|                                          | **Category-based filtering**    | Systematically removing specific high-risk data types (e.g., location, finance) regardless of context. |
|                                          | **De-identification**           | Removing personally identifiable markers (Names, Schools) while keeping generic attributes. |
| **Efficient and effective notification** | **Visual salience**             | The effectiveness of visual cues (color/highlighting) in directing attention to risks. |
|                                          | **Real-time feedback**          | The value of receiving immediate privacy alerts during the interaction flow. |
| **Increased awareness and trust**        | **Source tracking**             | Understanding the link between current inferences and past data sources enhances trust. |
|                                          | **Risk awareness**              | The tool helps users realize previously overlooked privacy risks in conversations. |
| **Simplified but Proactive Design**      | **Workflow integration**        | Preference for automated analysis over manual sorting (clustering/dragging). |
|                                          | **Automated analysis**          | The reduction of cognitive load through automated risk identification. |
| **Improvements**                         | **False negative**              | Sensitive information was not flagged by LLMs.               |
|                                          | **False positive**              | Non-sensitive information was wrongly flagged by LLMs.       |