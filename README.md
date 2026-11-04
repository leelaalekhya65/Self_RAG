# Self_RAG
Self-RAG (Self-Reflective Retrieval-Augmented Generation) is an advanced RAG technique where an LLM evaluates its own answers and decides whether it needs to retrieve more information to produce a better answer.
Problems with Naive RAG
1. Unnecessary Retrieval: Retrieves documents even when external information isn't needed.
2. Irrelevant Retrieval: May retrieve documents that are not sufficiently relevant to the query.
3. No Document Verification: Doesn't inherently verify whether retrieved documents contain factually correct information.
4. No Answer Verification: Doesn't inherently check whether its generated answer is factually correct or supported by evidence.
5. Hallucination: May generate incorrect or misleading answers using retrieved context.
6. Contradictory Information: May struggle when retrieved documents contain conflicting information.
7. Retrieval Noise: Irrelevant information can confuse the LLM and reduce answer quality.
   
In Self-RAG, before generating an answer, the model uses reflection to evaluate a few things:
1. Should I retrieve? – Does this question require external information?
2. Is retrieval relevant? – Are the retrieved documents relevant to the user's question?
3. Is the information useful? – Does the retrieved content help answer the question?

After generating the answer, it evaluates:
4. Is the answer supported? – Is my answer supported by the retrieved documents?
5. Is the answer useful? – Does my answer properly satisfy the user's question?

