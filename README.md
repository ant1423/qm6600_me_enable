# qm6600_me_enable
ELSKY QM6600-2c enable Intel ME

website: http://www.miniboard.cn/product/?8_59.html

# How to
1. Download Flash Image Tool and Flash Programing Tool.

2. dump the origin file. one of them<br>
full dump:
```
fpt -dump fulldump.rom
```

desc dump:
```
fpt -desc -dump desc.rom
```

4. open full dump file or desc dump file.

5. Flash Image > Descriptor Region > VSCC Table., add the spi infomation.default VSCC table contains 1F4700 (Atmel AT25DF321) and EF4017 (Winbond W25Q64).But actual spi is Winbond W25Q32, so add EF4016 to the VSCC Table.

6. flash the modified dump file back.one of them<br>

full dump:
```
fpt -rewrite -f fulldump-mod.rom
```

desc dump:
```
fpt -rewrite -desc -f desc-mod.rom
```
