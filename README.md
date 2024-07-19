# 🌟 RockyBot: Advanced SQL Query Chatbot

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg) ![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)

## 🚀 Introduction

Welcome to **RockyBot**! RockyBot is a sophisticated chatbot designed to interact with your SQL database, providing accurate answers to your business queries without the need for coding knowledge. Utilizing LangChain and Google Generative AI, this project leverages the power of machine learning to enhance your business efficiency.

 
  ![gogle palm image](https://github.com/Prakashpsk/-RockyBot-Advanced-SQL-Query-Chatbot/blob/main/Google-PaLM-Algorithm-image.png)

                                    
## 🧠 Skills/Concepts Developed

- **Python**: Developed core logic for data processing and API interaction.
- **Streamlit**: Built an interactive web application for user inputs and displaying results.
- **LangChain**: Implemented for handling document processing and embeddings.
- **Google Palm LLM**: Utilized for generating embeddings and responses.
- **SQL**: Managed database connections and executed complex queries.
- **Natural Language Processing (NLP)**: Applied NLP techniques to interpret and answer business queries.
- **Data Engineering**: Managed data pipelines for loading, processing, and storing documents.
- **API Integration**: Integrated Google Generative AI API for embedding and chat functionalities.

## ❓ Problem Statement

Business owners and managers often need quick and accurate insights from their databases but may lack the technical knowledge to write SQL queries. RockyBot solves this by allowing users to ask natural language questions and automatically generating the correct SQL queries to fetch the required data.

## 🌟 Impact of Your Work

RockyBot significantly enhances the efficiency of business operations by providing instant answers to data-related questions. It eliminates the need for technical expertise in SQL, making data-driven decision-making accessible to everyone in the organization.

## 📊 Modeling

### Steps

1. **API Key Setup**: Integrate Google Palm LLM with the API key.
    ```python
    from langchain.llms import GooglePalm

    api_key = 'your_api_key_here'
    llm = GooglePalm(google_api_key=api_key, temperature=0.2)
    ```
2. **Database Connection**: Connect to the SQL database.
    ```python
    from langchain.utilities import SQLDatabase
    from langchain_experimental.sql import SQLDatabaseChain

    db_user = "root"
    db_password = "root"
    db_host = "localhost"
    db_name = "atliq_tshirts"

    db = SQLDatabase.from_uri(f"mysql+pymysql://{db_user}:{db_password}@{db_host}/{db_name}", sample_rows_in_table_info=3)
    ```
3. **Query Execution**: Run and test SQL queries.
    ```python
    db_chain = SQLDatabaseChain.from_llm(llm, db, verbose=True)
    qns1 = db_chain("How many t-shirts do we have left for Nike in extra small size and white color?")
    ```
4. **Few-Shot Learning**: Implement few-shot learning for improving query accuracy.
    ```python
    few_shots = [
        {'Question': "How many t-shirts do we have left for Nike in XS size and white color?",
         'SQLQuery': "SELECT sum(stock_quantity) FROM t_shirts WHERE brand = 'Nike' AND color = 'White' AND size = 'XS'",
         'SQLResult': "Result of the SQL query",
         'Answer': qns1}
        # Add more examples
    ]
    ```

## 📈 Visualization

Visual representation of data can be added here using tools like matplotlib, seaborn, or Plotly for enhanced insights.

## 🏁 Conclusion

RockyBot revolutionizes how businesses interact with their data, making complex SQL queries accessible through natural language. It ensures that business owners and managers can quickly retrieve and analyze data, leading to better and faster decision-making.

## 💡 Recommendations

- **Expand Database Compatibility**: Extend RockyBot to support other types of databases.
- **Enhance NLP Capabilities**: Improve the natural language understanding to handle more complex queries.
- **User Interface Improvements**: Develop a more user-friendly interface for ease of use.

## 🛠️ How to Use

1. **Setup**: Clone the repository and install the required dependencies.
    ```sh
    git clone https://github.com/Prakashpsk/RockyBot.git
    cd RockyBot
    pip install -r requirements.txt
    ```
2. **Configure**: Add your API key and database credentials.
3. **Run**: Start the application.
    ```sh
    streamlit run app.py
    ```

## 🏆 Credits

- **YouTube Channel**: For code basis and tutorials.

## 👤 About the Author

[Prakash.P](https://www.datascienceportfol.io/prakashScientist) is a Data Scientist with expertise in modeling. Feel free to reach out for any questions or collaborations at [prakash2822001@gmail.com].
