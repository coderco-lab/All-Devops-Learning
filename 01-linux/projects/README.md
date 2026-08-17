282
283
284
285
286
287
288
289
290
291
292
293
294
295
296
297
298
299
300
301
302
303
304
305
306
307
308
309
310
311
312
313
314
315
316
317
318
319
320
321
322
323
324
325
326
327
328
329
330
331
332
333
334
335
336
337
338
339
340
341
# Bandit Levels 0 to 20
```

---

## Level 17 to Level 18

Goal: Compare `passwords.old` and `passwords.new` and find the changed line.

```bash
diff passwords.old passwords.new
```

The line shown with `>` in `passwords.new` is the next password.

Cleaner extraction:

```bash
diff passwords.old passwords.new | grep ">" | awk '{print $2}'
```

---

## Level 18 to Level 19

Goal: The `.bashrc` logs you out when you SSH in.

Run a command directly without starting an interactive shell.

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
```

---

## Level 19 to Level 20

Goal: Use the setuid binary in the home directory.

Inspect it first:

```bash
ls -l
./bandit20-do
```

Then use it to read the password file as `bandit20`:

```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```

---

## Notes

- Save each password as you go
- Some exact file names or ports may differ in your own session flow if you make mistakes and retry
- For Level 12, the repeated decompression path is best handled by checking `file` after every step
- For Level 16, the SSL port with the key is commonly found during the scan phase, but always trust your own `nmap` result first

