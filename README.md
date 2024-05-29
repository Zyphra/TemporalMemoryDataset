# Temporal Memory Dataset
This is the dataset used in the paper "Toward Conversational Agents with Context and Time Sensitive Long-term Memory" (Alonso et al., 2024). Here's the abstract:

*There has recently been growing interest in conversational agents with long-term memory which has led to the rapid development of language models that use retrieval-augmented generation (RAG). Until recently, most work on RAG has focused on information retrieval from large databases of texts, like Wikipedia, rather than information from long-form conversations. In this paper, we argue that effective retrieval from long-form conversational data faces two unique problems compared to static database retrieval: 1) time/event-based queries, which requires the model to retrieve information about previous conversations based on time or the order of a conversational event (e.g., the third conversation on Tuesday), and 2) ambiguous queries that require surrounding conversational context to understand. To better develop RAG-based agents that can deal with these challenges, we generate a new dataset of ambiguous and time-based questions that build upon a recent dataset of long-form, simulated conversations, and demonstrate that standard RAG based approaches handle such questions poorly. We then develop a novel retrieval model which combines chained-of-table search methods, standard vector-database retrieval, and a prompting method to disambiguate queries, and demonstrate that this approach substantially improves over current methods at solving these tasks. We believe that this new dataset and more advanced RAG agent can act as a key benchmark and stepping stone towards effective memory augmented conversational agents that can be used in a wide variety of AI applications.*

## Conversational Data
The dataset consists of conversational data and the test data. The conversational data consists of 12 conversation logs between two agents. These logs were taken from the LoCoMo dataset (Maharana et al., 2024) and modified. See paper for details. There are 12 conversation logs. Each log is stored in a separate json file. Each file contains a dictionary that stores conversation sessions. Each session stores a list of responses with associated meta-data (e.g., time, date, speaker, response number). To retrieve a conversation log, e.g., log number 46, into a python script, simply clone the repo and run

```python
import json

with open('ConversationalData/46.json', 'r') as openfile:
            data = json.load(openfile)
```

## Test Data
The test data consists of three directories, each containing test questions and answers for a different type of test: time based query test, time+content based query test, and ambiguous time-based query test. The time and ambiguous time tests are further split into sub-types (see article for details). Questions and answers for each test (sub-)type is stored in a json file. Each json file contains a dictionary with a key for each file number ('file_n'), which retrieves a list of dictionaries, where each dictionary stores versions of a question and a list of the response numbers that the question is referring to. 

To retrieve the test questions for the, e.g., 'date', time-based test into a python script clone the repository then from the base directory run
```python
import json

with open('TestData/time_qs/test_dates.json', 'r') as openfile:
            test_data = json.load(openfile)
```

To retrieve the test questions for the, e.g., 'date', ambiguous time-based test into a python script clone the repository then from the base directory run
```python
import json

with open('TestData/ambiguous_time_qs/test_dates.json', 'r') as openfile:
            test_data = json.load(openfile)
```

To retrieve the test questions for the time+content-based test into a python script clone the repository then from the base directory run
```python
import json

with open('TestData/content_time_qs/content_time_qs.json', 'r') as openfile:
            test_data = json.load(openfile)
```




## References

Maharana, A., Lee, D. H., Tulyakov, S., Bansal, M., Barbieri, F., & Fang, Y. (2024). Evaluating Very Long-Term Conversational Memory of LLM Agents. arXiv preprint arXiv:2402.17753.
