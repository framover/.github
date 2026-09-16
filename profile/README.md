# framover

*Framover* is Norwegian for *onwards*. The name comes from *Fram*, the ship built to carry Nansen's polar expedition, and this is where the data model behind NANSEN goes next.

## Where we come from

[NANSEN](https://github.com/VervaekeLab/NANSEN) is a MATLAB toolbox for organising, processing and analysing two-photon imaging data, developed in the Vervaeke lab since 2021. Its most durable idea was not the apps but the data model underneath them: map a lab's existing folders into a project without moving anything, address data by named variables instead of file paths, and swap analysis tools behind a shared set of data types. That model was embedded in one large MATLAB codebase and could not be used from anywhere else.

## Goal

A small set of language-neutral specifications that describe scientific data as it is, so that tools in any language, and AI agents, can find, type and process it without a lab reorganising its data first. Each specification is a JSON schema with conformance fixtures, so a reader written in a new language is checked against the same expectations as every other reader.

## Where we are going

Three specifications, layered from the ground up:

1. **Dataset Structure Model (DSM)**: where things are. Stores, entities, files, and the identity that makes one entity out of differently named folders. Version 1.0 is released and is being exercised on more datasets before any 2.0.
2. **Data model**: what things are. A type vocabulary and named variables bound to DSM entities. This is the next specification.
3. **Workflow**: how things are processed. Adapter and method manifests, and run records for provenance. This follows the data model.

Around the specifications: language runtimes that implement them, MATLAB first and Python next; modules that ship domain content such as two-photon types, adapters and methods; and a web view over entity tables. NANSEN continues as the MATLAB runtime and adopts the specifications one layer at a time.

## Principles

- Descriptive, not prescriptive. The specifications describe data as it is and never require a layout.
- A field enters a specification only when a reader consumes it.
- Fixtures are the specification. Two readers agree because they pass the same conformance cases.
- Specifications carry neutral names. Runtimes and apps carry the nansen name.

## Repositories

| Repository | What it holds | Status |
|---|---|---|
| [dataset-structure-model](https://github.com/framover/dataset-structure-model) | The DSM schema, conformance fixtures, and Python and MATLAB readers | 1.0 released |
