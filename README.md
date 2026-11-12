# Tax Law Brazil Cosit dataset

A question answering dataset on Brazilian corporate tax law, built for evaluating large language
models on legal reasoning in Portuguese.

- **101 questions** with the official answer, the normative reference and the gold passage
- **30 legal documents** that form the retrieval corpus

The questions were selected from "Perguntas e Respostas da Pessoa Jurídica 2023", a collection
updated every year by the General Coordination of Taxation (Cosit) of the Brazilian Federal Revenue
Service ([source PDF](https://www.gov.br/receitafederal/pt-br/assuntos/orientacao-tributaria/declaracoes-e-demonstrativos/ecf/perguntas-e-respostas-pj-2023.pdf), accessed on 11 Nov 2023).

## Files

| Path | Content |
|---|---|
| `tax_law_brazil_cosit/dataset_taxlaw_brazil.csv` / `.json` | Questions: `question`, `answer`, `reference`, `gold_passage` |
| `tax_law_brazil_cosit/corpus_documents.csv` / `.json` | Corpus: `document_id`, `content` |
| `tax_law_brazil_cosit/tax_law/`, `corpus/` | The same two tables in Hugging Face `datasets` format |
| `tax_law_brazil_cosit.zip` | Everything above in one archive |

## Loading

```python
from datasets import load_from_disk

ds = load_from_disk("tax_law_brazil_cosit")
print(ds["tax_law"][0]["question"])
```

The experiments that use this dataset are in the
[`code`](https://github.com/joaopaulopresa/code) repository.
