# contact_tracer
A proof-of-concept for identifying likely asymptomatic carriers through network analysis

Asymptomatic infections account for almost half of all SARS-CoV-2 cases. https://www.acpjournals.org/doi/10.7326/M20-3012
The goal of this repo is to test various methods, starting with quantum computing, for prioritizing testing for people who
have interacted with confirmed cases, in order to identify asymptomatic carriers and decrease the spread of SAR-CoV-2.
According to mathematical models, contact tracing, testing and isolation can dramatically reduce the spread.
https://www.thelancet.com/journals/laninf/article/PIIS1473-3099(20)30457-6/fulltext
But with limited testing, scientists must find ways to prioritize who to test.

This problem is one for which quantum computing is uniquely suited. The quantum_trace module,
which will use qiskit package, will take a handful of 2nd or 3rd generation positives and try to predict the mostly spread
path, so that the asymptomatic cases can be identified. The probability of each person being an asympotamic
carriers can be represented by one qubit, and gates (interactions between the qubits) can indicate the likelihood of any
person as the source of infection. Instead of calculating every probability, quantum computing can quickly test various
possible infection paths to determine the most likely. If a breakthrough in quantum computing emerges before a SAR-Cov-2
vaccine or cure, it could be a critical tool in epidemiologists' kit.

However, before we can try this proof of concept, we need data that can reasonably test our algorithms. That is the purpose
of the model_maker module. It will load pre-SARS-CoV-2 contact data, such as that from Community Resource for Archiving 
Wireless Data At Dartmouth (crawdad.org) and simulate an infection in one person which spreads.

We can explore other methods, such as GPUs and TPUs, after the Qiskit hackathon ends on July 1.
https://quantuminstitute.yale.edu/news/take-part-yqi-x-qiskit-quantum-hackathon-june-24-july-1
Even if quantum supremacy is not just around the corner, quantum computing may be a valuable tool in fighting SAR-CoV-3.
