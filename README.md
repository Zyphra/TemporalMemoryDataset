# Temporal Memory Dataset
This is the dataset used in the paper "Toward Conversational Agents with Context and Time Sensitive Long-term Memory". The dataset is separated into 'conversational_data' and 'test_data'. 

## Conversational Data
The conversational data consist of 12 conversation logs between two agents. These logs were taken from the LoCoMo dataset (Maharana et al., 2024) and modified slightly to extend portions of the conversations which are queried about further into the past, both in terms of time and number of tokens. There are 12 conversation logs. Each log is stored in a separate json file. To retrieve a conversation log, e.g., log number 46, into a python script, simply clone the repo and run

```python
import json

with open('conversational_data/46.json', 'r') as openfile:
            data = json.load(openfile)
```





## References

Maharana, A., Lee, D. H., Tulyakov, S., Bansal, M., Barbieri, F., & Fang, Y. (2024). Evaluating Very Long-Term Conversational Memory of LLM Agents. arXiv preprint arXiv:2402.17753.
