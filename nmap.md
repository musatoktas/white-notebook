 # Pratik Bilgilerle NMAP
 Hedef makine portlarını tespit edip aktif pasif bilgi toplayan yazılım. IP ve port taraması, TCP UDP taramaları yapar.
</br>
</br>
 
![nmap](https://github.com/musatoktas/white-notebok/blob/master/nmap.PNG?raw=true "NMAP ekran görüntüsü")

</br>
IP'lerin sonlarını değiştirerek taratmak
</br>

```
nmap 192.168.1.1,3,5,7,9
```
</br>
IP Aralığını taratmak
</br>

```
nmap 192.168.1.1-10
```

</br>
Nmap Topport ile ilk 10 yoğun portları tarama
</br>

```
nmap --top-port 10 192.168.1.1
```

