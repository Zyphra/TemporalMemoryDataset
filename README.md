# Temporal Memory Dataset
This is the dataset used in the paper "Toward Conversational Agents with Context and Time Sensitive Long-term Memory" (Alonso et al., 2024).

## Conversational Data
The conversational data consists of 12 conversation logs between two agents. These logs were taken from the LoCoMo dataset (Maharana et al., 2024) and modified slightly to extend portions of the conversations which are queried about further into the past, both in terms of time and number of tokens. There are 12 conversation logs. Each log is stored in a separate json file. Each file contains a dictionary that stores conversation sessions, each consisting of a list of responses, and each responses associated meta-data (e.g., time, date, speaker, response number). To retrieve a conversation log, e.g., log number 46, into a python script, simply clone the repo and run

```python
import json

with open('ConversationalData/46.json', 'r') as openfile:
            data = json.load(openfile)
```

## Test Data
The test data consists of three directories, each containing test questions and answers for a different type of test: time based query test, time+content based query test, and ambiguous time-based query test. The time and ambiguous time tests are further split into sub-types (see article for details). Questions and answers for each test (sub-)type is stored in a json file. Each json file contains a dictionary with a key for each file number (file_n), which retrieves a list of dictionaries, where each dictionaries stores versions of a question and a list of the response numbers that the question is referring to. 

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
