# D3FEND Ontology

This repository holds the necessary content to produce the D3FEND ontology distribution.

- > If you are looking for the latest release of the ontology, please find it [here](https://d3fend.mitre.org/resources/ontology/).

- > If you are interested in contributing to this project, please see our [contribution guidelines](CONTRIBUTING.md).

## Overview

> **Note**: before sending a merge request changes to `src/ontology/d3fend-protege.ttl` please always run 
`make format` **before** you commit changes or will will not be able to accept the request. :eyes:

The basic workflow is to edit the `d3fend-protege.ttl` file, save your changes, then simply
run `make all` in this directory. This is designed to accommodate both plain text editing
and Protege Ontology IDE modifications.

When making changes with a text editor please avoid introducing unsubstantial changes
to many lines in the file. This enables efficient code reviews.

> **Note:** if you are looking for the latest D3FEND ontology release please find it
[here](https://d3fend.mitre.org/resources/ontology/).

## System Dependencies

- java 15.0.1, other versions may work however
- python 3.8
- python pipenv package with `pipenv` in your PATH

## Building

The Makefile has all the necessary targets (commands) needed to build the D3FEND ontology.
Once your system dependencies are installed, Run `make install-deps`, then you can run
`make all` to build the ontology.

> In order to run `make build/d3fend.csv`, you need to be
running a d3fend-backend server, this is not yet released.

## Directories

|Directory          |Purpose                                          |
|-------------------|-------------------------------------------------|
|dist/         |Holds distributable ontology files resulting from a build (`make all`).|
|build/       |Holds intermediate files used in build workflow.|
|reports/      |Holds reports generated by report and test targets.|
|src/queries/  |Holds queries and report profiles necessary to update ontology and generate reports.|
|src/ontology/  |Holds the base ontology which is used during the build process to create the distribution.|

## Files

These files are located in the src, build, or dist directories.

> Note: some files are created when `make all` is executed.

|File                       |Purpose                                          |
|---------------------------|-------------------------------------------------|
|d3fend-protege.ttl         |Downloaded D3FEND ontology from webprotege.owl (renamed to match this name).|
|d3fend.{ttl,owl,json}      |D3FEND ontology distribution files.|
|d3fend-public.owl         |Temp merge of original web protege ontology and restrictions as object property assertions.|
|d3fend-res-as-prop.owl     |Temp file containing *just* restrictions as object property assertions between class puns.|
|d3fend-full.owl      |Final inference-enhanced copy with KBs for use in SPARQL end point. This is what is loaded into production Blazegraph.|
|d3fend-architecture.owl |File of architectural elements extracted by a filter-architecture-* target.|
|d3fend.csv              |Tabular form of defensive tactics and techniques trees.|
|d3fend-prefixes.json     |D3FEND ontology context information / namespace prefixes in JSON-LD format; usable by ROBOT and RDFLib.|
|annotations.ttl      |Not currently used; stub of alternative file-based means to add ontology header (see ROBOT documentation).|

## Developer Notes

- Ontology version is specified in `Makefile` as `D3FEND_VERSION`
- Ontology style guide/conventions [here](./CONVENTIONS.md) (work in progress).

## Build with docker

If you have docker and docker-compose, you can build a distribution
in the dist/ folder running

```bash
docker-compose up d3fend-ontology
```

## NOTICE

Use of the MITRE D3FEND™ Knowledge Graph and website is subject to the Terms of Use. Use of the MITRE D3FEND website is subject to the MITRE D3FEND Privacy Policy. MITRE D3FEND is funded by the National Security Agency (NSA) Cybersecurity Directorate and managed by the National Security Engineering Center (NSEC), which is operated by The MITRE Corporation. MITRE D3FEND; and the MITRE D3FEND logo are trademarks of The MITRE Corporation. MITRE ATT&CK® and ATT&CK® are registered trademarks of The MITRE Corporation. MITRE ATT&CK content is subject to the MITRE ATT&CK terms of use.

## NOTICE

This software was produced for the U. S. Government under Basic Contract No. W56KGU-18-D-0004, and is subject to the Rights in Noncommercial Computer Software and Noncommercial Computer Software Documentation Clause 252.227-7014 (FEB 2012) © 2022 The MITRE Corporation.

## NOTICE

MITRE hereby grants express written permission to use, reproduce, distribute, modify, and otherwise leverage this software to the extent permitted by the licensed terms provided in the LICENSE.md file included with this project.

## NOTICE

© 2022 The MITRE Corporation.

Approved for Public Release; Distribution Unlimited #21-3978.
