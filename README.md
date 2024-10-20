# Creating Your First Model on Hugging Face

This README provides step-by-step instructions for creating and uploading your first model on Hugging Face.

## Step 1: Set Up Your Environment

1. **Install the Hugging Face Transformers Library**:
   Open your terminal and run:
   ```bash
   pip install -r requirements.txt

2. **Login to Hugging Face and create a token [https://huggingface.co/login?next=%2Fsettings%2Ftokens] with write settings.**
3. **Load the Model and Tokenizer :**
   Here's an example using a pre-trained BERT model for text classification:

         from transformers import BertTokenizer, BertForSequenceClassification
         import torch
         
         # **Load the tokenizer and model
         tokenizer = BertTokenizer.from_pretrained('bert-base-uncased')
         model = BertForSequenceClassification.from_pretrained('bert-base-uncased')
         
         # Example input text
         text = "Hello, Hugging Face!"
         inputs = tokenizer(text, return_tensors='pt')
         
         # Forward pass
         with torch.no_grad():
             logits = model(**inputs).logits
         
         print(logits)

Step 4: **Save and share your model:**
   Add these lines of code to python file 

      model.save_pretrained('./my_model')
      tokenizer.save_pretrained('./my_model')         

      from huggingface_hub import upload_folder
      upload_folder('./my_model', repo_id='username/repoName')

   Congratulations! You've created and uploaded your first model on Hugging Face. Happy coding!
