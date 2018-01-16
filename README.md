# Duplicate Document Detection using Python
If you ever worked with text documents, there is a high probability that you’ve had to deal with duplicate content at some point or the other. The process of manually scanning every document to detect duplicates is a tedious and, often, ineffective one. This presentation focuses on designing a machine learning model that not only identifies similar documents based on their text similarity, but also utilizes the documents’ metadata to confirm that a pair of similar documents are indeed duplicates, thus reducing the need for any manual intervention in detecting duplicate documents. The solution is a 2-step process which involves calculating the text similarity between two documents, and subjecting the pair to a classifier for a verdict.

## A Sneak-peek into the solution:

Text Similarity - Candidate Duplicates
When a new document enters the workflow, a cosine similarity score is calculated between the new document and every other document in the corpus. Document pairs that have similarity scores greater than a set threshold are filtered as ‘Candidate Duplicates’. This filtering means that we are ready to accept that all the pairs that have similarity scores lesser than our set similarity threshold are not duplicates.

## Classifier
These candidate duplicates will now be subjected to a trained classifier which will classify pairs of documents as duplicates based on their metadata features. Our classifier is a decision tree classification model that is trained on labeled duplicate documents and labeled non-duplicate documents, along with their corresponding similarity scores and metadata features like the document lengths, filing dates, document types etc.
