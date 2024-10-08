# An Epic Filesystem Quest

>This program is the perfect example of never give up. It requires a lot of patience to solve

We learned the concepts of different commands such as `cd`,`ls`, and `cat`. So we are using all those learnt in a long program that is progressing based on clues to find the flag.
	This challenge, I have used all the commands learnt in files. And I have accordingly used the commands based on the condition/clues they give because any other commands used in the place would result in the flag burning up and challenge restarting. So, A long, patient and careful application of 
commands yielded the flag

```bash
giridhar@LAPTOP-EQ112OJM:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
chacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
NOTE  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
bin   challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:/$ cat NOTE
Great sleuthing!
The next clue is in: /opt/aflplusplus/qemu_mode/qemuafl/scripts/simplebench

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/aflplusplus/qemu_mode/qemuafl/scripts/simplebench
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/scripts/simplebench$ ls -a
.  ..  .POINTER  bench-backup.py  bench-example.py  bench_block_job.py  bench_prealloc.py  bench_write_req.py  results_to_text.py  simplebench.py
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/scripts/simplebench$ cat .POINTER
Tubular find!
The next clue is in: /opt/angr-management/_internal/jedi/third_party/typeshed/third_party/2and3/click

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/scripts/simplebench$ cd /opt/angr-management/_internal/jedi/third_party/typeshed/third_party/2and3/click
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/typeshed/third_party/2and3/click$ ls -a
.   .BLUEPRINT    _termui_impl.pyi  decorators.pyi  formatting.pyi  parser.pyi  testing.pyi  utils.pyi
..  __init__.pyi  core.pyi          exceptions.pyi  globals.pyi     termui.pyi  types.pyi
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/typeshed/third_party/2and3/click$ cat .BLUEPRINT
Tubular find!
The next clue is in: /opt/linux/linux-5.4/drivers/net/wireless/mediatek/mt76/mt7603
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/typeshed/third_party/2and3/click$ cd /opt/linux/linux-5.4/drivers/net/wireless/mediatek/mt76/mt7603
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/wireless/mediatek/mt76/mt7603$ ls -a
.  ..  Kconfig  Makefile  TRACE  beacon.c  core.c  debugfs.c  dma.c  eeprom.c  eeprom.h  init.c  mac.c  mac.h  main.c  mcu.c  mcu.h  mt7603.h  pci.c  regs.h  soc.c
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/wireless/mediatek/mt76/mt7603$ cat TRACE
Tubular find!
The next clue is in: /usr/share/racket/pkgs/pict
hacker@commands~an-epic-filesystem quest:/opt/linux/linux-5.4/drivers/net/wireless/mediatek/mt76/mt7603$ cd /usr/share/racket/pkgs/pict
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/pict$ ls -a
.  ..  GIST  LICENSE.txt  info.rkt
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/pict$
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/pict$ cat GIST
Yahaha, you found me!
The next clue is in: /usr/local/lib/python3.8/distpackages/jedi/third_party/typeshed/third_party/2and3/attr

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/pict$ cd /usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/attr
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/attr$ ls -a
.  ..  SECRET  __init__.pyi  _version_info.pyi  converters.pyi  exceptions.pyi  filters.pyi  validators.pyi
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/attr$ cat SECRET
Tubular find!
The next clue is in: /usr/share/racket/pkgs/drracket/help/compiled

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/attr$ ls /usr/share/racket/pkgs/drracket/help/compiled
SNIPPET-TRAPPED  bug-report_rkt.dep  bug-report_rkt.zo  bug-report_scrbl.dep  bug-report_scrbl.zo  info_rkt.dep  info_rkt.zo
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/attr$ cat /usr/share/racket/pkgs/drracket/help/compiled
/SNIPPET-TRAPPED
Tubular find!
The next clue is in: /opt/linux/linux-5.4/tools/arch/s390/include/uapi
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/third_party/2and3/attr$ cd  /opt/linux/linux-5.4/tools/arch/s390/include/uapi
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/tools/arch/s390/include/uapi$ ls -a
.  ..  ALERT  asm
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/tools/arch/s390/include/uapi$ cat ALERT
Yahaha, you found me!
The next clue is in: /opt/radare2/shlr/mpc
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/tools/arch/s390/include/uapi$ cd /opt/radare2/shlr/mpc
hacker@commands~an-epic-filesystem-quest:/opt/radare2/shlr/mpc$ ls -a
.  ..  HINT  Makefile  deps.mk  libmpc.a  mpc.c  mpc.d  mpc.h  mpc.o
hacker@commands~an-epic-filesystem-quest:/opt/radare2/shlr/mpc$ cat HINT
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{gME1Y56A9WP4Q1sJUBi_HQbI9LX.dljM4QDL2kTN0czW}
```

## References Used:
None
