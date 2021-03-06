# Lapio
* Näille palvelimille kirjaudutaan yliopiston tunnuksilla:

* melkki.cs.helsinki.fi
* melkinpaasi.cs.helsinki.fi
* shell.cs.helsinki.fi
* melkinkari.cs.helsinki.fi

* ``` man ls ```  
* ``` cat esimerkki.txt ``` cat (katenoi), joka tulostaa suoraan tiedoston sisällön komentorvissa
* ``` head -n 1 esimerkki.txt ``` Show the first line of the file 
* ``` tail -n 2 esimerkki.txt ``` Show the last two lines of the file
* ``` grep "salai" päiväkirja.txt ``` grep (search globally for a regular expression and print)
* ``` -n ``` or ```--line-number``` option tells ```grep``` to show the line number of the lines containing a string that matches a pattern.
* ``` ^ ``` 正则表达式， 开头的字符 例如 ```grep -i "^word" new.txt ``` 以word字符串开头的行，大小写不限
* ``` $ ``` 正则表达式， 结尾的字符 例如 ```grep -i "word$" new.txt ``` 以word字符串结尾的行，大小写不限
* ``` ls | grep muisto ``` 如果没有pipe ``` | ```, 需要先将ls输出导入到文件再对文件使用grep
* ``` > ```,  ``` > ``` 更改全部  ``` >> ``` 添加到文件后方
* ``` < ```

## SSH
* ``` ssh tunnus@melkki.cs.helsinki.fi ``` muodostaa yhteyden osaston koneelle
* ``` ssh-keygen ``` julkinen avain lisätään palvelimen polkuun ``` ~/.ssh/authorized_keys ```
* ``` scp polku/kopioitavaan/tiedostoon tunnus@palvelmen.osoite:polku/kohdekansioon ``` jonka avulla on mahdollista kopioida tiedostoja palvelimelta toiselle (vertaa komentoon ```cp```).
* ``` ssh-copy-id -i ~/.ssh/mykey user@host ``` Julkisen avaimen kopioiminen onnistuu, vaikka .ssh/ kansio tai ``` ~/.ssh/authorized_keys ``` ei ole luotuna.
* ``` eval $(ssh-agent -s) ```, joka tarkistaa että ssh-agentti on toimintavalmiudessa.
* ``` ssh-add ``` lisätään ssh-agentille yksitysavain

## Wget (world wide web get)
* ``` wget sivun.osoite ```

## wc(word count)
* ``` wc tiedosto``` is used to find the number of lines, characters, words, and bytes od a file.

## Oikeudet
* Oikeudet ja omistajuudet selviävät ```ls```-komennon ```-l```-vivun avulla.

## chmod(change mode)
![](https://tkt-lapio.github.io/assets/permission-selitys.png)
* r = lukuoikeus
* w = kirjoitusoikeus
* x = ajo-oikeus
* u = tiedoston omistaja
* g = ryhmään kuuluvat
* o = kaikki muut käyttäjät

* Väliviiva ```-``` argumentti poistaa oikeuden, ja plussa ```+``` antaa oikeuksia.

* ```chmod u+x esimerkki.txt``` antaa tiedoston omistajalle oikeuden ajaa tiedosto.

* ```chmod o-w esimerkki.txt``` poistaa muilta käyttäjiltä oikeuden kirjoittaa tiedostoon.

* ```chmod go+r esimerkki.txt``` antaa ryhmälle ja muille käyttäjille oikeuden lukea tiedoston.

# skirptit
* Alkuun tulee ```#!/bin/bash```. Skriptitiedostojen nimet myös yleensä lopetetaan päätteellä ```.sh```.
* ```echo "Hello World!"```. 回声
* ```TEST="Unix Programming"``` ```echo $TEST``` environment variables are set without using the $ sign but while accessing them we use the $ sign as prefix


* watch: toista komentoa tietyin väliajoin
* && tai ;: ketjuta komentoja peräjälkeen
* alias: määrittele komennoille aliaksia, joiden avulla voit kutsua niitä esimerkiksi nopeammin.
* &: kirjoittamalla merkin komennon loppuun sen aloittama prosessi jää taustalle, eikä lukitse komentoriviä
* history: tarkastele komentohistoriaa
* Ctrl + r: etsi komentoja omasta historiasta hakusanoilla



