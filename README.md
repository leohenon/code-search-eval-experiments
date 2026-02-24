# code-search-eval-experiments

Experiment data and results for
[code-search-eval-harness](../code-search-eval-harness).

## Structure

Each experiment is a self-contained directory:

    experiments/<experiment-id>/
        config.json                 experiment parameters
        tasks/                      gold evidence per task
        responses/<method>/         raw retrieval output per method
        results/<method>.json       scored output from the harness

## Scoring

    python -m scripts.run_eval \
        --tasks experiments/<id>/tasks \
        --responses experiments/<id>/responses/<method> \
        --out experiments/<id>/results/<method>.json
