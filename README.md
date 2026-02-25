# code-search-eval-experiments

Experiment data and results for
[code-search-eval-harness](../code-search-eval-harness).

## Structure

    templates/                      config templates
    experiments/<experiment-id>/
        config.json                 experiment parameters
        tasks/                      gold evidence per task
        responses/<method>/         raw retrieval output per method
        results/<method>.json       scored output from the harness

See [templates/config.json](templates/config.json) for the experiment
config format.

## Running

python scripts/run_experiment.py --experiment <path-to-experiments>/<id>
