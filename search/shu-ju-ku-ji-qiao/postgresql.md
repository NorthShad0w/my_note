# postgresql

## config:

enable sql log:

postgresql.conf

```
log_statement = 'all'
```

## sql query:

`select currentsetting('is_superuser');`

## bypass:

**bypass quote**

CHR() || CHR()           #basic queries ONLY

_**Using Dollar-signs ( >= version 8 PostgreSQL):**_

Essentially, two dollar characters (\$$) can be used as a quote.

a single one($) can indicate the beginning of a "tag".

