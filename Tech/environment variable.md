An **environment variable** is a named value available to a running program. Programs use environment variables to read settings such as database addresses, API keys, and executable search paths.

APP_MODE=development
- **Name:** `APP_MODE`
- **Value:** `development`

Think of environment variables as **settings handed to a program when it starts**.

## Why use environment variables?

They let us change a program’s configuration without changing its source code.

For example, the same application might connect to different databases:

|Environment|`DATABASE_HOST` value|
|---|---|
|Development on my laptop|`localhost`|
|Testing|`test-db.example.com`|
|Production|`prod-db.example.com`|
The application reads `DATABASE_HOST` and connects to the specified host.

## Where do environment variables live?

**Each running process has its own environment stored in memory.**

A **process** is a running instance of a program—for example, a shell, Python application, or Node.js server.

Its environment can be thought of as a dictionary:

PATH=/opt/homebrew/bin:/usr/bin:/bin
HOME=/Users/srujan
APP_MODE=development

Environment variables can originate from:
- Operating system and login configuration.
- Shell startup files.
- Commands entered in a terminal.
- A project’s `.env` file, when loaded.
- An IDE, container, CI workflow, or deployment platform.