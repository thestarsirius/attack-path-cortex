# Attack Path Cortex | قشرة مسارات الهجوم

An interactive defensive-security demo: a fake university network is modeled as a graph, six agents (recon, planner, grapher, patcher, memory, critic) are mapped to brain regions, and the dashboard computes real attack paths to the student database, finds the riskiest node, hardens it, and re-checks until no path remains.

لوحة تفاعلية دفاعية: شبكة جامعة وهمية على شكل رسم بياني، ٦ وكلاء موزعين على مناطق الدماغ، واللوحة تحسب مسارات الهجوم فعليًا إلى قاعدة بيانات الطلاب، وتحدد أخطر عقدة، وتحصّنها، وتعيد الفحص.

## How it works
- `GRAPH` inside `index.html` holds the nodes and edges (fake data only).
- A depth-first search lists every attack path from the phishing email to the student database.
- The node that appears on the most paths is the riskiest; the patcher "hardens" it by cutting its incoming edges, then the critic re-checks.
- Risk score is an estimate: `100 × (1 − e^(−paths/5))`.

## Use your own graph
Replace the `GRAPH` object with nodes/edges exported from your own data (for example the `graph.json` produced by [graphify](https://github.com/Graphify-Labs/graphify)).

## Disclaimer
Defensive and educational only. All data is fictional.

Author: Shahad Ghazwani
