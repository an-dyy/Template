.PHONY: clean clean-build clean-pyc clean-test coverage dist docs help install lint lint/flake8 lint/black

clean: clean-pyc clean-test

clean:
	find . -name '*.pyc' -exec rm -f {} +
	find . -name '*.pyo' -exec rm -f {} +
	find . -name '*~' -exec rm -f {} +
	find . -name '__pycache__' -exec rm -fr {} +

clean-test:
	rm -fr .tox/
	rm -f .coverage
	rm -fr htmlcov/
	rm -fr .pytest_cache

lint: lint/flake8 lint/black

lint/flake8:
	flake8 {{ cookiecutter.repo_name }} tests

lint/black:
	black --check {{ cookiecutter.repo_name }} tests

test:
	pytest

coverage:
	pytest ./ --asyncio-mode=strict --cov --full-trace

install: clean
	python setup.py install
