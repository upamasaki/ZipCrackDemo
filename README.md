# ZipCrackDemo

zipファイルを解析するサンプルファイルです．
*悪用厳禁です!!!

## 1. 必要なもの

- fcrackzip (kali linuxならデフォルトで入っています．)

## 2. パスワード付きのzipファイルを作る

ZIP内のファイルを適当に作成します．
ファイルは適当にカレンダーのtxtファイルでも作成しましょう．

```CMD
┌──(masaki㉿masaki)-[~/ドキュメント/git-repo/ZipCrackDemo]
└─$ calendar 
 6月 24 	Senate repeals Gulf of Tonkin resolution, 1970
 6月 24 	The capital of Jamaica, Kingston, is founded, 1664
 6月 24 	Battle of Carabobob in Venezuela
 6月 24 	Fisherman's Day in Madagascar, Mozambique and Somalia
 6月 24 	Kings Day in Spain
 6月 24 	Peasants Day in Peru
 6月 24 	St. Jean-Baptiste Day in Quebec
 6月 24 	Jeff Beck is born in Surrey, England, 1944
 6月 24 	Muere en un accidente de aviación Carlos Gardel, 1935
 6月 24 	Chris Faulhaber <jedgar@FreeBSD.org> born in Springfield, Illinois, United States, 1971
 6月 24 	N'oubliez pas les Jean-Baptiste !
 6月 24 	S'il pleut à la saint Jean,
	Guère de vin ni de pain.
 6月 24 	Ermordung von Reichsaußenminister Rathenau, 1922
 6月 24 	Beginn der Berliner Blockade, 1948
 6月 24 	Iván
 6月 24 	Midsummer (quarter day)
 6月 25 	Eric Arthur Blair (a.k.a. George Orwell) born, 1903
 6月 25 	Custer's Last Stand at Little Big Horn, 1876
 6月 25 	North Korea invades South Korea, 1950
 6月 25 	Alberto Ginastera dies in Geneva, Switzerland, 1983
 6月 25 	Georg Philipp Telemann dies in Hamburg, Germany, 1767
 6月 25 	Michael Joseph Jackson dies in Los Angeles, California, 2009
 6月 25 		Dan državnosti
 6月 25 	Bonne fête aux Prosper !
 6月 25 	Après la saint Jean, si le coucou chante,
	L'année sera rude et méchante.
 6月 25 	Begin der Korea-Krieges, 1950
 6月 25 	Georg Philipp Telemann in Hamburg gestorben, 1767
 6月 25 	Vilmos, Viola
┌──(masaki㉿masaki)-[~/ドキュメント/git-repo/ZipCrackDemo]
└─$ calendar > calender.txt    
```

次に，これをパスワード付きのZIPにします．とりあえずは数字のみのパスワードにしましょう．

```CMD
┌──(masaki㉿masaki)-[~/ドキュメント/git-repo/ZipCrackDemo]
└─$ zip -e --password=123456 calender1.zip calender.txt 
```

## 3. パスワード付きのzipファイルを解析する

下記のコマンドでパスワードを解析してみましょう．
[コマンドの詳細はこちらを参照](https://siva-hakaishin.com/computer/linux-zippass/)
```
┌──(masaki㉿masaki)-[~/ドキュメント/git-repo/ZipCrackDemo]
└─$ fcrackzip -u calender1.zip -l 2-6 -c 1a                                                                            1 ⚙


PASSWORD FOUND!!!!: pw == 123456
```

パスワードが数字かつ解析条件に数字のみの指定だと秒で終わる！！！

