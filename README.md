# GitHub Actions Part-1 Basics


Status of Last Deployment:<br>
<img src="https://github.com/adv4000/github-actions-part-1-basics/workflows/My-GitHubActions-Basics/badge.svg?branch=master"><br>


Copyleft by Denis Astahov ADV-IT 2019.


## Create virtual environment
python3 -m venv .venv

## Activate virtual environment
source .venv/bin/activate

## Create requirements.txt
echo "Flask" > requirements.txt

## Install Python libs
python3 -m pip install -r requirements.txt

## Check flask version
python3 -m flask --version

## Local execution
python3 -m flask --app application run --debug