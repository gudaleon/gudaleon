# Alex Neumann

Earth system modeller. Senior Research Associate, University of Toronto.

## Educated across six fields

My education is the span itself, and it is the differentiator. I trained first as a civil engineer (Moscow State University of Civil Engineering, 1997), on a mathematical foundation, and my centre is earth science and mathematical modelling (PhD, Geography, University of Toronto, 2014), reached through environmental science (M.Env.Sc., University of Toronto, 2009). Around that centre sit management and economics (MBA, MIRBIS, 2007) and, at the far reach, the social sciences and law (Undergraduate Law Studies, Civil Law, Moscow State Law Academy, 1995 to 1999). Few modellers carry all of that into earth system modelling. The range below is what that education produces, and this account, open since 2015, is its documentary record: 174 repositories in all, of which 52 are my own systems and tools and 122 are a working library of the field's codebases.

## The modelling range, organised by a typology

The range is organised by a typology whose top level crosses two axes. The first axis is process representation: empirical and statistical, conceptual, physically based and mechanistic. The second axis is spatial representation, glossed by one shared question: what spatial variation survives into the equations? Each domain keeps its own class labels, side by side and never merged, because the labels are not interchangeable. Temporal treatment, and complexity in the senses set by Claussen et al. (2002), meaning detail of description and number of processes represented explicitly, with integration reported as a separate indicator, are carried as descriptors. Complexity here is a spectrum, never a ranking. Where an axis stops, the boundary is stated.

| Process representation | Where my work sits on it |
|---|---|
| Physically based and mechanistic | SWAT, extended at source level in SWAT+P, a library of six switchable soil phosphorus formulations plus a macropore tile-drainage bypass in the SWAT+ source. CE-QUAL-W2, the two-dimensional longitudinal-vertical hydrodynamic and water-quality model, held as a working codebase. MyLake v2, a lake model rebuilt with a sediment module and a continuous reaction network. A sediment reactive transport model for Hamilton Harbour. Soil-crop modelling with EPIC. |
| Conceptual | The conceptual landscape units and runoff-generation schemes inside the semi-distributed watershed models above, and the scenario layer of the SPARROW decision tool described below. |
| Empirical and statistical | An ensemble of eight structurally different phosphorus-export models run in parallel on the same catchments against the same calibration record, Bayesian SPARROW among them, built on the principle that no single model should carry a management decision. |

Two hybrid families stand as separate entries, cross-referenced and never merged, because no published source equates them. The first is the hybrid semi-empirical family of my 2021 review (Neumann et al., Environmental Reviews 29: 443 to 490): statistical estimation structured by a subset of fundamental processes, with SPARROW as its working example in my hands. The second is the physics-informed and hybrid machine-learning family of the 2020s, where physical constraints enter the loss, the architecture or the residuals of a learning system. I work in both traditions, the first being the tradition my 2021 review codified and the second a current research programme, and the entries stay separate so that neither borrows the other's evidence.

Two further axes are fenced to their domains. Biological organisation, running from compartments through functional types and trait continua to individuals, is used only inside lake and ocean ecology and individual-based work, and there it is governed by a testable criterion, explicit individual variation (DeAngelis and Mooij 2005). My individual-based models of mussels and of fish, and my synthetic-person populations, meet that strict test. The geochemical reaction regime, equilibrium, kinetic or mixed, together with the coupling strategy between flow and chemistry, is used only inside reactive transport, where it belongs.

## The Earth boundaries the work crosses

The models are grouped above by how they represent the world. They can also be read by the Earth boundaries they sit on, and the second reading shows the habit of the work: my models characteristically couple across these boundaries rather than sitting inside one sphere.

- **Atmosphere.** Climate ensembles and their verification: a CMIP6 analysis for the Lake Erie basin, and an ensemble-change diagnostic for extremes and drought indices over Manitoba stations.
- **Hydrosphere.** Watershed, river, lake and groundwater models: SWAT and SPARROW on the land surface, CE-QUAL-W2 in rivers, estuaries and lakes, GLM in the working library, MODFLOW in the current groundwater programme.
- **Pedosphere.** Soil carbon, nitrogen and phosphorus cycles: the soil organic matter pools of the watershed models, the switchable soil phosphorus formulations of SWAT+P, and soil-crop modelling with EPIC.
- **Lithosphere and sediment.** Reactive transport in sediments, the sediment module of MyLake v2, and sediment phosphorus and iron cycling in the current programme.
- **Biosphere.** Ecosystem dynamics in the NPZD lineage, cyanobacteria cellular models, and individual-based models of mussels and fish.
- **Anthroposphere.** Whole-farm greenhouse-gas accounting for Ontario counties, coupled human-natural systems analysis, and management and best-management-practice decision tools.

Two worked examples show the coupling. The watershed continuum runs in one chain from climate forcing in the atmosphere, through soil nutrient cycles in the pedosphere, through river routing in the hydrosphere, to the ecosystem of a receiving lake in the biosphere, with management scenarios from the anthroposphere run on the same chain; that is the architecture of my Lake Erie work. The farm system couples soil, plant, atmosphere and management decision in a single accounting, which is the architecture of the whole-farm greenhouse-gas work. A model that stays inside one sphere is, in my practice, the exception.

## How models are chosen

Purpose, application and data situation are not classes of model. They are properties of a modelling task, so they stand alongside the typology as guidance on selection, which is where the literature puts them. In practice: the decision the model must support and the data actually available decide which cell of the typology a problem belongs in; parsimonious empirical models are used to constrain the process values of the mechanistic ones and to validate their macroscale patterns, as my 2021 guidelines paper argues; and where a decision carries real uncertainty, an ensemble of structurally different models is preferred to any single model, however distinguished.

## The record, stated as biography

Built, ported, extended, applied and verified are facts about a career, not classes of model, so they are stated here as biography and nowhere in the typology.

- **Built.** SWAT+P, at source level in the SWAT+ Fortran. My own greenhouse-gas simulation platform, with user-defined equation modules, parameter provenance tracking, Monte Carlo uncertainty analysis and Sobol sensitivity analysis as framework services. An implementation of the stoichiometric derivation method of Reichert and Schuwirth (2010), deriving stoichiometric coefficients from element and charge conservation by exact rational arithmetic. The eight-model phosphorus-export ensemble.
- **Ported.** Eawag's AQUASIM, the aquatic-system simulator, re-implemented in Python across all its compartments, with mass-balance checks and PEST++ and DREAM calibration. A reactive transport model of bioretention phosphorus, re-implemented in Python and augmented for eggshell and woodchip bioreactors, its comparisons against the original reported honestly as consistency checks. The Hamilton Harbour sediment reactive transport model, carried from its original graphical modelling environment into MATLAB, with a first-year cross-code verification against the reference exports.
- **Extended.** SWAT+ itself, above. MyLake, updated to version 2 with its sediment module and reaction network.
- **Applied.** SPARROW in four implementations, for the Great Lakes and for the Mississippi River Basin. MyLake v2 applied to Lake Vansjø. The whole-farm greenhouse-gas model used in Canadian agriculture, run for Ontario counties across the census years 2001, 2006, 2011 and 2016, with a source-code audit of the model itself.
- **Verified.** Verification is the through-line. For the Lake Erie climate work I re-implemented the Climpact and climdex index definitions independently in Python and compared the recomputed tables against the published thesis tables cell by cell. For the Waterville signal-separation work, every headline estimator is implemented twice in Python, with the spectral core implemented a third time, and cross-checked against synthetic series with known answers; no R is used anywhere in that analysis.
- **The working library.** The 122 forks in this account are other people's codebases that I keep, read and build against, FVCOM, GLM, SWMM and EPANET among them. A fork is not authorship, and nothing in this profile presents the library as my work. It is presented for what it is: the shelf of a modeller who keeps the field's source code at hand.

## Current work, in the present tense

- **Physics-informed machine learning for reactive transport.** A three-paper programme in progress: simple decay with retardation; saturating-rate groundwater, with groundwater flow and transport modelling in MODFLOW; and sediment iron and phosphorus. Each stage is benchmarked against analytical and numerical solutions as it is completed. No benchmark result is claimed before it exists.
- **The GRIP benchmark.** Machine learning for discharge and concentration, under active development: long short-term memory and gradient-boosted models benchmarked against the established process models the learning sits on, SWAT among them, over the basins of the Great Lakes runoff intercomparison.
- **Agentic workflows under AEVO.** AEVO, Architect, Execute, Verify, Own, is my framework for researcher-led, AI-assisted modelling: the researcher designs the framework and assembles the scenarios and forcing functions that test the model, the tools execute, and every headline result is verified by an independent route before it is believed. Its companion work ties an AI agent's answers on a drinking-water census to a claims register, so that nothing the agent says floats free of its evidence.

The through-line of all of it: models are chosen on evidence, built where building is needed, and verified before they are believed.
