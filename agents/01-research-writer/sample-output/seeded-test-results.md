# Seeded test results, final rules

Real output from the Research Writer on 2026-10-30, Groq `openai/gpt-oss-20b`. The input is `sample-input/seeded-draft.txt`, sent in three batches of 10. The closing line of each reply is left out.

```text
1 | UNSUPPORTED | none | no ledger evidence
2 | SUPPORTED | 5 | AR reduces navigation difficulties
3 | UNSUPPORTED | none | no ledger evidence
4 | SUPPORTED | 2 | too much visual info overloads learner
5 | UNSUPPORTED | none | ledger does not mention annotations
6 | SUPPORTED | 3 | review found 31 VR studies 2010-2020
7 | UNSUPPORTED | none | ledger lists 31, not 52
8 | SUPPORTED | 4 | VR simulators valued for cost-effectiveness, safety
9 | UNSUPPORTED | 4 | ledger says acceptable, not perfect
10 | SUPPORTED | 1 | wearable AR promising with clear signal
11 | UNSUPPORTED | none | No claim in ledger
12 | SUPPORTED | 7 | Quote confirms aid
13 | UNSUPPORTED | none | No evidence
14 | SUPPORTED | 6 | Quote confirms effects
15 | UNSUPPORTED | none | Contradicts evidence
16 | SUPPORTED | 8 | Quote confirms
17 | UNSUPPORTED | none | No evidence
18 | UNSUPPORTED | none | No evidence
19 | UNSUPPORTED | none | No evidence
20 | UNSUPPORTED | none | No evidence
21 | UNSUPPORTED | none | No supporting quote
22 | UNSUPPORTED | none | No supporting quote
23 | UNSUPPORTED | none | No supporting quote
24 | UNSUPPORTED | none | No supporting quote
25 | UNSUPPORTED | none | No supporting quote
26 | UNSUPPORTED | none | No supporting quote
27 | SUPPORTED | 2 | Quote states too much info impairs selection
28 | UNSUPPORTED | none | No supporting quote
29 | UNSUPPORTED | none | No supporting quote
30 | SUPPORTED | 4 | Quote values VR flexibility in traffic scenarios
```

Score: 20 of 20 unsupported caught, 10 of 10 supported matched to the right entry. Line 9 lists entry 4 as the quote it compared against, although the sentence is correctly UNSUPPORTED.
