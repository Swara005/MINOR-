# Fake Profile Detection on Linkedin-

Data Preparation:
We start with profiles containing different sections, such as About, Experience, and Education. Our goal is to classify these profiles as either real or fake.

Combining Text:
We combine the text from all sections of each profile into a single document. This gives us a comprehensive view of the profile's content.

Tokenization:
Using BERT's tokenizer, we break the combined text into tokens. Each token corresponds to a piece of the text, and we keep track of these tokens along with their associated labels (real or fake).

Creating BERT Embeddings:
We pass the tokens through the BERT model, which generates high-dimensional embeddings for each token. These embeddings capture the contextual meaning of each word in the profile.
Average Embeddings:

For each class (real and fake), we calculate the average embedding by averaging the embeddings of all tokens associated with that class. This helps us understand the typical characteristics of real and fake profiles.

Adjusting Token Embeddings:
We subtract the average class embedding from each token's embedding for that class. This adjustment highlights the unique information in each token relative to its class.

Combining Profile Embedding:
We then combine the adjusted embeddings of all tokens in a profile to create a single representation of the profile. This gives us a concise embedding that encapsulates the entire profile's information.

Fine-Tuning BERT for Classification:
We set up a simple classifier on top of the combined embeddings. This classifier is trained to distinguish between real and fake profiles. We use a training loop to adjust the model’s parameters based on the classification performance.
Model Evaluation:

Finally, we evaluate the model using a test set to see how well it predicts the class labels of unseen profiles.
