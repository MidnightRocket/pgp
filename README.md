I MidnightRocket use the following key structure:
A root of trust key:
```
pub	rsa4096/F9B8BB160BBCC79C 2022-05-09 [SC]
	Key fingerprint = 4D83 0275 D62C 5184 4463  7155 F9B8 BB16 0BBC C79C
uid		MidnightRocket (Long-term Root key) <45201103+MidnightRocket@users.noreply.github.com>
```

And a daily use key:
```
pub	ed25519/DA1FD6C6670E36D7 2022-05-09 [SC]
	Key fingerprint = DBFB 2472 B397 7CD7 93FE  A9D1 DA1F D6C6 670E 36D7
uid		MidnightRocket (Daily usage key) <45201103+MidnightRocket@users.noreply.github.com>
sub	cv25519/A2443C54AF560EC2 2022-05-09 [E]
sub	ed25519/CBCE0BC869046ECE 2022-05-09 [A]
```


The `Long-term Root key` is used only to sign special statements like this one, and to sign keys that I personally am in control of.
This key was generated in an air-gaped environment, and then imported to an OpenPGP smart card, to perform signatures on less secure systems. The smart card is kept physically secure, and is only taken out of storage when needed.

The `Daily usage key` is also generated in an air-gaped environment, and imported to another OpenPGP smart card. This key is carried around, and is used in daily operations, like signing commits etc. This key is naturally more susceptible to loss or theft, than the `Long-term Root key`. In case of loss or theft the `Long-term Root key` can be used to establish trust in a new `Daily usage key`.

I use this scheme over the 'separated main and sub keys', as I think it is a more flexible approach.



<br><br>

A key specifically for signing git commits on mobile devices: 

```
pub   ed25519/E688E1437173E2F8 2023-06-12 [SC] [expires: 2025-06-11]
      Key fingerprint = C56D 2BA5 845A 308E 3D3F  9006 E688 E143 7173 E2F8
uid                 [ultimate] MidnightRocket (For signing git commits on mobile devices only) <git@midnightrocket.dev>
sub   ed25519/8468965DB6E9895B 2023-06-12 [S] [expires: 2025-06-11]
```
