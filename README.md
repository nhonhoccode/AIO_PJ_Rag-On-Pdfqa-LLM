# Chainlit Chatbot with RAG and ngrok

This project demonstrates how to build and deploy a Retrieval-Augmented Generation (RAG) chatbot using [Chainlit](https://github.com/Chainlit/chainlit.git) for the user interface, and how to deploy it using [Google Colab](https://colab.google/) and [ngrok](https://ngrok.com/).

## Requirements

- Google Colab account
- GitHub account
- ngrok account

## Setup and Execution

1. **Clone the Repository**

    First, clone this repository to your local machine or directly to your Google Colab environment.

    ```bash
    git clone https://github.com/nhonhoccode/AIO_PJ_Rag-On-Pdfqa-LLM.git
    cd aioprj-m1-rag-on-pdfqa-llm
    ```

2. **Open Google Colab**

    Open [Google Colab](https://colab.research.google.com/) and upload the `rag-chatbot-by-chainlit.ipynb` file from this repository.

3. **Install Dependencies**

    In the first cell of your Colab notebook, install the necessary dependencies:
```
!pip install -q transformers==4.41.2
!pip install -q bitsandbytes==0.43.1
!pip install -q accelerate==0.31.0
!pip install -q langchain==0.2.5
!pip install -q langchainhub==0.1.20
!pip install -q langchain-chroma==0.1.1
!pip install -q langchain-community==0.2.5
!pip install -q langchain-openai==0.1.9
!pip install -q langchain_huggingface==0.0.3
!pip install -q chainlit==1.1.304
!pip install -q python-dotenv==1.0.1
!pip install -q pypdf==4.2.0
!npm install -g localtunnel
!pip install -q numpy==1.24.4
```

4. **Create file app.py**
    ```python
    %%writefile app.py
    """
    # Your entire app.py content here
    """
    ```

5. **Install and Connect ngrok**
    ```
    # Install ngrok
    !pip install pyngrok -q

    from pyngrok import ngrok

    # Replace <YOUR-AUTHTOKEN> with your actual token
    !ngrok config add-authtoken <YOUR-AUTHTOKEN>

    # Connect ngrok
    public_url = ngrok.connect(8000).public_url
    print(f"Public URL: {public_url}")
    ```
6. **Run the Application**
    ```
    !chainlit run app.py
    ```

8. **Access Your Chatbot**

    After running the code, Colab will print a public URL. Use this URL to access your chatbot.
9. **Result**


## Usage

1. **Upload a File**

    Upload a PDF or text file when prompted.

2. **Ask Questions**

    Ask questions about the content of the uploaded file. The chatbot will process the file and respond with answers, citing sources from the file.

## Contributing

If you encounter any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.
