# Bootcamp Description

Add description here

## Deploying the Lab

### Prerequisites

- Add list of prerequisite here (minimum Hardware requirements, OS, containers, and other base dependencies)

### Tested Environment

Add the labs where tested (e.g., DGX H100 80GB, workstation with RTX A500 GPU )

### Deploying with Container

#### Docker

Build the Docker image:

```bash
docker build -t tech-team2:latest .
```

Run JupyterLab from the container:

```bash
docker run --rm -it --gpus all -p 8888:8888 -v "$PWD/workspace:/workspace" tech-team2:latest jupyter lab --ip=0.0.0.0 --port=8888 --allow-root --no-browser
```

#### Singularity / Apptainer

Build the image:

```bash
apptainer build tech-team2.sif Singularity
```

Run JupyterLab from the image:

```bash
apptainer exec --nv --bind "$PWD/workspace:/workspace" tech-team2.sif jupyter lab --ip=0.0.0.0 --port=8888 --no-browser
```

### Deploying with Python

Use this path only when the labs do not require the container image or when you are preparing a lightweight local environment:

```bash
python -m venv .venv
. .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Dataset setup:

Follow the dataset instructions in the relevant lab notebook or place prepared datasets under `workspace/data/`.

### Known Issues

- List commonly encountered issues and solutions here

## Repository

- Owner: `programmah`
- Default branch: `main`
- Estimated duration: Add Bootcamp tutorial duration
