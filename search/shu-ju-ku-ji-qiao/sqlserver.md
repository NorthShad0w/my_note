# sqlserver

error based injection&#x20;

can use    \~      to bypass WAF example:safedog

select xxx from asd= 1 ------- no

\~1 = select xxx from \[asd] ---------------- yes



esay use xp\_cmdshell    (file upload function)

{% embed url="https://raw.githubusercontent.com/Alamot/code-snippets/master/mssql/mssql_shell.py" %}

