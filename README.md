# Alok Didde

**Robots, intelligent systems, and the infrastructure between them.**

I build systems at the edges: where software meets hardware, models meet messy data, and prototypes meet actual use. My work spans robotics, physical AI, retrieval, agent-native electronics, healthcare, and distributed systems.

## Now building

<a href="https://github.com/alokdidde/uzumaki"><img src="https://raw.githubusercontent.com/alokdidde/uzumaki/main/docs/media/uzumaki-banner.png" alt="Uzumaki: an agentic harness for any robot body" width="100%"></a>

### [Uzumaki: a robot harness that grows its own skills](https://github.com/alokdidde/uzumaki)

An agentic harness for any robot body and any model. A planner picks a validated skill for the goal, or says none fits. A generator then writes the missing skill as a small sandboxed program, runs it in MuJoCo, and repairs it from execution traces until it passes cases it never saw. Only then is it promoted into the skill library. Every run is checked by an independent evaluator and leaves a replayable, checksum-chained evidence bundle.

The same core runs eight simulated bodies today (SO-101, Franka Panda, ALOHA, TidyBot, Spot, Unitree G1 and Go1, standing and walking), each passing all 28 of its development cases, including failed grasps, dropped handovers, stale observations and worker crashes.

<table>
<tr>
<td width="33%"><img src="https://raw.githubusercontent.com/alokdidde/uzumaki/main/docs/media/aloha-dropped-handover.gif" width="100%" alt="ALOHA dropping a bar mid-handover and picking it up again"><br><sub>ALOHA notices a dropped handover and recovers</sub></td>
<td width="33%"><img src="https://raw.githubusercontent.com/alokdidde/uzumaki/main/docs/media/g1-nominal.gif" width="100%" alt="Unitree G1 humanoid picking a box with its left hand"><br><sub>Unitree G1 picking with its Dex3 hand</sub></td>
<td width="33%"><img src="https://raw.githubusercontent.com/alokdidde/uzumaki/main/docs/media/go1-walk-nominal.gif" width="100%" alt="Unitree Go1 walking a box between two tables"><br><sub>Go1 fetching on a learned walking policy</sub></td>
</tr>
</table>

### [Mushin: a System-1 decision model for robots](https://github.com/alokdidde/mushin)

Skills do the motion, but something still has to decide at every step which skill to run, with what parameters, and whether to act at all. Mushin is a compact vision-language model that makes that call in a single forward pass. From the task, the robot's state, its recent history and two camera frames, it returns a probability for every skill and for abstaining, the chance each skill would succeed right now, and the skill's parameters. It is built on Qwen3.5-0.8B, sits in Uzumaki's planner slot, and is aimed at running on a Jetson Orin Nano.

v0.1 is a research release, trained and tested only in simulation on 201k decisions with counterfactual labels:

- Picks the best skill more often than every baseline (0.747 vs 0.715), and 0.707 vs 0.632 on a robot body it never saw in training.
- Predicts whether a skill will succeed with AUROC 0.916 and well-calibrated probabilities (ECE 0.005).
- As Uzumaki's planner, matches the rule planner's task success with 17% fewer decisions.

## Selected work

### [Fulmetry](https://fulmetry.com/)

Describe the circuit board you need. A coding agent writes the TypeScript, chooses parts, places and routes the PCB, runs checks and simulations, and prepares the manufacturing files. You review the result and steer the next change.

[Source](https://github.com/Fulmetry/fulmetry) · [Documentation](https://docs.page/Fulmetry/fulmetry)

### Retrieval beyond embeddings

An experimental retrieval approach that uses Monte Carlo exploration to search a corpus instead of depending entirely on vector similarity. The interesting part is not merely ranking documents better. It is giving retrieval a strategy, memory, and somewhere to go when its first guess is wrong.

### A field robot that sees, navigates, and acts

An autonomous agricultural platform combining spatial reconstruction, visual pest detection, navigation, and robotic-arm control. Gaussian Splatting informed the map, CNNs handled detection, and forward and inverse kinematics drove manipulation.

## Smaller things shipped

- [Ganglia](https://github.com/alokdidde/ganglia), adaptive memory for AI agents using BM25, embeddings, recency, feedback, and an L1/L2/L3 hierarchy.
- [Saarathi](https://github.com/alokdidde/Saarathi), WhatsApp-native business intelligence for Indian micro-businesses.
- Healthcare systems covering remote patient monitoring, clinical workflows, real-time communication, claims, and AI-assisted documents.

## Working questions

- How much of robotics infrastructure can become usefully boring: predictable, inspectable, and reusable?
- How small and fast can the model that decides what a robot does next be, and still know when not to act?
- What changes when retrieval explores instead of only ranking?
- What makes open hardware genuinely extensible, rather than merely downloadable?

## Elsewhere

[Website](https://alokdidde.com/) · [Writing](https://alokdidde.com/blog/) · [LinkedIn](https://www.linkedin.com/in/alok-didde-85335726)

[alok.didde@gmail.com](mailto:alok.didde@gmail.com)
