# Linux'ta En Sık Kullanılan 100 Komut ve Örnekleri

## Dosya Sistemi Komutları

1. ls - Dizin içeriğini listeler
```bash
ls -la # Gizli dosyalar dahil tüm dosyaları detaylı gösterir
ls -lh # Dosya boyutlarını okunabilir formatta gösterir
```

2. cd - Dizin değiştirir
```bash
cd /home/kullanici # Belirtilen dizine git
cd .. # Üst dizine git
cd ~ # Ana dizine git
```

3. pwd - Mevcut çalışma dizinini gösterir
```bash
pwd # /home/kullanici/belgeler
```

4. mkdir - Yeni dizin oluşturur
```bash
mkdir yeni_klasor
mkdir -p dizin1/dizin2/dizin3 # İç içe dizinler oluşturur
```

5. rm - Dosya veya dizin siler
```bash
rm dosya.txt # Dosya siler
rm -r klasor # Dizini ve içeriğini siler
rm -f dosya # Zorla siler
```

6. cp - Dosya veya dizin kopyalar
```bash
cp kaynak.txt hedef.txt
cp -r kaynak_klasor hedef_klasor
```

7. mv - Dosya/dizin taşır veya yeniden adlandırır
```bash
mv eski.txt yeni.txt
mv dosya /hedef/dizin/
```

8. touch - Boş dosya oluşturur veya zaman damgasını günceller
```bash
touch yeni_dosya.txt
touch -t 202401011200 dosya.txt # Belirli tarih/saat ayarlar
```

## Metin İşleme

9. cat - Dosya içeriğini görüntüler
```bash
cat dosya.txt
cat dosya1.txt dosya2.txt > birlesik.txt
```

10. less - Dosya içeriğini sayfalayarak görüntüler
```bash
less buyuk_dosya.txt
```

11. head - Dosyanın başından belirli sayıda satır gösterir
```bash
head -n 5 dosya.txt # İlk 5 satırı gösterir
```

12. tail - Dosyanın sonundan belirli sayıda satır gösterir
```bash
tail -f log.txt # Dosyayı canlı takip eder
tail -n 10 dosya.txt # Son 10 satırı gösterir
```

13. grep - Metin arama
```bash
grep "aranan" dosya.txt
grep -r "kelime" /dizin # Alt dizinlerde arama yapar
```

14. sed - Akış düzenleyici
```bash
sed 's/eski/yeni/g' dosya.txt
sed -i 's/degisecek/yeni/g' dosya.txt # Dosyayı günceller
```

## Sistem Bilgisi

15. top - Sistem kaynak kullanımını gösterir
```bash
top
top -u kullanici # Belirli kullanıcının işlemlerini gösterir
```

16. htop - Gelişmiş sistem monitörü
```bash
htop
```

17. ps - Çalışan işlemleri listeler
```bash
ps aux
ps -ef | grep firefox
```

18. df - Disk kullanımını gösterir
```bash
df -h # İnsan okunabilir format
```

19. du - Dizin boyutunu gösterir
```bash
du -sh * # Her dizinin boyutunu gösterir
du -h --max-depth=1
```

20. free - RAM kullanımını gösterir
```bash
free -h
free -m # Megabyte cinsinden
```

## Ağ Komutları

21. ping - Ağ bağlantısını test eder
```bash
ping google.com
ping -c 4 192.168.1.1
```

22. netstat - Ağ bağlantılarını gösterir
```bash
netstat -tulpn
netstat -an
```

23. ssh - Uzak sunucuya bağlanır
```bash
ssh kullanici@sunucu
ssh -p 2222 kullanici@sunucu
```

24. scp - Güvenli dosya transferi
```bash
scp dosya.txt kullanici@sunucu:/hedef/
scp -r klasor kullanici@sunucu:/hedef/
```

25. wget - Dosya indirir
```bash
wget https://ornek.com/dosya.zip
wget -c https://ornek.com/dosya.zip # Yarım kalan indirmeye devam eder
```

## Paket Yönetimi (Debian/Ubuntu)

26. apt update - Paket listesini günceller
```bash
sudo apt update
```

27. apt upgrade - Sistemdeki paketleri günceller
```bash
sudo apt upgrade
```

28. apt install - Paket kurar
```bash
sudo apt install paket_adi
```

29. apt remove - Paket kaldırır
```bash
sudo apt remove paket_adi
```

## Kullanıcı ve İzin Yönetimi

30. chmod - Dosya izinlerini değiştirir
```bash
chmod 755 dosya
chmod +x script.sh
```

31. chown - Dosya sahipliğini değiştirir
```bash
chown kullanici:grup dosya
chown -R kullanici dizin
```

32. sudo - Yönetici yetkisiyle komut çalıştırır
```bash
sudo komut
sudo -i # Root kabuğuna geçer
```

33. useradd - Yeni kullanıcı oluşturur
```bash
sudo useradd -m kullanici
sudo useradd -m -s /bin/bash kullanici
```

## Arşivleme ve Sıkıştırma

34. tar - Arşivleme yapar
```bash
tar -czf arsiv.tar.gz dizin/
tar -xzf arsiv.tar.gz
```

35. zip/unzip - ZIP arşivi oluşturur/açar
```bash
zip -r arsiv.zip dizin/
unzip arsiv.zip
```

## Süreç Yönetimi

36. kill - İşlem sonlandırır
```bash
kill PID
kill -9 PID # Zorla sonlandırır
```

37. killall - İsme göre işlem sonlandırır
```bash
killall firefox
killall -9 firefox
```

38. nohup - Arka planda çalıştırır
```bash
nohup komut &
```

## Sistem Servisleri

39. systemctl - Sistem servislerini yönetir
```bash
systemctl start servis
systemctl status servis
```

40. journalctl - Sistem günlüklerini görüntüler
```bash
journalctl -u servis
journalctl -f # Canlı takip
```

## Dosya İçerik İşleme

41. find - Dosya arama
```bash
find /dizin -name "*.txt"
find . -type f -mtime +30 # 30 günden eski dosyalar
```

42. sort - Metni sıralar
```bash
sort dosya.txt
sort -n sayilar.txt # Sayısal sıralama
```

43. wc - Kelime, satır, karakter sayar
```bash
wc -l dosya.txt # Satır sayısı
wc -w dosya.txt # Kelime sayısı
```

44. diff - Dosya farklarını gösterir
```bash
diff dosya1.txt dosya2.txt
diff -u dosya1.txt dosya2.txt
```

## Ağ Güvenliği

45. iptables - Güvenlik duvarı yönetimi
```bash
sudo iptables -L
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
```

46. ufw - Basitleştirilmiş güvenlik duvarı
```bash
sudo ufw enable
sudo ufw allow 22
```

## Disk Yönetimi

47. fdisk - Disk bölümleme
```bash
sudo fdisk -l
sudo fdisk /dev/sda
```

48. mount - Disk bağlama
```bash
mount /dev/sdb1 /mnt/disk
mount -a # fstab'daki tüm diskleri bağlar
```

## Performans İzleme

49. vmstat - Sanal bellek istatistikleri
```bash
vmstat 1
vmstat -s
```

50. iostat - I/O istatistikleri
```bash
iostat
iostat -x 1
```

## Ağ Teşhis

51. traceroute - Ağ yolunu gösterir
```bash
traceroute google.com
```

52. nslookup - DNS sorguları
```bash
nslookup domain.com
nslookup -type=mx domain.com
```

53. curl - HTTP istekleri
```bash
curl https://api.ornek.com
curl -O https://ornek.com/dosya.zip
```

## Metin Düzenleme

54. awk - Metin işleme aracı
```bash
awk '{print $1}' dosya.txt
awk -F: '{print $1}' /etc/passwd
```

55. cut - Sütun ayırma
```bash
cut -d: -f1 /etc/passwd
cut -c1-10 dosya.txt
```

56. tr - Karakter değiştirme/silme
```bash
echo "Merhaba" | tr 'a' 'e'
cat dosya.txt | tr -d ' '
```

## Disk Temizliği

57. ncdu - Disk kullanım analizi
```bash
ncdu /
ncdu /home
```

58. dd - Düşük seviye disk işlemleri
```bash
dd if=/dev/zero of=test.img bs=1M count=100
dd if=/dev/sda of=disk.img
```

## Sistem Bilgisi

59. uname - Sistem bilgisi
```bash
uname -a
uname -r # Kernel sürümü
```

60. lsb_release - Dağıtım bilgisi
```bash
lsb_release -a
```

## Zamanlanmış Görevler

61. crontab - Zamanlanmış görev yönetimi
```bash
crontab -e
crontab -l
```

62. at - Tek seferlik zamanlanmış görev
```bash
at now + 1 hour
at 23:00
```

## Bellek Yönetimi

63. sync - Disk önbelleğini temizler
```bash
sync
```

64. swapon/swapoff - Takas alanı yönetimi
```bash
swapon -s
sudo swapon /swapfile
```

## Donanım Bilgisi

65. lspci - PCI aygıtlarını listeler
```bash
lspci
lspci -v
```

66. lsusb - USB aygıtlarını listeler
```bash
lsusb
lsusb -v
```

## Kullanıcı İşlemleri

67. who - Oturum açmış kullanıcıları gösterir
```bash
who
who -a
```

68. w - Aktif kullanıcıları ve yükü gösterir
```bash
w
w kullanici
```

## Dosya Sistemi Kontrol

69. fsck - Dosya sistemi kontrolü
```bash
sudo fsck /dev/sda1
fsck -f /dev/sda1
```

70. e2fsck - Ext dosya sistemi kontrolü
```bash
sudo e2fsck -f /dev/sda1
```

## Ağ Yapılandırma

71. ifconfig/ip - Ağ arayüzü yapılandırma
```bash
ifconfig
ip addr show
```

72. route - Yönlendirme tablosu
```bash
route -n
ip route show
```

## Güvenlik

73. passwd - Parola değiştirme
```bash
passwd
passwd kullanici
```

74. chage - Parola politikası
```bash
chage -l kullanici
chage -M 90 kullanici
```

## Dosya Arama ve İndeksleme

75. locate - Dosya arama (veritabanı üzerinden)
```bash
locate dosya.txt
updatedb # Veritabanını günceller
```

76. whereis - Program dosyalarını bulur
```bash
whereis python
whereis gcc
```

## Sistem Kayıtları

77. last - Son oturum açma kayıtları
```bash
last
last kullanici
```

78. lastlog - Kullanıcı son giriş kayıtları
```bash
lastlog
lastlog -u kullanici
```

## Dosya Transfer

79. rsync - Dosya senkronizasyonu
```bash
rsync -av kaynak/ hedef/
rsync -avz --progress kaynak/ kullanici@sunucu:hedef/
```

80. ftp - FTP istemcisi
```bash
ftp sunucu
```

## Shell İşlemleri

81. alias - Komut takma adları
```bash
alias ll='ls -la'
alias update='sudo apt update && sudo apt upgrade'
```

82. history - Komut geçmişi
```bash
history
history | grep wget
```

## Sistem Yedekleme

83. dd - Disk kopyalama
```bash
dd if=/dev/sda of=/dev/sdb bs=4M
dd if=/dev/sda1 of=partition.img
```

84. dump - Dosya sistemi yedekleme
```bash
dump -0uf /backup/backup.dump /home
```

## Süreç İzleme

85. strace - Sistem çağrılarını izler
```bash
strace ls
strace -p PID
```

86. ltrace - Kütüphane çağrılarını izler
```bash
ltrace program
ltrace -p PID
```

## Ağ İzleme

87. tcpdump - Ağ trafiğini yakalar
```bash
tcpdump -i eth0
tcpdump -i any 'port 80'
```

88. nmap - Ağ tarama
```bash
nmap localhost
nmap -p 1-100 192.168.1.1
```

## Disk Performansı

89. hdparm - Disk parametreleri
```bash
sudo hdparm -tT /dev/sda
sudo hdparm -i /dev/sda
```

90. badblocks - Disk hata kontrolü
```bash
sudo badblocks -v /dev/sda
```

##
