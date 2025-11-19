# DA5401: Endsem Data Challenge

Submitted by: **Devashish Tripathi**

Roll Number: **DA25C006**

Public repository for the Endsem Data Challenge on Metric Learning for the course DA5401.

The project notebook is contained in Notebook. All sections have been run and result in the best personal submission on the 60% test labels made available for the same (an RMSE of 3.690). There might be slight changes in the results due to randomness of some methods utilised in case of reruns.

The dataset files are provided, along with any other file extracted or created during a part of the process. The final submission file is also provided. To ensure that the notebook runs out-of-the-box given the dependencies are installed (refer to requrirements.txt), paths have been changed accordingly, but based on your system/platform, you might need to modify them again.

Additionally, if the notebook is to be run on Kaggle entirely from scratch, please ensure the following:

1. As of this commit, there is some issue with regards to using transformers on Kaggle for importing libraries. While transformers was only used to download models to extract text-embeddings which are already provided, if there is any need of doing so again, the following steps need to be taken:
   
    ```python
     # In the first cell of the Kaggle notebook`
     !pip install -U transformers
     # Now restart the session
    ```

2. You have a valid token from HuggingFace incase embeddings from Gemma are to be generated from scratch. If you are on Kaggle, just add your key in *Add-Ons>Secret*. Otherwise, in the first cell in the notebook

   Replace:
   ```python
    import os
    from kaggle_secrets import UserSecretsClient
    user_secrets = UserSecretsClient()
    secret_value_0 = user_secrets.get_secret("HF_TOKEN")
    
    os.environ["HF_TOKEN"] = secret_value_0
    
    from huggingface_hub import login
    
    login(token=os.environ["HF_TOKEN"])
   ```

   With:
   ```python
    import os
    os.environ["HF_TOKEN"] = "api_key"
    from huggingface_hub import login
    login(token=os.environ["HF_TOKEN"])
   ```


Thank you :)

