# Questions Academy Dataset: Questions Academy #

[![Tests](https://github.com/emerald-green-tech/questions-academy-dataset-questions-academy/actions/workflows/tests.yml/badge.svg)](https://github.com/emerald-green-tech/questions-academy-dataset-questions-academy/actions/workflows/tests.yml)

This package contains a dataset of multiple choice questions and answers, created by the [Questions Academy] developers
and contributors.

## Question Schema ##

Here's an example question:

```yaml
ID: 83f51ca5-4672-48ae-8e8a-70fe15312922

Question: >
  Three of these animals hibernate. Which one does not?

Answers:
  1: >
    Mouse
  2: >
    Sloth
  3: >
    Frog
  4: >
    Snake

Correct: 2

Explanation: |
  None

Active:
  True

Notes: >
  None

SchemaVersion: 1
```

Fields:

*   **ID**: A unique ID for the question.
*   **Question**: The question stem.
*   **Answers**: A mapping of index number and answer text.
*   **Correct**: The index number of the correct answer.
*   **Explanation**: An infrequently used, optional field that explains the answer.
*   **Active**: Whether the question is active on the [Questions Academy] website. Some questions are not displayed on
    the website, in which case they will have `Active` set to `False`.
*   **Notes**: Question related notes, not displayed on the [Questions Academy] website.
*   **SchemaVersion**: A version of the YAML schema. Only version 1 is available.

## Contributions ##

If you want to contribute questions in YAML format, please open a [pull request]. If you want to contribute in any other
format, please open an [issue].

## Testing ##

There are unit tests that validate the YAML schema and the question syntax, and spell check the questions and answers.
The tests are in separate Git repository [questions-academy-dataset-tests]. If you want to run the tests, clone this
repository including its submodules:

```sh
git clone git@github.com:emerald-green-tech/questions-academy-dataset-opentriviaqa.git --recurse-submodules
```

Or, if you have already cloned the dataset without submodules, then only fetch the submodules:

```sh
git submodule update --init --recursive
```

Then install the test dependencies:

```sh
pip install --only-deps tests/
```

Note that the `--only-deps` option was added in [pip version 26.2], so you need a recent version of `pip`. Finally, run
`pytest`:

```sh
pytest
```

You can increase the verbosity of the tests by setting the logging level to `INFO` (informational messages only) or
`DEBUG` (additional messages):

```sh
pytest --log-cli-level INFO
pytest --log-cli-level DEBUG
```

## License

This work is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License][CC-BY-SA-4.0].

<!-- Links -->
[pull request]: https://github.com/emerald-green-tech/questions-academy-dataset-questions-academy/pulls
[issue]: https://github.com/emerald-green-tech/questions-academy-dataset-questions-academy/issues
[questions-academy-dataset-tests]: https://github.com/emerald-green-tech/questions-academy-dataset-tests
[Questions Academy]: https://questions.academy/
[CC-BY-SA-4.0]: https://creativecommons.org/licenses/by-sa/4.0/
[pip version 26.2]: https://pip.pypa.io/en/stable/user_guide/#installing-only-dependencies