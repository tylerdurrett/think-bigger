# Assessing agent research results

Researched 2026-09-07 for [What evidence can credibly assess an agent's research results?](https://github.com/tylerdurrett/think-bigger/issues/4). Primary sources were checked on that date. This is a bounded assessment of options, not a chosen evaluation policy or a claim that any candidate problem has been solved. No training or investigation was run.

## Answer

Accessible success tests can be formal, computational, statistical, or learned. A useful distinction is **what a test's evidence supports**: choosing the next attempt, measuring progress, or establishing a contribution. Determinism is neither necessary for credible empirical evidence nor sufficient to establish that the right problem was solved. The comparison below is a synthesis of the cited sources; proposed practices and example investigations are explicitly planning inferences.

| Approach | Guiding search | Measuring progress | Supporting a final claim |
| --- | --- | --- | --- |
| Formal proof or exact certificate | Check proposed steps or candidates; failed checks give feedback | Accepted sub-results, with assumptions visible; partial proofs do not imply proximity to completion | Establish the precisely stated formal result under audited assumptions; separately establish its correspondence to the intended question and its novelty |
| Reproducible computation and statistical tests | Cheap experiments, simulations, development data | Compare with fixed baselines on held-out cases, with uncertainty | Support a bounded empirical claim on the stated population, workload, or simulation; broader claims require corresponding evidence |
| Prompted or trained evaluator | Rank attempts, identify defects, allocate expensive checks | Validated scores on cases withheld from evaluator and solver development | Support claims about measured properties within the evaluator's demonstrated validity; high scores alone do not establish a scientific discovery |

## Formal and deterministic checking

Lean's kernel checks proof terms, including terms produced by tactics. Its axiom audit matters: `sorry` introduces `sorryAx`, and additional axioms can make false statements provable. A successful build is consequently weaker evidence than a checked theorem with inspected dependencies. Native computation can also enlarge the trusted components; record the toolchain and examine the reported assumptions. [Lean reference](https://lean-lang.org/doc/reference/latest/), [axioms](https://lean-lang.org/doc/reference/latest/Axioms/).

**Example investigation, not a nominated open problem:** an agent searches for a proof of a mathematical statement already expressed in Lean. The final artifact contains the original statement, a proof, dependencies, and a repeatable checking command. Planning inference: keep the statement fixed while searching and check the English-to-formal correspondence separately. Otherwise the agent can successfully prove an easier statement. An exact finite enumeration can similarly certify a bounded claim only when coverage and the checker are justified; testing many examples of an unbounded conjecture is evidence for exploration, not its proof.

**Access and compute:** Lean provides a public local installation route through its editor extension. Basic checking does not require model training or a GPU. The latter is an engineering inference about the checker, not a measured resource guarantee for arbitrary proofs: memory and checking time depend on the theorem and libraries, while agent search may dominate costs. [Official installation](https://lean-lang.org/install/).

## Reproducible computational and statistical assessment

Scikit-learn documents test-set leakage from preprocessing and model selection, along with pipelines that fit transformations on training folds. Its cross-validation guide provides grouped and temporal splitting for dependent observations. These tools make a repeatable numerical result possible, but the split must represent the intended use. [Leakage guidance](https://scikit-learn.org/stable/common_pitfalls.html), [cross-validation](https://scikit-learn.org/stable/modules/cross_validation).

SciPy implements permutation tests and bootstrap confidence intervals for custom statistics. Permutation validity depends on the chosen null hypothesis and permitted rearrangements; exhaustive permutation can be impractical. Bootstrap intervals also depend on the sampling design. Inference: ordinary row resampling or shuffling is inappropriate when it breaks important temporal or group dependence. Use a justified design, report effect size and uncertainty, and preserve code, data versions, random seeds, environment, and all attempted variants. [Permutation tests](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.permutation_test.html), [bootstrap](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.bootstrap.html).

Repeatedly consulting a holdout while selecting hypotheses can compromise its validity. Work on the reusable holdout demonstrates that adaptive analysis requires special treatment. A simple planning option is a development set for agent feedback and a reserved confirmation set; once the latter informs another revision, record that it has become development evidence. For many comparisons or sequential stopping, specify the relevant statistical treatment for that investigation. No single confidence threshold is appropriate to select here. [Authors' account of adaptive analysis](https://research.google/blog/the-reusable-holdout-preserving-validity-in-adaptive-data-analysis/).

**Example investigation:** evaluate a proposed demand-prediction method using the public UCI Bike Sharing data. The dataset includes 2011–2012 rentals, weather, and calendar variables, with a roughly 1.1 MB hourly CSV and CC BY 4.0 licensing. It also includes casual and registered counts whose sum is the total target. Inference: using those same-period components to predict the total would leak the answer; using observed future weather for a forecast would misstate what information is available. A temporally separated comparison with a simple baseline could support an improvement on this historical workload. It would not by itself show a novel method, present-day generalization, or an actual transport benefit. [Dataset and schema](https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset).

**Access and compute:** this example uses downloadable data and public Python tooling, with no new physical experiment. A small baseline and statistical comparison are plausibly CPU-scale given the data size; that is an estimate, not a benchmark run. The work required to establish a novel contribution may be much greater than this validation demonstration.

## Learned judges, including training our own

The MT-Bench study found strong agreement with human preferences in its studied setting, while documenting position, verbosity, self-enhancement, and reasoning weaknesses. That is evidence that a judge can be useful, not that preference agreement certifies research correctness. [Original study, 2023](https://arxiv.org/abs/2306.05685).

Prometheus 2 provides an accessible example of a specialized judge supporting custom rubrics, direct scores, and pairwise comparisons. Its evidence concerns response-evaluation benchmarks; its public datasets include model-generated feedback. Neither benchmark correlations nor synthetic labels establish validity on a new scientific domain. [Prometheus 2, 2024](https://arxiv.org/html/2405.01535v2), [public evaluator code](https://github.com/prometheus-eval/prometheus-eval).

**Example investigation:** develop a judge that screens proposed computational explanations for particular errors, then test whether its rankings reduce the number of expensive independent checks needed to find valid candidates. Training labels might come from execution outcomes, known cases, or publicly available verified annotations. This is a planning inference, not an existing demonstrated result. A useful contribution could be a validated evaluator itself. When the labels only express another model's preferences, the demonstrated achievement may instead be distilling that preference signal.

Public tooling supports this experiment: TRL's versioned reward-modeling documentation describes chosen/rejected response pairs, a small-model example, and PEFT adapter training. A numeric reward measures learned preference; it is not automatically a probability of correctness. A narrow classifier on task features may also suffice, depending on the target property. [TRL reward modeling](https://huggingface.co/docs/trl/v1.12.0/en/reward_trainer).

### Evidence needed to validate a judge

The following is a proposed investigation checklist inferred from these sources, not a universal product requirement:

1. **Specify the property and the label source.** Distinguish factual correctness, preference, usefulness, and novelty. Establish why the reference labels deserve trust, including their uncertainty. An operator unfamiliar with a field can inspect provenance and known examples; their confidence alone does not create domain ground truth.
2. **Separate development and assessment.** Withhold entire problem families, documents, time periods, or other relevant groups where near-duplicate items would leak. Keep calibration data separate from the final test. For opaque pretrained models, unknown pretraining overlap remains an uncertainty even after local train/test separation. [Data separation](https://scikit-learn.org/stable/common_pitfalls.html), [Prometheus transparency discussion](https://arxiv.org/html/2405.01535v2).
3. **Measure relevant errors.** Compare the judge with simple baselines on representative cases, difficult negatives, and known failures. Report false acceptance and false rejection where applicable, uncertainty, and performance by problem type. Test whether scores predict the independently assessed outcome that matters, not merely whether two agents agree.
4. **Check probability claims.** If output scores are used as confidence, assess reliability against withheld labels and fit calibration on separate data. Reliability diagrams compare predicted probabilities with observed frequencies. Brier/log loss measure more than calibration alone. Ranking accuracy and a rubric score do not supply calibrated certainty. [Calibration documentation](https://scikit-learn.org/stable/modules/calibration.html).
5. **Challenge presentation sensitivity and feedback exploitation.** Swap answer order, vary verbosity while preserving content, remove model identities, and include fluent wrong answers. Check performance again on candidates optimized against the judge. Reward-overoptimization research shows proxy gains can coincide with declines on a separate gold reward; its synthetic setup is evidence of the mechanism, not a measured failure rate for this project. [Judge biases](https://arxiv.org/abs/2306.05685), [overoptimization study](https://arxiv.org/abs/2210.10760).
6. **Make independence substantive.** A different model or fresh agent session is not proof of independent errors. Prefer evidence with a distinct basis when available: execution, independent labels, withheld measurements, or another validated method. Preserve disagreements and allow an inconclusive result. Multiple judges can be a useful diagnostic without establishing truth by majority vote.

If accessible labels or outcomes cannot validate the intended property, the judge may still guide exploration. The final claim must reflect that limitation. This leaves probabilistic evaluation fully in scope without requiring an outside collaborator to bless every attempt.

### Dated feasibility evidence

| Route | Public evidence checked 2026-09-07 | Practical limit |
| --- | --- | --- |
| Use an existing open judge | Prometheus 2's 7B model card publishes weights under Apache 2.0 and local loading examples | An approximate 7B model needs about 14 GB for 16-bit weights alone, by arithmetic; runtime memory and compute are additional. This is not a tested device requirement. [Model card](https://huggingface.co/prometheus-eval/prometheus-7b-v2.0) |
| Train a small judge or adapters | TRL documents small-model reward training and adapter support | Feasible route to prototype, not evidence of domain accuracy. Data quantity, context length, batch size, activations, optimizer, and device support determine resources. [TRL](https://huggingface.co/docs/trl/v1.12.0/en/reward_trainer) |
| Quantized adapter training | QLoRA's 2023 paper reports 65B fine-tuning on one 48 GB GPU | Demonstrates a memory-saving method; it is not a promise about our judge, workload, hardware, or training duration. [QLoRA](https://arxiv.org/abs/2305.14314) |
| Reproduce a published large judge recipe | Prometheus 2 reports eight 40 GB A100 GPUs and about 800 GPU-hours for training | A substantially larger undertaking than loading its released model. Its dataset terms differ from its model license. [Training and licensing appendices](https://arxiv.org/html/2405.01535v2#A2) |

The operator's available hardware and spending limits are unknown. No cloud account, special allocation, model subscription, or current frontier-model capability is assumed. Benchmark throughput and memory for the actual candidate before proposing training expenditure; public availability and personal feasibility are separate facts.

## What is answered and what remains

**The bounded question is answered:** accessible options support credible evidence beyond deterministic testing, and custom evaluators are a plausible subject of an investigation. The sources establish techniques and known limitations, not a ready-made judge for arbitrary novel research.

Necessary follow-on decisions belong with a concrete candidate: the exact claim and population; the success test and trustworthy reference evidence; acceptable error and uncertainty; how adaptive feedback is separated from confirmation; and an affordable pilot on available hardware. None requires a universal threshold or a general harness to be selected now.

Unresolved empirical questions are whether a selected judge transfers to the eventual domain, whether available labels cover the relevant failures, how much model/data contamination exists, and what computation that investigation needs. Correctness, novelty, importance, and newsworthiness remain distinct assessments. A success test can contribute to the first without establishing the others.
