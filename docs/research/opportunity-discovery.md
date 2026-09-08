# Finding and developing accessible research opportunities

Research date: 2026-09-07. Prepared for [Where can we find and develop accessible research opportunities?](https://github.com/tylerdurrett/think-bigger/issues/3).

This bounded survey identifies seven public resources and three documented discovery methods. It does not select an initial domain, certify any candidate as novel, or establish that an agent can solve it. Resource descriptions below are sourced facts; judgments about operator suitability and suggested investigations are explicitly research assessments.

## Findings

There are several viable sources for the envisioned collection, but they contain different things: explicit unanswered questions, known mathematical objects with unexplained properties, optimization instances with unsettled optima, and datasets on which a new empirical question could be posed. A benchmark task is not automatically an unsolved scientific problem. The collection would need to distinguish these kinds of opportunity to describe an eventual contribution accurately.

The strongest near-term access fit is a question whose inputs, baseline, and verification route are all downloadable or reproducible by the operator. That does not imply small compute needs or easy interpretation. Learned or statistical evaluation can fit: the single-cell denoising example below measures performance without directly observing ground truth. None of these resources demonstrates that an inexperienced operator can reliably judge research significance without acquiring domain understanding.

## Seven resources

### 1. Erdős Problems and its community metadata repository

**Provenance and example.** Thomas Bloom's [Erdős Problems](https://www.erdosproblems.com/) supplies statements and references. The associated [community repository](https://github.com/teorth/erdosproblems) maintains structured metadata, including status, tags, and related integer sequences. The [interactive table](https://teorth.github.io/erdosproblems/?status=open) records the **minimum overlap problem** as open; this is an illustration, not an independently verified current-status claim or recommendation to attempt it.

**Status check.** Read the exact statement, bibliography, discussion, and history, then inspect recent literature. The website explicitly says its status-change dates can reflect solutions discovered long before the database update. The repository's [field definitions](https://github.com/teorth/erdosproblems/blob/main/CONTRIBUTING.md) distinguish informal results and formalization; multipart questions need particular care.

**Access and evaluation.** Structured repository material has an [Apache-2.0 license](https://github.com/teorth/erdosproblems/blob/main/LICENSE), verified through GitHub's API. This is not a blanket license for the original papers or all website content. Some statements have Lean formalizations through [Formal Conjectures](https://github.com/google-deepmind/formal-conjectures). A formalized statement is a starting point, not an already supplied proof checker for arbitrary natural-language answers.

**Operator assessment.** Excellent provenance and explicit questions; substantial mathematical learning may still be necessary. Simple wording does not establish tractability. Local finite experiments may guide an attempt, while a universal claim needs a proof or appropriate counterexample.

### 2. On-Line Encyclopedia of Integer Sequences (OEIS)

**Provenance and example.** Maintained by the OEIS Foundation, entries contain definitions, formulas, code, references, contributors, and history. **Recamán's sequence**, [A005132](https://oeis.org/A005132/internal), includes a conjecture about whether every nonnegative integer appears, together with later doubts from its proposer. It demonstrates how a short computational definition can conceal a difficult research question. [OEIS introduction](https://oeis.org/wiki/Welcome)

**Status check.** Read dated comments and cited work, not only sequence keywords. An entry's editorial approval does not prove a conjecture within it. Search related sequences and alternate formulations before treating missing formulas or terms as a gap in knowledge.

**Access and evaluation.** Content is offered under [CC-BY-SA-4.0, with attribution requirements](https://oeis.org/wiki/The_OEIS_End-User_License_Agreement). Entries often supply runnable code and term files; these support independent recalculation. Matching finitely many terms does not establish a formula for every index.

**Operator assessment.** Relatively approachable for learning and small experiments; identifying a meaningful advance requires more than extending an easy sequence. Browsing sequences requesting more terms is a concrete discovery route documented by OEIS. It does not imply that every such extension is newsworthy.

### 3. House of Graphs

**Provenance and example.** The maintainers describe a searchable collection of interesting graphs, plus a directory of complete graph classes and generators. The research paper identifies extremal examples and counterexamples as central uses; named graphs such as the **Petersen graph** are illustrative objects, not unsolved problems. [Maintainer site](https://www.houseofgraphs.org/), [House of Graphs 2.0 paper](https://arxiv.org/abs/2210.17253), [author-hosted full paper](https://backoffice.biblio.ugent.be/download/01GQFACVMZMT5PM54MHN98PB0G/01GR1D0GFDXT5T2ZC57ZTKNKXT)

**Status check.** Search for an existing object, its invariants, and associated references; there is no universal open/solved status for a graph. Failure to find a counterexample in the interesting-graphs collection is not exhaustive verification. Distinguish that collection from a complete finite class.

**Access and evaluation.** Graph downloads, stored invariants, and generators support local searches and independent checks. Registration is required to contribute graphs, not merely browse. This survey did not establish a single blanket redistribution license for all graph data and linked generators; retain source links and inspect the selected asset's terms before bundling it.

**Operator assessment.** Visual examples can teach definitions and make conjectures concrete. A proposed inequality between graph properties still needs a literature check and explicit quantifiers. Exhaustive enumeration may become expensive rapidly.

### 4. CSPLib

**Provenance and example.** CSPLib is a constraint-programming benchmark library with problem specifications and associated materials. **Golomb rulers** has a statement, references, results, and models in several languages, including MiniZinc and Python-based systems. The goal concerns positions whose pairwise distances are distinct. [Golomb ruler specification](https://www.csplib.org/Problems/prob006/), [models](https://www.csplib.org/Problems/prob006/models/), [source repository](https://github.com/csplib/csplib)

**Status check.** A numbered CSPLib problem identifies a family, not a declaration that all its instances are unsolved. Consult the results page and cited research for the particular size or algorithmic claim. Historical records need refreshing before proposing a new bound.

**Access and evaluation.** The inspected pages state CC-BY-4.0; inspect the selected model and solver's own terms as well. Supplied models support local reproduction. For a ruler, independently checking unique distances verifies feasibility; it does not by itself establish minimum length.

**Operator assessment.** Accessible specifications and existing models lower the initial learning burden. Potential research directions include a new construction, improved bound, or better solving method; merely solving a documented small instance is practice. Hardware and runtime depend on the exact instance.

### 5. MIPLIB 2017

**Provenance and example.** The mixed-integer-programming library collects optimization instances with submitters and structural information. Its **Open** tag means no solution of the instance has been reported as solving it. The inspected list includes **tokyometro** with an incumbent objective, illustrating that an open optimum can coexist with feasible solutions. [MIPLIB overview](https://miplib.zib.de/), [Open instances](https://miplib.zib.de/tag_open.html)

**Status check.** Recheck the instance page, solution file, and [changelog](https://miplib.zib.de/CHANGELOG.html). The [download page](https://miplib.zib.de/download) provides versioned solution and instance-set files and notes that classifications can change. Record the version used for comparisons.

**Access and evaluation.** Public downloads include instances and test/checking scripts. A feasibility checker and objective recomputation support checking a proposed incumbent; proving optimality is a separate burden. [SCIP](https://scipopt.org/) provides a publicly available solver under Apache-2.0 since version 8.0.3, with dependency-specific terms. This survey did not establish one blanket license covering redistribution of every MIPLIB instance.

**Operator assessment.** Concrete computational progress is measurable, but numerical tolerances, incumbent versus bound, and model meaning require study. Some instances are far beyond a personal computer's practical limits. A better solution to one frozen instance need not establish a generally better algorithm or real-world deployment impact.

### 6. OpenML

**Provenance and example.** OpenML stores datasets, tasks, model runs, and benchmarking suites. A task specifies a dataset and evaluation procedure; the official introduction demonstrates **credit-g classification, task 31**, and curated suites. That is an illustration of available infrastructure, not a novel scientific question. [Concepts](https://docs.openml.org/concepts/), [official examples](https://docs.openml.org/intro/)

**Status check.** Dataset IDs, versions, active/deactivated status, and prior runs document data and experiments. They do not certify that a scientific question remains unanswered. Search the exact hypothesis and contemporary methods separately. [Dataset metadata and status](https://docs.openml.org/concepts/data/)

**Access and evaluation.** APIs load data and run evaluations. Licenses belong to individual datasets; original-data and paper URLs are available metadata. Fixed splits enable comparison, but repeated optimization against those splits can undermine a fresh generalization claim. [Dataset creation and provenance fields](https://docs.openml.org/data/)

**Operator assessment.** Useful for learning experimental discipline and exploring method behavior on modest tabular datasets. Potential contributions require a sharp hypothesis, such as a reproducible failure under a defined shift, and meaningful baselines. A higher leaderboard number alone does not demonstrate scientific novelty.

### 7. Open Problems in Single-Cell Analysis

**Provenance and example.** This consortium maintains biological analysis benchmarks with task code, metrics, datasets, and releases. Its **denoising** benchmark includes public peripheral-blood and pancreas datasets. It uses molecular cross-validation: split observed molecules, denoise one part, and evaluate against another. This supplies an example of statistical evaluation when the underlying clean signal is unobserved. [Denoising benchmark](https://www.openproblems.bio/benchmarks/denoising/)

**Status check.** Follow the exact task release, dataset, metric definition, and method results. These are ongoing comparison tasks, not binary unsolved theorems. The inspected benchmark also exposed automated quality-control findings; investigate such findings before treating a ranking as authoritative.

**Access and evaluation.** The organization specifies MIT software unless stated otherwise, separate website-content licensing, and original licenses for datasets and third-party assets. Check the exact dataset. [Licensing and attribution](https://github.com/openproblems-bio), [datasets](https://openproblems.bio/datasets/)

**Operator assessment.** Public-data method research can fit the no-new-experiments constraint. Larger matrices and model training may need substantial memory or accelerators. Biological interpretation is a higher learning burden than running the pipeline. Improved denoising on a benchmark supports a bounded computational claim; establishing a new biological mechanism may require evidence outside this project's initial access boundary.

## Three documented ways to develop questions

1. **Find empirical structure and turn it into a conjecture.** Davies and colleagues trained predictors on mathematical objects, used attribution to investigate relationships, and developed conjectures and mathematical results in knot theory and representation theory. This documents a path from computational observation to a question worth formal study. It involved expert mathematicians, so it is evidence for the method, not evidence that an inexperienced operator can replace that expertise. [Primary paper](https://doi.org/10.1038/s41586-021-04086-x)

   **Proposed adaptation:** ask whether two computable properties of a selected graph class have an unexplained relationship; test on generated objects and known difficult examples. This particular proposal is brainstorming. Predictive success suggests a relationship under the sampled distribution, not a theorem.

2. **Study stronger constructions and what makes them work.** FunSearch paired program generation with an evaluator and produced improved cap-set constructions and bin-packing heuristics. Its interpretable programs allowed further analysis and scaling. The paper supports discovering useful structure while extending known results; it does not establish generic automatic discovery of important questions. Its reported experiments used substantial sampling and parallel resources. [Primary paper](https://www.nature.com/articles/s41586-023-06924-6)

   **Proposed adaptation:** inspect a reproduced construction for a restriction that might be relaxed, or an observed regularity that might generalize. Record the changed assumption and proposed claim precisely. There is no evidence yet that any particular relaxation identified here would be new or useful.

3. **Reproduce a claim and investigate a consequential discrepancy.** Kapoor and Narayanan document leakage failures in ML-based science and a case study in which correcting evaluation changed conclusions about model performance. This is evidence that methodological gaps can yield useful research questions, even without inventing a new model. [Primary paper](https://doi.org/10.1016/j.patter.2023.100804)

   **Proposed adaptation:** on an accessible dataset, ask whether an apparent improvement survives an appropriate split, baseline, or distribution shift. Treat the suspected flaw as a hypothesis until reproduced. A correction or negative result can contribute knowledge, but duplication of an already documented correction is not new research.

## Novelty checks and manually initiated revisits

The following is a proposed working method inferred from the resources above, not a product decision or a guarantee of novelty:

1. Write the precise unresolved claim, assumptions, scope, and desired contribution. Separate a new proof, a new bound, rediscovery of an old result, formalization, replication, and benchmark improvement.
2. Locate the original statement and closest known results. Search exact wording, alternate names, equivalent formulations, bibliographies, subsequent papers, and relevant code. For integer sequences, search terms and related entries; for graphs, search existing examples as well as theorem names.
3. Record what was checked, when, and where the evidence stops. Prefer “no resolution located in these sources as of this date” over an unconditional novelty claim. Record contradictions between sources instead of choosing the most exciting status.
4. Before committing a substantial run or announcing a result, manually repeat the targeted status and literature checks. Also check upstream attempts or collaboration markers where available; they indicate potential overlap, not exclusive ownership of an idea.
5. On return, compare the earlier upstream revision with current evidence: statement changes, solved-status updates, better bounds, new dataset versions, revised metrics, or relevant model/tool capability evidence. Retain both the earlier assessment and the reason it changed. A newly released model is a reason to reassess feasibility, not proof that an old failed attempt will now succeed.

Useful provenance would include canonical URL and identifier, original authors, access date, upstream edit date or commit, exact open subquestion, nearest result, access requirements, dataset/tool versions, evaluation route, and unresolved learning needs. This is evidence about information worth retaining, not a proposed database schema.

## Coverage, uncertainty, and follow-on decisions

The survey answers where to begin looking across mathematics, combinatorial optimization, general ML, and computational biology. It supplies concrete examples of public assets and three documented discovery methods. No data pipelines, solver runs, training jobs, or proofs were executed. Hardware feasibility and novelty remain unassessed for individual attempts. Several pages were accessible only through search-indexed primary-source text or accompanying repositories; snapshot dates therefore matter, and no catalog-wide current counts are relied upon.

License coverage was established where primary sources stated it; blanket redistribution terms remain unresolved for House of Graphs and MIPLIB, and original papers/datasets may differ from their surrounding repository's terms. Public availability alone was not treated as permission to relicense or bundle material.

Concrete decisions this evidence enables, without settling them:

- Which contribution types should an initial trial compare, and what evidence makes each worth attempting?
- How should the operator acquire enough background to inspect assumptions, evaluate novelty, and understand the limits of the result? Educational support is relevant across every surveyed domain; its form remains open.
- What minimum evidence makes a candidate ready for investigation, including freshness of the status check and access to a meaningful validator?
- Which small, concrete candidates should be used to test the workflow before choosing shared harness infrastructure?

These can feed the map's assessment, evaluation, candidate-entry, and research-session decisions. This report does not require a website, claim system, general solver, or first-domain selection to answer its bounded research question.
