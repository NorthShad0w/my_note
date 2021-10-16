# sqlserver

error based injection 

can use    \~      to bypass WAF example:safedog

select xxx from asd= 1 ------- no

\~1 = select xxx from \[asd] ---------------- yes

