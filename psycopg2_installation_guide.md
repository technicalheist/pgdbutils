# Troubleshooting psycopg2 Installation Issues

## Install psycopg2
``` pip install psycopg2```

**Question 1: Error during `psycopg2` installation with missing `pg_config`**

```plaintext
Error: pg_config executable not found.

pg_config is required to build psycopg2 from source. Please add the directory
containing pg_config to the $PATH or specify the full executable path with the
option:

    python setup.py build_ext --pg-config /path/to/pg_config build ...

or with the pg_config option in 'setup.cfg'.

If you prefer to avoid building psycopg2 from source, please install the PyPI
'psycopg2-binary' package instead.

For further information please check the 'doc/src/install.rst' file (also at
<https://www.psycopg.org/docs/install.html>).
```

**Solution 1: Install `psycopg2-binary`**

```bash
pip install psycopg2-binary
```

---

**Question 2: Error during `psycopg2` installation with unrecognized `--pg-config` option**

```plaintext
Running setup.py install for psycopg2 ... error
error: option --pg-config not recognized
```

**Solution 2: Set `PATH` environment variable**

1. Identify the path to your `pg_config` executable.

2. Set the `PATH` environment variable to include the directory containing `pg_config`:

   ```bash
   export PATH=/path/to/pg_config_directory:$PATH
   ```

   Replace `/path/to/pg_config_directory` with the actual path to the directory containing `pg_config`.

3. Install `psycopg2` again:

   ```bash
   pip install psycopg2
   ```

Alternatively, consider using `psycopg2-binary`:

```bash
pip install psycopg2-binary
```

These solutions should help resolve issues related to `pg_config` during `psycopg2` installation.
```
