# qm6600_me_enable
ELSKY QM6600-2c enable Intel ME

[website](http://www.miniboard.cn/product/?8_59.html)

# How to
1. Download Flash Image Tool and Flash Programing Tool.

2. dump the origin dedc file. <br>
```
fpt -desc -dump desc.rom
```

3. open desc dump file. Flash Image > Descriptor Region > VSCC Table., add the spi infomation.default VSCC table contains 1F4700 (Atmel AT25DF321) and EF4017 (Winbond W25Q64).But actual spi is Winbond W25Q32, so add EF4016 to the VSCC Table.

4. flash the modified dump file back.one of them<br>
```
fpt -rewrite -desc -f desc-mod.rom
```
and then
```
fpt -greset
```

# Reference
* https://github.com/corna/me_cleaner/issues/80
* https://www.win-raid.com/t1658f39-Guide-Clean-Dumped-Intel-Engine-CS-ME-CS-TXE-Regions-with-Data-Initialization.html
