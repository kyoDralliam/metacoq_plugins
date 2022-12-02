# MetaCoq plugins for nested inductive types

This repository contains a partial update of
https://github.com/uds-psl/metacoq_plugins
to coq 8.16 and metacoq version 1.1.1

The originality of the work is to be credited to the authors of the
linked repository above.

For now, only the `subterm` repository is expected to work



## Installation

```sh
opam repo add coq-released https://coq.inria.fr/opam/released

opam install coq-metacoq-pcuic.1.1.1+8.16 coq-metacoq-pcuic
```

## Development setup

```sh
opam repo add coq-released https://coq.inria.fr/opam/released

opam install coq-metacoq-pcuic.1.1.1+8.16 coq-metacoq-pcuic
```

To compile a subproject with name `SUBPROJECT` use `make -C SUBPROJECT`. E.g. use `make -C parametricity` to compile the parametricity plugin.


Some subprojects may depend on others, for instance the nested induction plugin depends on the parametricity plugin.
This means one needs to run `make -C parametricity && make -C parametricity install` before running `make -C nested-induction`.

<!-- ## Nested Induction Principles -->


## Subterm Relations

Subterm relation generation can be seen in action in `subterm/test.v`.
The main entry point function `subterm` takes a template-coq program for an inductive (as obtained with `<# myInductive #>`)
and generates a new inductive `myInductive_direct_subterm` describing the direct subterms of the inductive in the signature of its constructors.

Current limitations:
- Does not work with non-uniform parameters, with nested-inductive types.
- Does not deal with occurences of mutual inductive types.


<!-- ## Pickle/Unpickle -->


