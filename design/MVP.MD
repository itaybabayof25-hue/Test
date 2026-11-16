הנה הטקסט, מוכן להעתקה:

```markdown
# MVP:

| Step | Type |
|---|---|
| 1. Uploading the invoice to the system by the user | **User action** |
| 2. Extracting the relevant fields from the uploaded invoice | **Llm** |
| 3. The system will perform a matching check between the invoice and the databases of the company, to check whether this is a supplier recognized by the company. If approved, the system will move to step 4<br><br>If not approved, we will move to step 6 | **Regular code** |
| 4. The system will check whether an active order exists by comparing against the company's procurement/operations log.<br><br>If yes, we will move to step 5<br><br>If not, we will move to step 7 | **Regular code** |
| 4.1. Checking whether the invoice has been paid<br><br>If it has been paid, the system will pop up a message with the payment details.<br><br>If it has not been paid, the system will continue to step 5 | **Multi-turn conversation** |
| 5. If the matching stage was approved (steps 3,4), the system will issue a confirmation message for the service (initial approval), and will ask the user for approval to move on to the next stage of the check, step 8 | **Multi-turn conversation.** |
| 6. In a case where the system does not recognize the service provider as a supplier approved by it - the system will draft a message to the user with a recommendation to clarify the matter with management. | **Multi-turn conversation.** |
| 7. In a case where there is no match between the service appearing on the invoice and the company's procurement/service log - the system will display a message to the user with a recommendation to clarify the matter with the procurement/operations managers. | **Multi-turn conversation.** |
| 8. The system moves on to the advanced stage of the check, and works to locate the relevant contract between the supplier and the company | **RAG** |
| 9. If the contract was located, the system will move to step 10, and if the contract does not exist, the system will issue a message to clarify the matter with the procurement managers/management. | **Multi-turn conversation** |
| 10. Extracting the relevant fields from the supplier's contract. | **llm** |
| 11. Comparison between the fields obtained from the invoice (section 2) and the fields obtained from the contract (section 10).<br><br>If a match is obtained, the system will move to step 12<br><br>If a mismatch is obtained, the system will move to step 13 | **Simple code** |
| 12. The system displays a message to the user that everything is in order and recommends approval. | **Multi-turn conversation** |
| 13. The system will issue a message to the user detailing the data found to be problematic in step 11. | **Multi-turn conversation.** |
```