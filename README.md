# Analýza datagramů ve Wiresharku

## Co je Wireshark?

Wireshark je softwarový nástroj, který umožňuje:
- sledovat datagramy, které jsou přijímány a odesílány síťovou kartou.
- prozkoumat podrobně datagram v hexadecimálním zápisu (jako posloupnost čísel v šestnáctkové soutavě) i v&nbsp;podobě určené pro snadné čtení.

Wireshark je k&nbsp;dispozici zdarma a mohou ho využívat například správci sítě při analýze datového toku!

> POZOR!!! Wireshark pouštějte vždy POUZE v&nbsp;domácí síti nebo ve **cvičné** síti! Při snímání datagramů můžete za jistých okolností získat obsah datagramů jiných osob, což by bylo porušení soukromí při komunikaci!
>
> I&nbsp;správce sítě by měl vždy předem použití Wiresharku v&nbsp;pracovní síti ohlásit, popsat účel sledování a jaká data se budou sledovat!

## Postup úlohy:

1. Nejprve si ve VirtualBoxu připravte virtální stroj s&nbsp;webovým serverem<br />
    Obraz virtuálního disku s&nbsp;nainstalovaným webovým serverem máte připraven:<br />
    - na serveru `\\dilna` ve složce `\\dilna\VM-sablony`
    <br />![Vytvoření nového VM ve VirtualBoxu](img/wireshark_01_vbox-new.png)
1. Ponechte 1&nbsp;GB operační paměti a připojte obraz virtuálního disku:<br />
    ![Nastavení nového virtuálního stroje](img/wireshark_02_vbox-create.png)
1. Virtuální stroj se serverem WWW spusťte:
    <br />![Spusťte virtuální stroj se serverem](img/wireshark_03_vbox-run.png)
1. Spusťte druhý virtuální stroj &mdash; klienta<br />
    Zatímco server bude poskytovat webový obsah ke stažení, virtuální stroj s&nbsp;Windows bude sloužit ke spuštění Wiresharku a snímání datagramů.<br />![Spusťte virtuální stroj s Win 10](img/wireshark_04_win10lab.png)
1. &nbsp;<br />![](img/wireshark_05_nastaveni.png)
1. V&nbsp;nastavení síťové karty obou strojů zvolte položku `Vnitřní síť`.<br />![Přepnutí do vnitřní sítě VirtualBoxu](img/wireshark_060_vnitrni-sit.png)
1. Nastavte IP adresu klientského stroje na 192.168.0.10/24<br />![](img/wireshark_080_ip-adresa.png)
1. Na klientském stroji s&nbsp;Windows spusťte Wireshark<br />![](img/wireshark_070_wireshark.png)
1. V&nbsp;prohlížeči na klientském stroji otevřete webovou prezentaci ze serveru &mdash; měla by se vám zobrazit úvodní stránka Apache.<br />![](img/wireshark_090_over-web.png)
1. Spusťte snímání datagramů<br />![](img/wireshark_100_spust-snimani.png)
1. Obnovte obsah webové stránky pomocí klávesové zkratky _Ctrl+F5_<br />![](img/wireshark_110_obnov-web.png)
1. Až komunikace skončí, vypněte snímání datagramů<br />![](img/wireshark_120_ukonci-snimani.png)
1. Vyfiltrujte si pouze komunikaci HTTP v&nbsp;rámci jednoho TCP spojení<br />![](img/wireshark_140_filtr.png)
1. Prozkoumejte, zda průběh komunikace odpovídá poznatkům o fungování protokolu TCP ze 2. ročníku<br />![](img/wireshark_130_nasnimano.png)
