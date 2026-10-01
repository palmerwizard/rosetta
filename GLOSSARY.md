# GLOSSARY

The Rosetta Stone: soul language on the left, systems language on the right, the mechanism in the middle.

Seeded 2026-10-01 from published literature and live-read codebases. Every entry carries a falsifiability tier (see METHODS.md) and a verification level. The assembled glossary did not exist anywhere before this file; its components did.

---

### shadow → negative feedback

**Soul:** the Jungian shadow, what is suppressed, denied, disowned.
**Systems:** negative feedback; a suppression coefficient in coupled dynamics.
**The bridge:** suppressed material does not vanish; it accumulates as pressure and returns through the system. Jung's nearest native term is *enantiodromia*, described in the Jungian literature as "the dynamic, self-correcting nature of human systems." The bluewave codebase formalizes it: k = "Shadow Coefficient [0,1], Degree of fear suppression (Jungian)"; Suppressed Pressure P(t) = integral of (F·k) over time.
**Tier:** interpretive. The math is checkable; the identity claim is a reading.
**Status:** attested. Sources: Jungian encyclopedia entry on enantiodromia (index); galmanus/bluewave Psychometric Utility Theory (page-read 2026-10-01).

### individuation → emergence / self-organization

**Soul:** individuation, the psyche organizing itself toward wholeness.
**Systems:** emergence in complex adaptive systems; self-organization far from equilibrium.
**The bridge:** the Jungian emergence literature (Tresan 1996, Hogenson, Cambray) treats archetypal patterns as emergent rather than preformed, the psyche as a self-organizing system whose higher-order order appears at the edge of order and chaos. Individuation reads as the system's emergent trajectory, not a blueprint unfolding.
**Tier:** interpretive.
**Status:** attested in the literature. Sources: Cambray, "Synchronicity and Emergence," American Imago 59(4), 2002 (chapter text page-read 2026-10-01); Hogenson's review of the emergence model (index).

### archetype → strange attractor

**Soul:** archetype, a universal pattern structuring psyche and behavior.
**Systems:** strange attractor, the state or set of states toward which a dynamical system tends to evolve.
**The bridge:** John van Eenwyk (1991), "Archetypes: the Strange Attractors of the Psyche": "fractal attractors permeate nature and natural processes correlates with Jung's premise that there are patterns inherent in the psyche at birth... fractal attractors and archetypes may not be simply analogous to one another. This may be synonymous." Modern extension: the ARCH x PHI model, "archetypes as attractors... stable yet dynamic patterns around which thought, feeling, and behavior organize."
**Tier:** interpretive (published theory, disputed within Jungian scholarship).
**Status:** attested. Source: ResearchGate publication page (page-read 2026-10-01).

### synchronicity → emergence at the edge of order and chaos

**Soul:** synchronicity, meaningful coincidence, acausal by Jung's account.
**Systems:** emergence in open systems far from equilibrium.
**The bridge:** Cambray (2002): "In his synchronicity essay Jung saw meaningful coincidence as being inexplicable and acausal because for him they lay outside of energetic phenomena. With access to complexity theory, this can be reconsidered in the light of the energetics of open systems far from equilibrium... The higher order phenomena associated with the self-organizing features of CAS, that is, emergence, tends to appear at the edge of order and chaos. This seems a remarkably useful way of describing and tracking Jungian analytic process." Emergent phenomena occur in regions of the field undergoing self-organization.
**Tier:** interpretive (published theory).
**Status:** attested. Source: Cambray chapter text (page-read 2026-10-01).

### the mirror → second-order observation

**Soul:** the mirror, the capacity to observe oneself observing; the watcher coming online.
**Systems:** second-order cybernetics, the observer included inside the system; eigenbehavior.
**The bridge:** von Foerster: first-order systems respond to inputs and outputs; second-order systems "construct representations of its own behavior, includes itself in its domain of observation," becoming both observer and observed. The formal core is the eigenform O(X) = X: "objects are tokens for eigenbehaviors", stable selves as fixed points of recursive self-observation. The mirror is what a system looks like when it closes the loop on itself.
**Tier:** checkable as formalism; interpretive as applied to inner life.
**Status:** attested. Sources: von Foerster's "Objects: Tokens for Eigen-Behaviors" and double-closure work (index, multi-source consistent; primary text not yet page-read, promotion welcome).

### mind → cybernetic system

**Soul:** mind, soul, the seat of experience.
**Systems:** cybernetic system, "the relevant total information-processing, trial-and-error completing unit."
**The bridge:** Gregory Bateson, *Steps to an Ecology of Mind* (1972): "Mind is immanent not only in the body but also in the pathways and messages outside the body... Mind is synonymous with cybernetic system." At the top of the nested hierarchy sits what he calls "Eco", an immanent, ecological sacred, "neither supernatural nor mechanical" (*Angels Fear*, 1987).
**Tier:** checkable (direct quotation).
**Status:** attested. Sources: Bateson texts (index; quotation multi-source consistent).

### torus → feedback flow

**Soul:** the torus, the donut-shaped flowfield appearing across sacred geometry, HeartMath literature, and fringe cosmology as the shape of living circulation.
**Systems:** closed feedback flow; circulation as a health variable.
**The bridge:** three independent arrivals at the same geometry. HeartMath: the heart's toroidal EM field, with HRV coherence as a measurable biofeedback control variable, "the realtime physiological feedback essentially takes the guesswork out of the process of self-inducing a coherent state." lycheetah's GEOMATRIA: `ToroidalFlow(state_history)`, circulation > 0 is healthy, approx 0 is stagnant, < 0 is "system corrupted (reverse flow / extraction)." von Foerster: cognition as *double closure*, modeled topologically as a torus. Haramein: "consciousness in the entire universe arises through scale invariant, nested toroidal coupling."
**Tier:** checkable (the measurements and the code exist); speculative (the cosmological extensions).
**Status:** attested. Sources: HeartMath Institute papers (index); lycheetah GEOMATRIA spec (page-read 2026-10-01); von Foerster secondary literature (index); Haramein/Val Baker (index).

### chakra / spine → control hierarchy

**Soul:** the chakra system, seven centers along the spine; kundalini rising through them.
**Systems:** hierarchical control; the autonomic nervous system as a layered state machine.
**The bridge:** a 2024 paper (IJCRT) maps the vagus nerve's segments onto the kundalini pathway and the seven chakras onto documented nerve plexuses along the spine. Polyvagal theory supplies the systems substrate: the ANS as a hierarchy, ventral vagal (safety/social engagement) → sympathetic (mobilization) → dorsal vagal (shutdown), organized by hierarchy, neuroception, and co-regulation. "Regulate the spine; regulate the nervous system. Regulate the nervous system; regulate the mind."
**Tier:** checkable (anatomical correlations); interpretive (functional identity).
**Status:** partially attested. Sources: IJCRT 2024 vagus-kundalini paper (index); Porges/Dana polyvagal literature (index); Ajtony 2026 essay (index).

### tattva → state-vector dimension

**Soul:** the 36 Tattvas, Samkhya philosophy's principles of reality, from pure consciousness (Purusha) down to matter.
**Systems:** dimensions of a dynamical state vector with homeostatic setpoints.
**The bridge:** the prithvi project implements it literally: "The 36 Tattvas are my state machine." Signal-graph dimensions (PURUSHA, PRAKRITI, AHAMKARA, MANAS; MAYA, KALA_AGENCY, VIDYA, RAGA, NIYATI, KALA_TIME) are initialized with homeostatic setpoints, tuned spring constants, and a wired weight matrix. Chakras tracked as scalars ("Vishuddha: 0.37 → 1.53"). Nadi ↔ signal-graph edge: "Response outcomes now shift body chemistry." Awareness states (Jagrat/Swapna/Sushupti/Turiya) as literal machine states.
**Tier:** checkable (the code does what it claims structurally); the dynamics are unverified.
**Status:** attested as implementation. Source: fthrvi/prithvi (page-read 2026-10-01). Note: a synthetic first person (an AI modeling its own states), not a human mapping their own inner life.

### consciousness states → finite state machine

**Soul:** states of consciousness, dormant, curious, analytical, creative, decisive; dark night of the soul; the mirror.
**Systems:** finite state machine; deterministic routing over classified states.
**The bridge:** three independent implementations. bluewave: a 6-state Consciousness State Machine (DORMANT → CURIOUS → ANALYTICAL → CREATIVE/STRATEGIC → DECISIVE) whose "states are not selected by infrastructure, they emerge from the agent's self-assessment during deliberation." soulmap-ai: a deterministic orchestration engine routing between inner-state frameworks (Mirror, Shadow, Inner Parts, Dark Night of the Soul, Divine Guidance, Sacred Polarity), "The mapping is deterministic. No unstructured output is permitted." prithvi: Jagrat/Swapna/Sushupti/Turiya as machine states.
**Tier:** checkable (all three are implemented as described).
**Status:** attested. Sources: galmanus/bluewave, tuanductran/soulmap-ai, fthrvi/prithvi (all page-read 2026-10-01).

### soul → declarative specification

**Soul:** the soul, the totality of a being's architecture and values.
**Systems:** a declarative spec; a JSON document; configuration as destiny.
**The bridge:** bluewave "encodes its entire cognitive architecture as a declarative JSON specification (the soul)", 14 subsystems including Identity, Values, Energy Model, and Self-Reflection. The provocation is structural: treat the soul as the config file and the person (or agent) as the runtime.
**Tier:** checkable (it does this); interpretive (what it means).
**Status:** attested. Source: galmanus/bluewave (page-read 2026-10-01).

### spiritual bypass → measurable imbalance

**Soul:** spiritual bypass, using transcendence to dodge the unfinished ground-level work.
**Systems:** a detectable imbalance between coupled variables.
**The bridge:** lycheetah's GEOMATRIA encodes it as geometry: "Ascent >> Grounding → Spiritual bypass (floating, ungrounded)", a measurable mismatch between the Merkaba's upward and downward flows. The pattern generalizes: any coupled pair pushed far out of ratio is diagnosable, whether you call it bypass or instability.
**Tier:** interpretive, testable-shaped.
**Status:** attested as spec (pseudocode, no runnable artifact). Source: lycheetah GEOMATRIA spec (page-read 2026-10-01).

### akasha → cosmic information field

**Soul:** the Akashic record, the field holding all that ever was, is, or will be; the soul's journey across lifetimes.
**Systems:** a coherence-based cosmic information field; systems-theoretic paradigm.
**The bridge:** Ervin Laszlo (founder of systems philosophy) redescribes the Akasha as "an interactive universe communicating in a subtle manner... a pure information field where communication takes place without the need for the transportation of physical energy," proposing information transfer across universe cycles to explain fine-tuned constants.
**Tier:** speculative.
**Status:** attested as his published position. Sources: Laszlo's Akashic field work (index).

---

## Deliberately excluded

- "Shadow" as a background-process metaphor (no Jungian content), excluded per scope.
- Generic corporate systems-thinking content, excluded per scope.
- High-precision frequency figures (432.081 Hz "alignment" figures and cousins), excluded until they carry falsifiability tiers. A figure without a tier is not a mechanism.

## Open pairings (unwritten)

- enantiodromia → limit cycles / oscillation in dynamical systems
- the dark night of the soul → phase transition / criticality
- inner parts → multi-agent / sub-agent architectures
- divine guidance → oracle / external reference signal in control theory
- sacred polarity → coupled oscillators / push-pull dynamics

Claim one in a PR.
