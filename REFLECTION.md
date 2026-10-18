# Mini-Project Reflection

**Jason Cooper**  
**CS 4390R X01**

## Project Reflection

When I first started this assignment, I actually planned on building a different GPT-2 project. After doing more research, I realized the original idea would require more time and computing resources than I had available, so I pivoted to building a phishing email classifier instead. Looking back, I think that was the right decision because it still let me apply the concepts from class while producing a complete working project.

One thing that went well was getting a pretrained GPT-2 model to perform binary classification instead of text generation. Before this project I mostly thought of GPT models as chatbots, so it was interesting seeing how they could be adapted for another task. I also liked building the full pipeline from loading the dataset to training, testing, and saving the model and evaluation results. Even though the final accuracy wasn't especially high, the notebook completed the entire machine learning workflow successfully.

The biggest challenge ended up being data preparation and debugging rather than the model itself. Public datasets don't always use the same column names or formatting, so I had to make sure the loader could correctly recognize the email text and labels. Training locally on CPU also meant limiting the dataset size and freezing most of the transformer layers to keep training times reasonable. I also ran into a few issues getting the notebook to recognize the correct dataset before finally getting everything working.

If I continued working on this project, I would train on a much larger dataset using a GPU and compare GPT-2 against other models like BERT or RoBERTa. I'd also like to include features beyond just the email text, such as URLs, sender information, and email headers, since those are commonly used in real phishing detection systems. Finally, I would spend more time tuning the model instead of relying mostly on the default training settings.

Overall, I'm happy with how the project turned out. The final model isn't something I would trust in a production environment, but it demonstrates the process of adapting a pretrained language model for a cybersecurity classification task. More importantly, it gave me practical experience working with Hugging Face, PyTorch, model fine-tuning, evaluation metrics, and the kinds of debugging that come with real machine learning projects.