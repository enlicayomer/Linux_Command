
Temel Linux Komutları

### Dosya İşlemleri

Dosyaları listeler:
```sh
$ ls
```
Gizli dosyalar dahil dosyaları listeler:
```sh
$ ls -al
```
Ev dizinine geçis yapar:
```sh
$ cd
```
Mevcut dizini gösterir:
```sh
$ pwd
```
belirtilen isimde dizin oluşturur:
```sh
$ mkdir dizin
```
dosya siler:
```sh
$ rm dosya
```
belirtilen dizini siler:
```sh
$ rm -r dizin
```
belirtilen dosyayı silmeye zorlar:
```sh
$ rm -f file
```
belirtilen dizini silmeye zorlar:
```sh
$ rm -rf dizin
```
dosya1'i dosya2'ye kopyalar:
```sh
$ cp dosya1 dosya2
```
dizin1'i dizin2'ye kopyalar; dizin2 yoksa oluşturur:
```sh
$ cp -r dizin1 dizin2
```
dosya1'in adını dosya2 yapar:
```sh
$ mv dosya1 dosya2
```
belirtilen dosyaya sembolik bağ oluşturur:
```sh
$ ln -s dosya bağ
```
boş dosya oluşturur:
```sh
$ touch dosya
```
dosyaya girdi yönlendirir:
```sh
$ cat > dosya
```
dosyanın çıktısını sayfalayarak gösterir:
```sh
$ more dosya
```
Dosyanın ilk 10 satırını gösterir:
```sh
$ head dosya
```
Dosyanın son 10 satırını gösterir:
```sh
$ tail dosya
```
Dosyanın son 10 satırını eşzamanlı olarak gösterir:
```sh
$ tail -f dosya
```

### Süreç(Process) Yönetimi
aktif süreçleri gösterir:
```sh
$ ps
```
tüm süreçleri gösterir:
```sh
$ top
```
belirtilen süreci sonlandırır:
```sh
$ kill pid
```
belirtilen tüm süreçleri sonlandırır:
```sh
$ killall proc
```
durdurulmuş işlemi arkaplanda yapmaya devam eder:
```sh
$ bg
```
arkaplandaki içi ön plana getirir:
```sh
$ fg
```
n numaralı işi ön plana getirir:
```sh
$ fg n
```

### Dosya İzinleri
belirtilen dosyanın izinlerini rakamsal olarak değiştirmeye yarar. Her rakam
kullanıcı, gurup ve diğerlerini ifade eder ve 3 hanede kullanılır
  - 4 - okuma(r)
  - 2 - yazma(w)
  - 1 -  çalıştırma(x):
```sh
$ chmod RAKAM dosya
```
read- write, execute for all:
```sh
$ chmod 777
```
rwx for owner, rx for group and world:
```sh
$ chmod 755
```
Daha fazla seçenek için:
```sh
$ man chmod
```

### SSH
belirtilen makinaya bağlanır:
```sh
$ ssh kullanici@sunucu
```
belirtilen sunucuya belirtilen porttan bağlanır:
```sh
$ ssh -p PORT_NUMARASI kullanici@sunucu
```
parolasız giriş için ssh anahtarını belirtilen sunucuya kopyalar:
```sh
$ ssh-copy-id kullanici@sunucu
```

### Arama
belirtilen dosyalarda ifadeyi arar:
```sh
$ grep ifade dosya
```
belirtilen dosyalarda ifadeyi özyineli aratır:
```sh
$ grep -r ifade dir
```
komutun çıksında ifadeyi aratır:
```sh
$ komut | grep ifade 
```
belirtilen dosyayı aratır:
```sh
$ locate dosya
```

### Sistem Bilgileri
mevcut saat ve tarihi gösterir:
```sh
$ date
```
içinde bulunan ayın takvimini gösterir:
```sh
$ cal
```
sistemin açık kalma süresini gösterir:
```sh
$ uptime
```
sistemle ilgili özet bilgileri verir:
```sh
$ w
```
giriş yapan kullanıcıyı gösterir:
```sh
$ whoami
```
kullanıcı hakkında bilgi verir:
```sh
$ finger kullanıcı
```
çekirdek bilgisini gösterir:
```sh
$ uname -a
```
işlemci bilgisini gösterir:
```sh
$ cat /proc/cpuinfo
```
RAM bilgisini gösterir:
```sh
$ cat /proc/meminfo
```
belirtilen komutun kullanım klavuzu:
```sh
$ man komut
```
disk kullanımını gösterir:
```sh
$ df
```
dizinin kullandığı disk alanını gösterir:
```sh
$ du
```
kullanılan RAM bilgisini gösterir:
```sh
$ free
```
uygulama yolunu gösterir:
```sh
$ whereis uygulama
```
uygulamanın tam yolunu gösterir:
```sh
$ which uygulama
```

### Sıkıştırma İşlemleri
dosyayı içeren bir tar arşivi oluşturur:
```sh
$ tar cf dosya.tar dosya
```
dosya.tar içinde dosyaları açar:
```sh
$ tar xf dosya.tar
```
sıkıştırılmış tar arşivi oluşturur(gzip):
```sh
$ tar cf dosya.tar.gz dosya
```
sıkıştırılmış arşivi açar:
```sh
$ tar xf dosya.tar.gz
```
Sıkıştırılmış tar arşivi oluşturur(bzip2):
```sh
$ tar cf dosya.tar.bz2
```
arşivi açar:
```sh
$ tar xf dosya.tar.bz2
```
dosyayı sıkıştırır ve uzntısını .gz yapar:
```sh
$ gzip dosya
```
sıkıştırılmıs dosyayı açar:
```sh
$ gzip -d dosya.gz
```

### Ağ
Hedefe ping atar ve sonuşları gösterir:
```sh
$ ping hedef
```
belirtilen alan adının kayıt bilgilerini gösterir:
```sh
$ whois domain
```
belirtilen alan adının DNS bilgilerini gösterir:
```sh
$ dig domain
```
PTR kaydını gösterir:
```sh
$ dig -x host
```
dosya indirir:
```sh
$ wget file
```
durdurulmuş indirmeye devam eder:
```sh
$ wget -c file
```

### Yazılım Derleme/Kurma
Kaynaktan paket derleme:
```sh
$ ./configure --prefix=/usr
$ make
$ make install
```
belirtilen paketi kurar:
```sh
$ pisi it paket
```
belirtilen paketi kaldırır:
```sh
$ pisi rm paket
```

### Klavye Kısa Yolları
Komutu durdurur, sona erdirir:
```sh
 Ctrl+C
```
komutu durdurur, devam etmek için fg, arkaplanda devam etmek için bg kullanılır:
```sh
 Ctrl+Z
```
konsol oturumundan çıkış yapar:
```sh
 Ctrl+D
```
mevcut satırdan bir kelime siler:
```sh
 Ctrl+W
```
tüm satırı siler:
```sh
 Ctrl+U
```
Komut geçmişinde arama yapar:
```sh
 Ctrl+R
```
Son verilen komutu tekrarlar:
```sh
 !!
```

