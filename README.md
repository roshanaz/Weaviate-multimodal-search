# Multimodal Search with Weaviate

This project demonstrates multimodal search capabilities using Weaviate, allowing for combined text and image search functionality.

## Prerequisites

- Python 3.10 or higher
- Docker and Docker Compose
- `uv` package manager (recommended) or pip

## Setup Instructions

### 1. Install uv (if not already installed)

```bash
# Install uv using pip
pip install uv

# Or using curl (recommended)
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### 2. Initialize the Python Environment

```bash
# Initialize uv environment
uv init

# Install dependencies
uv sync
```

### 3. Start Weaviate Services

The project uses Weaviate with CLIP for multimodal vector search. Start the services using Docker Compose:

```bash
docker-compose up -d
```

This will start:
- Weaviate instance on port 8080
- CLIP inference API for image/text embeddings

### 4. Running the Notebook

1. Ensure your Python environment is activated
2. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
3. Open `create_collections.ipynb` in your browser
4. Execute the notebook cells sequentially

## Project Structure

- `docker-compose.yml`: Docker configuration for Weaviate and CLIP services
- `create_collections.ipynb`: Main notebook with code examples
- `pyproject.toml`: Python project dependencies

## Troubleshooting

- If Weaviate services fail to start, ensure ports 8080 and 50051 are not in use
- Check Docker logs using: `docker-compose logs`
- Verify Weaviate is running: `curl http://localhost:8080/v1/meta`

## Stopping the Services

To stop the Weaviate services:

```bash
docker-compose down
```
