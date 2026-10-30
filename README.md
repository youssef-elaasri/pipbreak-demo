# pipbreak demo

A tiny Flask app pinned to **Flask 2.2.5**, with Dependabot set to update **Werkzeug** only.

Flask 2.2 declares `Werkzeug>=2.2.2`, so pip happily installs Werkzeug 3 - which removed APIs
Flask 2.2 calls. Dependabot's PR installs cleanly; the app breaks at runtime.

The [pipbreak](https://github.com/youssef-elaasri/pipbreak) action runs on that PR, compares the
environment before and after the update, and comments with exactly what breaks. See the open
pull requests.

The whole setup is [one workflow file](.github/workflows/pipbreak.yml).
