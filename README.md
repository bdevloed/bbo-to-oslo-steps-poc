# bbo-to-oslo-steps-poc
PoC exploring the feasibility of an automated BBO to OSLO-Steps mapping

## Context
Investigating the feasibility generating OSLO steps starting from BPMN.

The goal is not to provide a fully working solution, rather understand 
- how far this could be automated
- what has to be taken into account when creating BPMNs in order to have a working BPMN -> OSLO steps solution.
- what extra information is needed next to BPMN and mappings to create OSLO-Steps.

A bit more context on BPMN and BBO can be found in the [bpmn_bbo_mapping](https://github.com/MartijnBogaert/bpmn_bbo_mapping) repo.

## Implementation
### BPMN to linked data
[bpmn_bbo_mapping](https://github.com/MartijnBogaert/bpmn_bbo_mapping) maps BPMN (xml) to linked expressed using the BBO and BBO-ext ontologies.


### BBO to OSLO-Steps
This repo maps the data (partially) to OSLO steps.

The mapping rules and queries are written in [Notation3](https://w3c.github.io/N3/spec/) and can be executed using the (EYE Reasoner)[https://github.com/eyereasoner/eye].

## Run the code

### Docker on Linux/OSX

```
docker run --net=host --rm -v $HOME:$HOME -w $(pwd) -ti eyereasoner/eye --nope --quiet --pass *.n3
```

### Docker on Windows
```
docker run --net=host --rm -v %HOMEPATH%:%HOMEPATH% -w %cd% -ti eyereasoner/eye --nope --quiet --pass *.n3
```

### EYE native
```
eye --nope --quiet --pass *.n3
```
