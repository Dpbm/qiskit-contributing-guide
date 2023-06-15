# Guide
This repo, contains some step by step guide for contributing for qiskit-terra

>Obs: This is not an official guide, so if you want to collaborate too, please, check the official documentation:
[qiskit.org](https://qiskit.org/documentation/contributing_to_qiskit.html). If you want to collaborate to `qiskit-terra`, check [this one too](https://github.com/qiskit/qiskit-terra/blob/main/CONTRIBUTING.md).

>Also, this repo aims to help who wants to fix some bugs. If you are adding a new feature, or making something different, you may need to check the full documentation first!!

>I've created this just to remind me what I need to do before I create a pull request

## tools

* python3 (in my case 3.8)
* pip
* [anaconda](https://www.anaconda.com/)

## preparing the environment

1. fork the qiskit project
2. clone to a local directory:
```bash
#example:
git clone https://github.com/{Username}/qiskit-terra.git
cd qiskit-terra
```
3. create conda environment
```bash
conda create -y -n QiskitDevenv python=3.8.15
conda activate QiskitDevenv
```

4. install dependencies
```bash
pip install .
pip install -U tox reno
```

5. create a new branch for you modifications

```bash
git checkout -b branch-name
```

## Tests

To run your tests:
```bash
tox -n --
```

You can also specify the python version like:

```bash
#example for python 3.8
tox -epy38 -n --
```

Also specify a single test suite:
```
tox -- -n test/python/circuit/test_circuit_qasm.py
```

## Lint

To check if your code follow the style patterns run:

```bash
tox -eblack
tox -elint
```

## docs

After all changes, create a release note using `reno`. Make sure to follow the patterns!

```
reno new release-note-title
reno report
```

## Finishing

In the end, just push your modifications `to your fork`, then make a pull request for `qiskit-terra`
