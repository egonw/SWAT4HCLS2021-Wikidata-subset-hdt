## Note
This work has been accomplished during the [SWAT4HCLS](http://swat4ls.org) 2021 (Semantic Web Applications and Tools for Healthcare and Life Sciences)

## ** Workflow to subset Wikidata using Wdumper and convert the output to HDT for sharing/querying **

[Shared Link](https://viewer.diagrams.net/?highlight=0000ff&edit=_blank&layers=1&nav=1&title=SWAT4HLC.drawio#R5VpZd5s4FP41Pqd9sA%2BLjeljszjLtDNpM%2BekfeqRQYASgRghYtyH%2Be1zBWIxXoInjknTPNjoSkLS%2Fe53F8UD8zTMLjiKg8%2FMxXRgaG42MM8GhqFPdRu%2BpGRZSMamWQh8Tlw1qBbckp9YCTUlTYmLk5WBgjEqSLwqdFgUYUesyBDnbLE6zGN0ddUY%2BXhNcOsgui69I64ICqk90Wr5JSZ%2BUK6sa6onROVgJUgC5LJFQ2SeD8xTzpgonsLsFFOpvFIvxbzZlt5qYxxHosuE%2B8wVcATXFn%2BcL%2B0r5EUCDS21N7EsD4xdOL9qMi4C5rMI0fNaesJZGrlYvlWDVj3mE2MxCHUQ3mMhlgpMlAoGokCEVPXChvnym5qfN77LxmhSNs%2ByZufZUrWKvcoNblWBEiUs5Q7ece7SlBD3sdgxblwBBRaOWYhhPzCPY4oEeVzdB1Km5lfjajTgQQGyBzjqvY%2BIpmqlgWFR2O7JHB58%2BXB3loYx5qUclqm6qrF8u8RlzoOcrfE0Gkj7ab0eoTBE0D9buHuscxVKUhkak%2B88y5e4TOV4FIKBnETzJK7QbFhebVfSSBYBEfg2RjmMC3AuqzakVIO5wNlua1hHT00YThUzlWuqmLqoiW6UdA4aJC%2FnHRxwY9oLHTMivjWeG2SEVs1F2Vg2idkvhY2OFDasPjlsPM3hwBXDe%2FSIXpzE%2By20jcU9s3Y6fm2s1c1%2Bg2hNuu%2FNvpdnoNmRgVsAPQ4BzQ5BlDwQFwnghWZo%2BliaO0Q7%2BHo3uk9YNPJ%2FvofGv7Lj4iTPNcOY4yQB%2BLbSsxuJ5ZIBx16%2BMeuflOX%2BQAiZ3H6U5zZmLgcVjXzGfIpHsDKIUmdgzvJD69eYLW6W4iqcafaDE0y%2FXk91f5pcBvOb6IP5%2BUsVdItPnMVgajARMtGIMuTWq1be6Lirl8pCtWr6cjDKoZjTdYdiWsd0KB9%2BU38y7upPjGc6FDX1hhHYYhVZxq3IolstgIuNqVktjKtt%2FH%2FYx097Kko8%2FCNxCI4cnPxI0nmCxSgS4KE2%2B52WGUEJGstHAAdRiinzOQphIGT2BHYPSUSr76bueIp5HslwWb8fKNRXob0K9ZNuob4N3OFCvf3rJeirdNaOR2e9a4au95qhl9vcwLskRlFJppglYhhzBsRLSOTL7IDjkD3KFJkAYXwkV3ICoI8DhEmkFiMHoIeGTBQ0IvNolKcPaUzzzNqDj6uvV8n7Bnuba%2FaebJstl2h3zLVfjoCTPgh4SFJ0DnK9cqJDLLq%2B%2FetPeeIYO9LYPSZL0Lvynkh7B0oEnWVC8kFZfhGwZMNxGHcLGuXjRCAJEarr4zidU5IEFW3aF0fFTjyWR2%2BHUcZXEuiBYWrw53nr2e0%2BiTcjI8ZhhzNdG00nE1DJDH%2BCADyaGJZU0BOZ85PTN6S%2Blaw4WyGuvMOuS4C%2FcwWWYMiyRepOPvs4whyJXJlzaUIXqfRXPGQ7tbupgOmgNZ%2BIIJ2rUgEADjm8ZVZWWLe5AYgc%2BN3q2%2BM9W%2FXYoQDbmS71fSFpbShE7A3e1n4xb9tzJTLo7d8DVkcv%2FdxK5HnwWPtWDHmS%2FnYLhrH92gqGsoLZAJEKX7W2S4coO4ZJrpiP%2BZVUnG0PZBV2%2Bi7H3Yoo66ymlMQJ7gIapadVwDVdhG3PkZmy4OwBN3osx8Zz70B%2BsQ2rtu4YxxtQHb8YqttLhgOjar5dVKfma0N1cixUjbeLqtm6s5n0DereMVLdqgWueIshUte048VIaNa%2FbymuSetfCZnn%2FwE%3D)

The same diagram is below:

![](https://i.imgur.com/nBFFcuK.png)

**Steps:**

1.  I downloaded a Wikidata dump of 2014 (~4 GB compressed) from [here](https://drive.google.com/uc?id=1JeowPytImF08kch7RJ71g7sHhbPn93MQ&export=download)

2.  I obtained the JSON specs file for Wdumper, generated by Guillermo [here](https://github.com/ingmrb/WikidataSubsetting/blob/main/Wdumper%20method/life_sciences.json) which was generated to subset Wikidata according to the model published in [https://doi.org/10.7554/eLife.52614](https://doi.org/10.7554/eLife.52614)

3. I created a dokcer image for both "Wdumper" and "hdt-java" and provided them on DockerHub with example usage ([Wdumper](https://hub.docker.com/r/aammar/wdumper) & [hdt-java](https://hub.docker.com/r/aammar/hdt-java)). So, they can be used directly without clone the GitHub repos and building the docker images.

4. I ran the wdumper tool using the WD dump and the JSON specs as input. The output was a (.nt.gz) file.

* File Size compressed (.gz): ~500MB </br>
* File Size Uncompressed (.nt): 6.64GB

Command used:

```shell=bash
docker run -it \
           --rm --name wdumper \
           -v YOUR_DATA_PATH_HERE:/data \
           -e DUMPS_PATH=/data \
           aammar/wdumper \
           /data/wikidata_2014_dump.json.gz \
           /data/life_sciences.json
```

5. Next, I tried to run the hdt-java docker on the nt.gz file but apparently, som IRIs contains illegal characters and the file needs cleaning.

6. I unzipped the nt file, cleaned it (regex), and zipped it again, like this:

```shell=bash
gunzip wdump-1.nt.gz

sed -i -E 's/(<.*)}(.*>)/\1\2/' wdump-1.nt
sed -i -E 's/(<.*)\\n(.*>)/\1\2/' wdump-1.nt
sed -i -E 's/(<.*)\|(.*>)/\1\2/' wdump-1.nt

gzip wdump-1.nt
```

7. I ran the hdt-java (rdf2hdt.sh command) on the .nt.gz file to get the HDT compressed file (still running now).
Command used:

```shell=bash
docker run -it \
           --rm --name hdt \
           -v YOUR_DATA_PATH_HERE:/data \
           aammar/hdt-java \
           rdf2hdt.sh \
           /data/wdump-1.nt.gz \
           /data/life_sciences_subset.hdt

```

8. The results of the compression are really good:

>File converted in: 16 min 37 sec 9 ms 389 us </br> 
>Total Triples: 60161218 </br>
>Different subjects: 5715877 </br>
>Different predicates: 802 </br>
>Different objects: 38767299 </br>
>Common Subject/Object:216743 </br>
>HDT saved to file in: 14 sec 493 ms 307 us </br>

* HDT file size: 589MB 
* Input file size (.nt): 6.64GB = 6800MB
* (**Compression ratio:** 589 / 6800 = **8.66%**)

**Next step**, is to try to run an instance of Fuiski server (Docker) provided by Jose on top of this HDT file and try some queries.
