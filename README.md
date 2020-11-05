# Python application deployer

This command line script exists for fast deployment to remote server.
Was mostly created for test purposes and might have some issues.

## Used languages/packages

Python3.6, [click](https://click.palletsprojects.com/en/7.x/),
[paramiko](http://www.paramiko.org/) and [scp](https://pypi.org/project/scp/).

## Installation and usage

To install simply run `pip install py_deploy`

You can also install it from git: `pip install git+https://github.com/velykanov/py_deploy.git`

To deploy your application to the server simply run `py-deploy -t /some/dir/ -h remote_host`.
This command would deploy current directory to remote server.

Here's the full list of options:
```shell script
-i, --identity-file TEXT  SSH identity file
-p, --password            Defines if password must be passed
-P, --port TEXT           SSH target port
-s, --source TEXT         Source  (default: '.')
-t, --target TEXT         Target  [required]
-h, --host TEXT           Host IP address or name  [required]
-u, --username TEXT       Remote username
-e, --exclude TEXT        Dirs names to exclude  (default: ['tests', '.git', '__pycache__'])
-v, --verbose
--version                 Show the version and exit.
--help                    Show this message and exit.
```

### Please note!

This tool won't work if your python versions are mismatched
(for instance your app is written using Python3.8 including
some specific features and you're running this tool using Python3.6).

## Changelog

| Version | Changes |
|:--------|:--------|
| 1.0.1 | Added ssh password support. Split target into separate arguments. |
