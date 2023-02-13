# gabibbo kontakte
## web
come si può notare la webapp usa mongodb e non sanitifica gli input, faceva solo un check per `username === 'admin'`
e quindi con NoSql si può semplicemente fare `'{"username":{"$ne": null}}'` che prende tutti gli entry del database
references : https://book.hacktricks.xyz/pentesting-web/nosql-injection#basic-authentication-bypass


flag{n0_5ql_n0_1nj3c710n_n0_5cu54_1n73nd3v0_n0_p4r7y}