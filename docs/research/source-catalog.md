# Curated sources and problem lists for the default search

Research date: 2026-09-08. Prepared for [Which curated sources and problem lists should the workflow search by default?](https://github.com/tylerdurrett/think-bigger/issues/14).

This catalog extends the seven resources surveyed in [Opportunity discovery](opportunity-discovery.md) (Erdős Problems, OEIS, House of Graphs, CSPLib, MIPLIB 2017, OpenML, Open Problems in Single-Cell Analysis). Those seven are referenced, not re-surveyed. Every page below was checked on 2026-09-08 unless a section says otherwise; last-update evidence is quoted from the page itself. The catalog is a starting set for prior-work review and candidate discovery, not a boundary on where the workflow may look. It does not select a first domain or certify any problem as open.

## Findings

Maintained sources with an explicit, dated representation of unresolved status are concentrated in a few places: the Kourovka Notebook's arXiv editions, Google DeepMind's Formal Conjectures repository, the Electronic Journal of Combinatorics dynamic surveys, the Waterloo TSP instance pages, and the Global Benchmark Database for SAT. Several classic lists still index useful problems but are stale or degraded: Open Problem Garden's recent activity is spam, Douglas West's page calls itself "long neglected", and QAPLIB, SteinLib, and TSPLIB have not changed in over a decade. Stale lists remain useful as leads for the rediscovery hunt because the problems they name are searchable elsewhere; they are unreliable as a status oracle.

Indexes that record AI-assisted results now exist but are fragmented. The community wiki of AI contributions to Erdős problems was frozen on June 30, 2026, and discussion moved to a forum thread that was active today. Epoch AI publishes two trackers with per-problem solved-by-AI status and dates. The Kourovka Notebook's September 2026 revision notes solutions "obtained using AI". Formal Conjectures marks solved conjectures with a formal-proof pointer but does not label who or what produced the proof. No source certifies AI provenance uniformly; each records it in its own vocabulary.

For citation chasing in both directions, Semantic Scholar's citations and references endpoints worked unauthenticated today, OpenAlex now meters usage in dollars with a free daily budget, Crossref and OpenCitations are free with published limits, zbMATH Open's REST and OAI-PMH interfaces answered without credentials, and dblp was blocked by a bot-challenge page from this environment. Google Scholar has no API and disallows crawling of its search paths. Papers With Code shut down in July 2025; its last snapshot is archived on Hugging Face under CC-BY-SA-4.0. MathSciNet remains subscription-only, with a free MR Lookup tool for citation matching.

Coverage gaps: no maintained open-problem index with status was found for physics simulation or for machine-learning methodology; computational biology offers dated challenge rounds (CASP, DREAM) rather than status lists.

## At a glance

| Source | Domain | Unresolved-status representation | Last-update evidence seen 2026-09-08 | Main use | Records AI results? |
|---|---|---|---|---|---|
| Open Problem Garden | graph theory, algebra, combinatorics | "Solved problems" view; importance stars; posted date | legitimate content about 2 years old; spam 10 weeks old | leads for rediscovery | no |
| Kourovka Notebook (arXiv) | group theory | numbered problems with comments; new solutions per revision | v46, 2026-09-01 | rediscovery and discovery | yes, noted in v46 comments |
| MathOverflow `open-problems` | all mathematics | `is_answered`, accepted answers; tag wiki | questions dated 2026-08-28 | rediscovery ("is this known?") | no |
| Wikipedia unsolved-problem lists | math, CS, physics | "solved since" sections (math); none (CS) | revisions 2026-09-08 (math), 2026-03-27 (CS), 2026-09-07 (physics) | index only | no |
| Clay Millennium Problems | seven named problems | six unsolved, one solved | © 2026 page | definitional index | no |
| Ben Green, "100 open problems" | additive combinatorics, number theory | "Update YYYY" remarks; numbering kept when solved | "Most recent update: December 2025" | discovery and rediscovery | no |
| EJC Dynamic Surveys | combinatorics (Ramsey, labeling, colouring) | tables of known values and bounds; dated revisions | DS1 2026-04-24; DS25 2026-07-03 | rediscovery of bounds; discovery of open cells | no |
| AIM Problem Lists (AIMPL) | workshop problem lists across mathematics | editor remarks; archived versions | no dates on index; deep links live | discovery leads | no |
| Douglas West, open problems | graph theory, combinatorics | inconsistent "PROVED"/"FALSE" notes | "long neglected"; 2015 references | leads only | no |
| Randomstrasse101 | probability, TCS, statistics | numbered blog problems; arXiv yearly compilation | post 2026-06-05; arXiv 2026-03-31 | discovery leads | no |
| The Open Problems Project (TOPP) | computational geometry | "Status" field; "Entry Revision History" dates | repo push 2025-06-19 (Problem 21 solved) | rediscovery and discovery | no |
| Formal Conjectures | Lean-formalized conjectures | `research open` / `research solved` tags; `formal_proof` pointer | commit 2026-09-08 | rediscovery (statement-level) and discovery | indirectly; commit text mentions AI formalization attempts |
| Waterloo TSP collections, TSPLIB | TSP instances | "Optimal" vs gap percentage; dated best tour and bound | World TSP tour 2025-10-17; VLSI page 2017-05-03; TSPLIB frozen 2013-01-01 | discovery of open instances | no |
| GBD and SAT Competition | SAT instances | result SAT/UNSAT/Unknown; `verified-result`; competition year | SAT 2026 instances tagged and results posted | discovery of unknown-result instances | no (SAT 2026 has an "AI generated" sub-track) |
| DIMACS Implementation Challenges | algorithm engineering | none explicit; challenge instance sets | 13th challenge 2026–27 | discovery of instance sets | no |
| QAPLIB, SteinLib, Mittelmann, MiniZinc Challenge | optimization instances | OPT vs heuristic markers (QAPLIB); optimal values (SteinLib) | QAPLIB 2012-04-20; SteinLib 2015-03-30; Mittelmann 2026-08-20; MiniZinc 2026 | discovery of open instances; solver capability | no |
| erdosproblems AI wiki and forum | Erdős problems | colour-coded outcome per AI contribution | wiki frozen 2026-06-30; forum post 2026-09-08 | rediscovery of AI attempts | yes |
| Epoch AI FrontierMath trackers | selected open problems | Solved (AI), Solved (human), Unsolved; dated changes | 2026-08-12 status change; 2026-09-01 announcement | rediscovery of AI attempts | yes |
| AlphaEvolve results; Equational Theories | constructions; magma implications | improvements over prior best; 100% complete graph | commit 2026-01-05; paper 2025-12-16 | precedent index | yes |
| CASP, DREAM, math-bio survey | computational biology | challenge rounds; no status list | CASP17 2026; DREAM posts 2026-06-29 | discovery via benchmark rounds | no |
| Papers With Code archive; interpretability survey | ML methodology | leaderboards (frozen); survey without status | snapshot 2025-07-28; paper 2025-01-27 | rediscovery of baselines | no |

## Mathematics problem collections

### 1. Open Problem Garden

**Provenance.** A Drupal site of crowd-submitted problems; today's footer credits the "CSI of Charles University" and distributes content under the GNU Free Documentation License. Subject counts shown today: algebra 298, graph theory 227, number theory 49, topology 40, combinatorics 35, geometry 29, theoretical computer science 13. [Home page](https://openproblemgarden.org/), [area listing](https://openproblemgarden.org/container/area)

**Status and dates.** Each problem page carries "Importance" stars, "Recomm. for undergrads", "Posted by" with a date, a revisions link, and comments; the [Erdős–Hajnal page](https://openproblemgarden.org/op/the_erdos_hajnal_conjecture) shows "Importance: High ✭✭✭" and a March 18th, 2007 posting date. Resolved problems move to a separate [Solved problems view](https://openproblemgarden.org/?q=view/solved), which lists titles, importance, and area but shows no resolution date or solver. The area listing links to that view with "Resolved problems from this section may be found in Solved problems."

**Access and license.** Public, no API; GFDL per the footer. The `www.` host did not resolve from this environment today; the bare domain served the site.

**Searching for a claim.** Site search and the sortable area listings; no structured export. Because the solved view is undated, treat "open" here as a lead to verify elsewhere.

**Best use and maintenance.** Rediscovery leads and undergraduate-recommended candidates. The [recent-activity tracker](https://openproblemgarden.org/tracker) today listed gaming-cheat spam posted "10 weeks 6 days ago" under the "Open problem" type; the most recent mathematical entry, "Nowhere-zero flows", was "2 years 2 weeks ago". The site appears unmoderated at present.

### 2. Kourovka Notebook (Unsolved Problems in Group Theory)

**Provenance.** Edited by E. I. Khukhro and V. D. Mazurov; the arXiv abstract describes "a collection of open problems in group theory proposed by hundreds of mathematicians from all over the world", published every 2–4 years since 1965, now in its 21st edition with 150 new problems and comments on earlier problems. [arXiv 1401.0300](https://arxiv.org/abs/1401.0300)

**Status and dates.** Status is carried in the numbered problems' comments, revised per arXiv version; v1 is dated January 1, 2014 and v46 September 1, 2026. The v46 comments say there are "quite a few new solutions added in this update, including some solutions obtained using AI." [v46 listing](https://arxiv.org/abs/1401.0300v46)

**Access and license.** Free PDF on arXiv under arXiv's non-exclusive distribution license (shown on the abstract page). The project site kourovka-notebook.org timed out on two attempts today; the arXiv copy is the reliable route.

**Searching for a claim.** Text search of the PDF by problem number, proposer, or keyword; there is no API. Compare consecutive versions to date a status change.

**Best use and maintenance.** Both rediscovery and discovery in group theory; actively maintained (46 revisions, latest one week before this check). It is one of the few classic notebooks that names AI-assisted solutions explicitly.

### 3. MathOverflow `open-problems` tag (and cstheory `open-problem`)

**Provenance.** Community Q&A. The tag wiki says: "If it turns out that a problem is equivalent to a known open problem, then the open-problem tag is added. After that, the question essentially becomes, 'What is known about this problem? ...'". Queried through the Stack Exchange API today, the tag had 606 questions. [Tag wiki via API](https://api.stackexchange.com/2.3/tags/open-problems/wikis?site=mathoverflow), [tag info via API](https://api.stackexchange.com/2.3/tags/open-problems/info?site=mathoverflow)

**Status and dates.** Each question exposes `creation_date`, `is_answered`, and `accepted_answer_id`; the three newest today (2026-08-27 and 2026-08-28) were unanswered. Items carry `content_license: CC BY-SA 4.0`. The cstheory site's `open-problem` tag had 84 questions. [cstheory tag info](https://api.stackexchange.com/2.3/tags/open-problem/info?site=cstheory)

**Access and license.** CC BY-SA 4.0 content. API throttles: more than 30 requests per second from one IP is cut off; without a key the IP-shared quota observed today was 300 per day (`quota_max: 300`); with a registered key the default daily quota is 10,000; responses may carry a `backoff` field that must be honoured. [Throttle documentation](https://api.stackexchange.com/docs/throttle). Direct fetches of mathoverflow.net were blocked from this environment; the API host answered.

**Searching for a claim.** `/search/advanced` with `tagged=open-problems` and a title query, or full-text search on the site; check answers and comments for "this was solved in ..." notes, which are the site's usual status signal.

**Best use and maintenance.** Rediscovery. The tag's purpose is literally to ask whether a problem is known and what is known about it; it is also a good place to find recent statements of problems that the maintained lists have not absorbed.

### 4. Wikipedia lists of unsolved problems (index, not source)

**Provenance.** Editable encyclopedia lists. The mathematics list aggregates Hilbert (23, 13 unsolved), Millennium (7, 6 unsolved), Smale (18, 14 unsolved), and Erdős problems (">1220", "634 unsolved" at the time of the page text), plus notebooks (Kourovka, Sverdlovsk, Dniester) and a "problems solved since 2015" section. [Mathematics list](https://en.wikipedia.org/wiki/List_of_unsolved_problems_in_mathematics)

**Status and dates.** Latest revisions via the MediaWiki API today: mathematics 2026-09-08T15:57Z (revision 1373894071), computer science 2026-03-27 (1345711618), physics 2026-09-07 (1373709508). The computer-science list carries no solved dates and treats all entries as open. [Revision query](https://en.wikipedia.org/w/api.php?action=query&prop=revisions&titles=List_of_unsolved_problems_in_mathematics|List_of_unsolved_problems_in_computer_science|List_of_unsolved_problems_in_physics&rvprop=timestamp|ids&format=json), [computer-science list](https://en.wikipedia.org/wiki/List_of_unsolved_problems_in_computer_science)

**Access and license.** CC BY-SA text; full API.

**Searching for a claim.** Search the list and its history for the problem name; follow the references, never the list's own status, since edits are unreviewed.

**Best use and maintenance.** Index to other lists and to the names under which a problem is discussed. Active but uncited status claims should be treated as leads.

### 5. Clay Millennium Prize Problems

**Provenance.** The Clay Mathematics Institute's seven problems, announced May 24, 2000, with a $1 million prize each; the page lists six unsolved and the Poincaré conjecture solved. Rules are on a linked page. [Millennium problems](https://www.claymath.org/millennium-problems/)

**Status and dates.** Binary, institution-adjudicated status; the page carries a "© 2026" notice and no per-problem status dates.

**Access and license.** Public web page; copyright CMI.

**Searching for a claim.** Not needed as a search target; it defines seven problem names that other sources use. Claims about Navier–Stokes in September 2026 are covered in [Recent contributions, May–September 2026](recent-contributions-2026.md) and were not re-verified here.

**Best use and maintenance.** Definitional index only; no discovery role for this project.

### 6. Ben Green, "100 open problems"

**Provenance.** An author-hosted PDF: "This collection of open problems has been circulated since 2018", expanded from a manuscript circulated among students from 2013. Sections cover sum-free sets, arithmetic progressions, sumsets and bases, Sidon sets, covering and packing, sieving, additive combinatorics, additive and combinatorial number theory, discrete geometry, nonabelian questions, harmonic analysis, and miscellany. [PDF](https://people.maths.ox.ac.uk/greenbj/papers/open-problems.pdf)

**Status and dates.** The text says updates come "perhaps once a year or so. Most recent update: December 2025", that "I intend to keep the original numbering even if problems are completely solved", and status changes appear as dated remarks such as "Update 2025. Bedert [28] has solved the original question". A 2025 remark notes that erdosproblems.com "now contains discussion forums for each problem".

**Access and license.** Free download; no license statement in the document.

**Searching for a claim.** Text search of the PDF; solved problems remain in place with an "Update" remark, so a hit does not imply the problem is open.

**Best use and maintenance.** Discovery and rediscovery in additive combinatorics; maintained by a single author on an annual cadence.

### 7. Electronic Journal of Combinatorics Dynamic Surveys

**Provenance.** The journal's dynamic surveys are revised in place. Today's index lists 28 surveys with revision dates, including DS1 "Small Ramsey Numbers" (Radziszowski; latest revision April 24, 2026, first published August 1, 1994), DS6 "Graph Labeling" (Gallian; October 30, 2025), DS25 on colouring squares of graphs (Cranston; July 3, 2026), DS27 on generalized Turán problems and DS28 (both February 13, 2026), DS10 (February 14, 2025), and DS20 (March 14, 2025). Several others have not been revised since the 2000s. [Dynamic surveys index](https://www.combinatorics.org/ojs/index.php/eljc/issue/view/Surveys), [DS1](https://www.combinatorics.org/ojs/index.php/eljc/article/view/DS1)

**Status and dates.** Surveys such as DS1 tabulate "all known nontrivial values and bounds" with citations, so an unknown value is a visible gap between bounds, dated by the survey revision.

**Access and license.** Open access; the journal states it is "free for both authors and readers" and leaves copyright with authors; no Creative Commons license is stated on the About page. [About the journal](https://www.combinatorics.org/ojs/index.php/eljc/about)

**Searching for a claim.** Search the survey PDF for the parameter or graph family; compare the revision date against the claim's date.

**Best use and maintenance.** Rediscovery of the current best bound and discovery of open cells in bound tables; maintenance varies by survey, so check the revision date rather than the journal.

### 8. AIM Problem Lists (AIMPL)

**Provenance.** The American Institute of Mathematics indexes roughly 150 workshop problem lists across 23 categories; about 60 link to the aimpl.org platform and the rest to PDFs or other documents. [Index](https://aimath.org/problemlists/)

**Status and dates.** A list page (checked with curl) shows an editor, numbered sections, "Archived versions", a "Cite this as" line, and a footer stating information is released under the Creative Commons Attribution-ShareAlike license; page permissions allow logged-in users to add remarks. No explicit open/solved flag or date was visible on the list or index pages. [Example list](http://aimpl.org/aagaautomorphic/)

**Access and license.** CC BY-SA per the list footer. Today the aimpl.org root redirected to aimath.org and the HTTPS certificate was reported expired by the fetch tool; HTTP deep links resolved.

**Searching for a claim.** Browse by category; text search within each list's PDF or LaTeX export.

**Best use and maintenance.** Discovery leads from expert workshops; status must be established elsewhere.

### 9. Douglas West, "Open Problems - Graph Theory and Combinatorics"

**Provenance.** Over 100 problems in four sections (extremal, structure, order and optimization, arrangements and methods). The maintainer's note calls the page "now long neglected". [Page](https://dwest.web.illinois.edu/openp/)

**Status and dates.** Occasional markers ("PROVED", "FALSE", "This has been proved by Torsten Mütze"), otherwise none; cited arXiv items date to 2015. The older faculty.math.illinois.edu host refused connections today.

**Access and license.** Public page; no license statement.

**Searching for a claim.** Text search only.

**Best use and maintenance.** Leads only; stale.

### 10. Randomstrasse101

**Provenance.** A blog "dedicated to Open Problems in Mathematics, with a focus on Probability Theory, Computation, Combinatorics, Statistics, and related topics", with a yearly arXiv compilation ("Randomstrasse101: Open Problems of 2025", Bandeira, Dmitriev, Lucca, Nizić-Nikolac, Rödder, submitted March 31, 2026) intended as "a stable record". [Blog](https://randomstrasse101.math.ethz.ch/), [arXiv 2603.29571](https://arxiv.org/abs/2603.29571)

**Status and dates.** Problems are numbered (7–38 visible today) and grouped into dated posts; the latest post is June 5, 2026. No solved marking was observed on the front page or in the abstract.

**Access and license.** Public blog; arXiv compilation under arXiv's license.

**Searching for a claim.** Blog tags and text search; the arXiv record for citation.

**Best use and maintenance.** Discovery leads in probability and computation; active in 2026.

## Theoretical computer science and formal mathematics

### 11. The Open Problems Project (TOPP)

**Provenance.** Edited by Erik Demaine, Joseph Mitchell, and Joseph O'Rourke; over 75 computational-geometry problems in about 40 categories, grown from 30 in 2001. The site "is no longer encouraging new problem submissions" but "strongly encourage[s] updates to existing problems, especially when those problems have been solved". [Site](https://topp.openproblem.net/)

**Status and dates.** Each entry has Statement, Origin, Status/Conjectures, Partial and Related Results, Appearances, an "Entry Revision History" with dated edits, and a bibliography; Problem 1 records "Just solved by Wolfgang Mulzer and Günter Rote, January 2006!" with an edit dated 3 Jan. 2006. [Problem 1](https://topp.openproblem.net/p1)

**Access and license.** Public site built from a GitHub repository whose last push was June 19, 2025 with the commit "Update Problem 21 (now solved!)"; GitHub reports the license as `NOASSERTION`, so reuse terms are unstated. [Repository](https://github.com/edemaine/topp), [latest commit](https://api.github.com/repos/edemaine/topp/commits?per_page=1)

**Searching for a claim.** Browse categories or grep the repository's `Problems/` files and `topp.bib`.

**Best use and maintenance.** Rediscovery and discovery in computational geometry; updates arrive by pull request at a slow but non-zero rate.

### 12. Formal Conjectures (Google DeepMind)

**Provenance.** A Lean 4 collection of formalized conjectures, intended as a benchmark for automated provers and as a way to clarify statements; dual-licensed Apache-2.0 (software) and CC-BY-4.0 (other material), with third-party content under its original license. [Repository](https://github.com/google-deepmind/formal-conjectures)

**Status and dates.** Every statement carries exactly one `@[category]`: `research open` ("an unsolved open mathematical problem or conjecture for which no solution or proof is currently accepted"), `research solved`, `textbook`, `API`, or `test`. When a problem is solved, contributors change the tag to `research solved` and add `@[formal_proof using <kind> at "<url>"]` where kind is `formal_conjectures`, `lean4`, or `other_system`. Benchmark snapshots are tagged `bench-v{N}-lean4.{X}.{Y}` and are immutable. AI-usage rules follow Mathlib's conventions. [CONTRIBUTING](https://raw.githubusercontent.com/google-deepmind/formal-conjectures/main/CONTRIBUTING.md), [README](https://raw.githubusercontent.com/google-deepmind/formal-conjectures/main/README.md)

**Access and license.** Public; the latest commit today (September 8, 2026) formalizes Falconer's conjecture and its message reports that the authors "set GPT-Astra to formalise the d = 2 case" before discontinuing that attempt. The README plans "to periodically leverage AlphaProof to help identify potential misformalisations". [Latest commit](https://api.github.com/repos/google-deepmind/formal-conjectures/commits?per_page=1)

**Searching for a claim.** Grep the repository for the statement, its `@[AMS]` classification, or its source (Erdős number, Wikipedia, MathOverflow); check the category tag and the issues list (774 open issues today).

**Best use and maintenance.** Statement-level rediscovery and discovery; actively maintained. Epoch AI reports that 50 of its 68 selected Erdős problems were already formalized here (see section 18). Model names in commit messages are leads, not verified capability claims.

## Optimization, SAT, and instance libraries

### 13. Waterloo TSP collections and TSPLIB

**Provenance.** William Cook's TSP site at the University of Waterloo hosts national, VLSI, World, and art instances. [Site](https://www.math.uwaterloo.ca/tsp/index.html)

**Status and dates.** The national table (footer "Last Updated: February 8, 2022") marks instances "Optimal" or gives a gap between best tour and bound (0.012% to 0.093%) and says "We will be most happy to report any improved tours or improved lower bounds". The VLSI summary ("Last Updated: May 3, 2017") shows about 82 of 102 instances optimal and about 20 with percentage gaps. The World TSP page records a best tour of 7,515,755,912 found October 17, 2025 by Yuichi Nagata against a lower bound of 7,512,218,268 from June 5, 2007, a 0.0471% gap. [National](https://www.math.uwaterloo.ca/tsp/world/countries.html), [VLSI](https://www.math.uwaterloo.ca/tsp/vlsi/summary.html), [World](https://www.math.uwaterloo.ca/tsp/world/index.html)

**Access and license.** Public downloads; no license statement found. TSPLIB (Heidelberg) lists optimal or best-known values and states "it is not intended to add further problem instances (1.1.2013)"; no license statement. [TSPLIB](http://comopt.ifi.uni-heidelberg.de/software/TSPLIB95/)

**Searching for a claim.** Open the instance page and compare the claimed tour or bound against the dated values.

**Best use and maintenance.** Discovery of open instances with explicit, dated bounds; the World page changed in late 2025 while the VLSI and national pages have not changed for years.

### 14. Global Benchmark Database (GBD) and the SAT Competition

**Provenance.** GBD is "a comprehensive suite of tools for provisioning and sustainably maintaining benchmark instances and their metadata" for SAT, MaxSAT, and pseudo-Boolean problems, MIT-licensed, with a 2024 SAT tool paper. [Repository](https://github.com/Udopia/gbd), [web interface](https://benchmark-database.de/)

**Status and dates.** Instances carry family, author, a result status (SAT/UNSAT/Unknown), a `verified-result` feature, solver runtimes, and competition-track tags from 2002 through 2026. SAT Competition 2026 (organizers Fazekas, Heule, Iser) published instances "tagged and ready for download in the GBD", instance-wise results, and slides; tracks include an "AI Generated/AI-Tuned" sub-track. [SAT 2026](https://satcompetition.github.io/2026/), [competition index](https://satcompetition.github.io/)

**Access and license.** GBD code is MIT; the competition says benchmarks are freely downloadable but does not state instance licenses. Query via CLI (`gbd get "family = ..." -r verified-result`), a Python API returning dataframes, or the web interface.

**Searching for a claim.** Hash-identify the instance in GBD and read its result and runtime features; the competition's instance-wise results show which solvers finished it.

**Best use and maintenance.** Discovery of unknown-result instances and rediscovery of whether an instance has been solved; actively maintained through the 2026 competition.

### 15. DIMACS Implementation Challenges

**Provenance.** Thirteen challenges since 1990; the 13th (2026–2027) is "Network Flows 2.0" with instances at Lehigh's CORAL site, and older material is archived at DIMACS. [Challenge index](http://dimacs.rutgers.edu/programs/challenge/)

**Status and dates.** No explicit open/solved status; challenge instance sets and results papers define the state of the art at the challenge date.

**Access and license.** Public; no license statement on the index page.

**Searching for a claim.** Locate the challenge for the problem class and read its results and instance pages.

**Best use and maintenance.** Discovery of instance sets in the current challenge; earlier challenges are historical.

### 16. QAPLIB, SteinLib, Mittelmann benchmarks, MiniZinc Challenge

**QAPLIB.** Maintained by Peter Hahn and Miguel Anjos as of an August 2011 news item; the instance table marks proven optima "(OPT)", otherwise names the heuristic that found the best value and gives a gap "(solution – bound)/(solution)*100 %"; the footer date is 20 April 2012 and news anchors run to July 2011. No license stated. [Overview](https://coral.ise.lehigh.edu/data-sets/qaplib/), [instances](https://coral.ise.lehigh.edu/data-sets/qaplib/qaplib-problem-instances-and-solutions/)

**SteinLib.** ZIB-hosted Steiner tree instances with optimal values where known; latest update March 30, 2015 (PUC results); "Copyright ZIB 2001"; no explicit license. [SteinLib](https://steinlib.zib.de/steinlib.php)

**Mittelmann benchmarks.** Hans Mittelmann's solver benchmarks across LP, MILP, SDP, NLP, MIQP, and combinatorial optimization, with dated tables through August 20, 2026 (including a Concorde/Hexaly/LKH TSPLIB benchmark dated July 28, 2026). These measure solver capability, not open status. [Benchmarks](https://plato.asu.edu/bench.html)

**MiniZinc Challenge.** Annual through 2026; a list of all problems and globals used in past challenges is published; instance licensing is not stated. [Challenge](https://www.minizinc.org/challenge/)

**Use.** QAPLIB and SteinLib give explicit open instances but have not been updated for over a decade, so any "open" marker needs a literature check; Mittelmann's tables are the freshest evidence of what solvers can do today.

## Indexes that record AI-assisted results

### 17. erdosproblems AI-contributions wiki and forum threads

**Provenance.** The `teorth/erdosproblems` GitHub wiki "collects contributions of AI systems to the understanding of Erdős problems". Its home page states: "The wiki is no longer updated. The latest data is as of Jun 30, 2026." The page history shows a "freeze" commit on June 30, 2026. [Wiki home](https://github.com/teorth/erdosproblems/wiki), [AI contributions page](https://github.com/teorth/erdosproblems/wiki/AI-contributions-to-Erd%C5%91s-problems), [history](https://github.com/teorth/erdosproblems/wiki/AI-contributions-to-Erd%C5%91s-problems/_history)

**Status and dates.** Contributions are classed 1(a) AI standalone, 1(b) alongside literature, 1(c) building on literature, 1(d) collaborating with humans, and 2(a)–(d) literature search, formalization, rewriting, computational verification; outcomes are marked green (full resolution), yellow (partial), red (incorrect), white (unverified). Each entry records problem number, AI system, date, outcome, and human involvement. A "Notable cases" page lists problems 1026 (December 2025), 728 (January 2026, "the first autonomous and nontrivial solution to an Erdős problem by AI systems"), 1196 (April 2026), and 90 (May 2026) without naming systems or recording formal verification. [Notable cases](https://github.com/teorth/erdosproblems/wiki/Notable-cases-of-AI-contributions-to-Erd%C5%91s-problems)

**After the freeze.** On erdosproblems.com, the pinned "AI Contributions" thread (Thomas Bloom, 27 Dec 2025) is marked "Now archived - please use the new thread"; the successor "AI Contributions 2" thread (pinned 13 Jul 2026) had 364 dated posts through 8 Sep 2026 when read with curl today. These are discussion, not a structured index. [Thread 1](https://www.erdosproblems.com/forum/thread/AI%20Contributions), [Thread 2](https://www.erdosproblems.com/forum/thread/AI%20Contributions%202)

**Rediscovery evidence.** The "Early science acceleration experiments with GPT-5" paper (submitted November 20, 2025) reports that the Erdős index held "685 'open' problems out of 1105 total as of October 31, 2025" and that the model located previously published solutions to ten problems "not previously marked as known" (223, 339, 494, 515, 621, 822, 883 part 2, 903, 1043, 1079), with references "generally accurate and easy to verify manually". This is direct evidence that a maintained list can carry "open" markers for problems already solved in the literature. [arXiv 2511.16072](https://arxiv.org/html/2511.16072)

**Best use.** Checking whether an Erdős problem has already been attempted by an AI system and how the outcome was judged; the frozen wiki is a dated snapshot and the forum is unstructured.

### 18. Epoch AI FrontierMath Open Problems and FrontierMath Erdős

**Provenance.** Epoch AI, supported by Schmidt Sciences, maintains "FrontierMath: Open Problems", 50 unsolved problems verified by bespoke checker programs; access to verifiers is sold, and the page says only OpenAI has purchased it. [Open Problems](https://epoch.ai/frontiermath/open-problems)

**Status and dates.** Per-problem status is Solved (AI), Solved (human), or Unsolved (6, 1, and 43 today) with notability tiers; the page requires that "core ideas of the solution be unambiguously contributed by AI". The latest change, August 12, 2026, marked a Hadamard-matrix problem solved by AI with a provisional note pending details of human contributions. A September 1, 2026 announcement introduced "FrontierMath Erdős": 68 Erdős problems selected by Thomas Bloom as of August 2026 (about 10% of "652 unsolved problems cataloged on erdosproblems.com"), verified by Lean formalization; 50 were already in Formal Conjectures and 18 were formalized by AI. In its standardized run, two of 68 were solved by one model and none by four others; the announcement names specific models, which this report treats as leads. [FrontierMath Erdős announcement](https://epoch.ai/latest/announcing-frontiermath-erdos)

**Access and license.** Status pages are public; problem verifiers are not.

**Searching for a claim.** Scan the status table for the problem; the dated change log is the useful part.

**Best use.** Rediscovery of AI attempts on a small, curated set; useful as an example of dated, adjudicated status with an explicit AI-provenance bar.

### 19. AlphaEvolve results and the Equational Theories Project

**AlphaEvolve results.** A Google DeepMind repository (Apache-2.0 code, CC-BY-4.0 other material) holding a notebook of constructions where the system "outperforms the state-of-the-art", deliberately excluding matched results; last commit January 5, 2026 ("Fixed metadata typo"). It documents improvements, not open problems. [Repository](https://github.com/google-deepmind/alphaevolve_results), [latest commit](https://api.github.com/repos/google-deepmind/alphaevolve_results/commits?per_page=1)

**Equational Theories Project.** Apache-2.0; its dashboard reports the implication graph "100.00000% complete" with zero unresolved implications among 22,028,942, and the project paper (submitted December 8, 2025, revised December 16, 2025) states the team "successfully determined all 22 028 942 edges" using "a combination of human-generated and automated proofs ... all validated by the formal proof assistant language Lean". [Repository](https://github.com/teorth/equational_theories), [dashboard](https://teorth.github.io/equational_theories/dashboard/), [arXiv 2512.07087](https://arxiv.org/abs/2512.07087)

**Use.** Neither is a discovery list now; both are precedents for how a community index records solved status and automated contributions, and AlphaEvolve's notebook is a rediscovery check for construction-type claims.

## Other computationally accessible fields

### 20. Computational biology: CASP, DREAM, and a dated survey

**CASP.** The Prediction Center reports CASP17 (2026) with "approximately 20 targets still in prediction", public targets, predictions, and evaluation tables for all rounds, and a conference registration deadline of September 10, 2026. [Prediction Center](https://predictioncenter.org/)

**DREAM Challenges.** Three challenges were listed open today, all posted June 29, 2026 (Digital Pen feature extraction, DREAM-Q Target 2035 quantum, DREAM x CACHE Target 2035 drug discovery); closed challenges and publications are archived. [Open challenges](https://dreamchallenges.org/open-challenges/)

**Survey.** "Open Problems in Mathematical Biology" (Vittadello and Stumpf, arXiv June 20, 2022, CC BY-SA 4.0) is a curated question list without status tracking. [arXiv 2206.09516](https://arxiv.org/abs/2206.09516)

**Use.** Challenge rounds give dated tasks and baselines rather than open/solved status; a survey question needs the same literature check as any other lead. The single-cell benchmark in the earlier report remains the closest thing to a status-bearing resource in this area.

### 21. Machine-learning methodology: Papers With Code archive and a dated survey

**Papers With Code.** paperswithcode.com returned a 302 redirect to huggingface.co/papers/trending today. A GitHub issue opened August 14, 2025 reports the redirect with no maintainer response. The `pwc-archive` organization on Hugging Face hosts seven datasets (papers with abstracts, evaluation tables, methods, datasets, links between paper and code, redirects, files) described as "the last publicly available snapshot"; the methods card states "This dataset will not be updated. It corresponds to the last available public snapshot of the data, retrieved on July 28th, 2025" under CC-BY-SA-4.0, matching the CC-BY-SA license in the original data repository's README. [Redirect issue](https://github.com/paperswithcode/paperswithcode-data/issues/116), [pwc-archive](https://huggingface.co/pwc-archive), [methods dataset card](https://huggingface.co/datasets/pwc-archive/methods), [original README](https://raw.githubusercontent.com/paperswithcode/paperswithcode-data/master/README.md)

**Survey.** "Open Problems in Mechanistic Interpretability" (arXiv, January 27, 2025) is a forward-looking review without per-problem status. [arXiv 2501.16496](https://arxiv.org/abs/2501.16496)

**Use.** The archived evaluation tables are a frozen baseline index for rediscovery as of July 2025; nothing found here records open methodological questions with status.

### 22. Physics simulation: no maintained index found

Searches today for a maintained open-problem list in computational physics, turbulence, molecular dynamics, or lattice QCD returned dated review articles (for example a 2021 survey of the finite-density lattice-QCD sign problem) and arXiv listings, not a status-bearing index. Wikipedia's physics list was revised on 2026-09-07 and is an index only; the Clay page covers Navier–Stokes. [Lattice QCD survey](https://arxiv.org/abs/2108.12423), [Wikipedia physics list revision](https://en.wikipedia.org/w/api.php?action=query&prop=revisions&titles=List_of_unsolved_problems_in_physics&rvprop=timestamp|ids&format=json)

## General-purpose search routes for prior-work review

These are not lists; they are how the rediscovery hunt chases citations in both directions. Limits below were read today and change often.

- **arXiv.** The API allows "one request per three seconds" from all machines under one control with a single connection; metadata is CC0, e-prints keep their own licenses, and mirroring e-prints is prohibited. Bulk routes are OAI-PMH (harvesting guidance: bursts of 4 requests per second then a 1-second sleep), the Kaggle metadata dataset, and requester-pays S3. [API terms](https://info.arxiv.org/help/api/tou.html), [bulk data](https://info.arxiv.org/help/bulk_data.html)
- **Semantic Scholar.** Academic Graph, Recommendations, and Datasets APIs; the product page states unauthenticated callers share a 1,000-requests-per-second pool subject to throttling, and an API key starts at 1 request per second. The citations and references endpoints both answered unauthenticated today for arXiv:2210.17253 (citing papers dated 2026; references dated 2017–2023) with `offset`/`next`/`data` pagination. The license agreement (effective May 17, 2023) requires attribution and forbids redistributing the API; the November 2024 release notes (now discontinued) say inactive keys are pruned after about 60 days and keys are not issued to free email domains. [API overview](https://www.semanticscholar.org/product/api), [citations call](https://api.semanticscholar.org/graph/v1/paper/arXiv:2210.17253/citations?fields=title,year&limit=3), [references call](https://api.semanticscholar.org/graph/v1/paper/arXiv:2210.17253/references?fields=title,year&limit=3), [license](https://www.semanticscholar.org/product/api/license), [release notes](https://raw.githubusercontent.com/allenai/s2-folks/main/API_RELEASE_NOTES.md)
- **OpenAlex.** API keys became required on February 13, 2026 (announced January 13, 2026). Pricing (page updated August 9–11, 2026): a free account gets $1 of usage per day; single-entity lookups are free; list+filter $0.10, search $1, semantic search $1, and content download $10 per 1,000 calls; anonymous callers get one-tenth of the free budget. A keyless singleton call today returned headers `x-ratelimit-limit-usd: 0.1` and a work object with `referenced_works` and `cited_by_count`; for House of Graphs 2.0 those were empty and zero, whereas Semantic Scholar had both, a coverage difference worth checking per paper. Data is CC0. [Announcement](https://groups.google.com/g/openalex-users/c/rI1GIAySpVQ), [pricing](https://help.openalex.org/access/pricing/), [example costs](https://help.openalex.org/access/example-costs/), [API introduction](https://help.openalex.org/api-reference/introduction)
- **Crossref.** Free, no sign-up, polite pool via a `mailto` parameter; the tips page says to back off on 429. A GET today returned `x-rate-limit-limit: 3` with `x-rate-limit-interval: 1s` from this address, lower than older documentation suggests, so read the headers at run time. [REST API](https://www.crossref.org/documentation/retrieve-metadata/rest-api/), [tips](https://www.crossref.org/documentation/retrieve-metadata/rest-api/tips-for-using-the-crossref-rest-api/)
- **OpenCitations.** `/citations/{id}` and `/references/{id}` by DOI, PMID, or OMID; an access token is recommended but optional; "API calls are rate-limited to 180 requests/minute per IP address"; dumps are available for bulk use. [Index API v2](https://api.opencitations.net/index/v2)
- **zbMATH Open.** Free since January 1, 2021; REST API 1.0 released July 1, 2021. Terms (June 2021) say "All data are allowed to be used under a CC-BY-SA license" and ask for "a reasonable rate" of requests; the API returns FIZ Karlsruhe's own data and publisher-authorized data, and some review text is withheld "due to conflicting licenses". Both the REST search and the OAI-PMH `Identify` verb answered without credentials today. [API terms](https://api.zbmath.org/v1/static/terms-and-conditions.html), [release note](https://www.fiz-karlsruhe.de/en/nachricht/zbmath-open-release-api-10), [REST](https://api.zbmath.org/), [OAI-PMH](https://oai.zbmath.org/)
- **MathSciNet (restricted).** The application front end requires JavaScript and, per AMS subscription pages, site-wide IP-authenticated institutional subscriptions; AMS web pages were behind a bot challenge from this environment today, so pricing text was not re-read. The free MR Lookup tool returns up to three matching items per query and is usable for citation matching without a subscription. [MR Lookup](https://mathscinet.ams.org/mrlookup), [AMS subscriptions page](https://www.ams.org/publications/math-reviews/mathsciprice)
- **dblp.** The search API (`/search/publ/api`) and FAQ pages on dblp.org and both mirrors returned an Anubis "Making sure you're not a bot" challenge to curl and to the fetch tool today, so the documented CC0 license and API guidance could not be re-read from here; the XML dump remains the documented bulk route. [FAQ on API](https://dblp.org/faq/13501473.html), [license FAQ](https://dblp.org/faq/Under+what+license+is+the+data+from+dblp+released.html)
- **Google Scholar.** No API; robots.txt disallows `/scholar` and `/search` and allows only specific profile and metrics views, so automated querying is outside its terms. [robots.txt](https://scholar.google.com/robots.txt)
- **Hugging Face Papers.** The redirect target for Papers With Code; a trending feed with code links, not a leaderboard index.

## Coverage, uncertainty, and follow-on decisions

The survey answers where maintained lists with status live and how each represents it, and it records which general search routes an individual operator can use without credentials today. It did not run any of the routes at scale, and rate limits and pricing observed today (OpenAlex credits, Crossref headers, Stack Exchange quotas) should be re-read at run time.

Specific limits of the evidence:

- Several hosts were unreachable or challenge-gated from this environment: kourovka-notebook.org (timeout), dblp.org and mirrors (bot challenge), ams.org pages (bot challenge), mathoverflow.net web pages (blocked; the API answered), aimpl.org over HTTPS (expired certificate reported), and web.archive.org. Where a claim depends on such a page, the report says so.
- A search-engine summary attributed the "685 open of 1105" count to Open Problem Garden; the primary paper applies it to the Erdős index. Secondary summaries of status counts should not be trusted without the primary text.
- Licenses are stated only where the page states them. TOPP, the Waterloo TSP pages, TSPLIB, QAPLIB, SteinLib, DIMACS, SAT Competition instances, and MiniZinc Challenge instances carry no license statement on the pages checked.
- Model names in Epoch AI's and Formal Conjectures' text are reported as they appear; this report does not verify any capability claim.
- Physics simulation and ML methodology lack a maintained, status-bearing open-problem index in the sources found; computational biology has dated challenge rounds instead.
- No source records AI provenance in a shared vocabulary; the erdosproblems wiki, Epoch AI, and the Kourovka comments each use their own.

Decisions this evidence enables, without settling them:

- Which of these sources the workflow polls by default, and how it records each source's last-update evidence alongside a status observation.
- Whether the rediscovery hunt should depend on a metered route (OpenAlex) or on the free routes (Semantic Scholar, Crossref, OpenCitations, zbMATH Open, arXiv), and how to handle dblp's bot challenge.
- How to represent "listed as open in a stale source" differently from "open per a dated, maintained source" when a candidate enters the collection.
- Whether AI-attempt indexes (erdosproblems, Epoch AI) should be consulted before any attempt on a listed problem, given their fragmentation.
