# code-search-eval-experiments

Experiment data and results for
[code-search-eval-harness](../code-search-eval-harness).

## Structure

    templates/                      config and task templates
    experiments/<experiment-id>/
        config.json                 experiment parameters
        tasks/                      gold evidence per task
        responses/<method>/         raw retrieval output per method
        results/<method>.json       scored output from the harness

See [templates/config.json](templates/config.json) and
[templates/task.json](templates/task.json) for the expected formats.

## Running

    export ANTHROPIC_API_KEY=...
    export VOYAGE_API_KEY=...

    # 1. Start Qdrant
    docker run -p 6333:6333 -v qdrant_data:/qdrant/storage qdrant/qdrant

    # 2. Index the repo
    python ../code-search-eval-harness/scripts/index_repo.py --experiment experiments/<id>

    # 3. Run
    python ../code-search-eval-harness/scripts/run_experiment.py --experiment experiments/<id>
