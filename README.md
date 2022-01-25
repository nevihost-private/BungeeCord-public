BungeeCord
==========
Minecraft sunucularını bağlamak için tasarlanmış Layer 7 proxy.
--------------------------------------------------

BungeeCord, esas olarak oyuncuları birden fazla Minecraft sunucusu arasında ışınlamak için tasarlanmış gelişmiş bir proxy ve API'dir.

Bilgi
-----------
BungeeCord, [SpigotMC](https://www.spigotmc.org/) tarafından sağlanır ve birçok yararlı bilgi ve bağlantı içeren kendi [tartışma başlığına](https://www.spigotmc.org/go/bungeecord) sahiptir.

# Editleme && Kurulum
Öncelikle BungeeCord'a bağlamak istediğiniz sunucuların `spigot.yml` dosyasını açıyoruz ve `bungeecord: false` yazısını `bungeecord: true` olarak değiştiriyoruz.

#### Düzenlemeden önceki hali;
```yml
settings:
  bungeecord: false
 ``` 
#### Olması gereken;
```yml
settings:
  bungeecord: true
 ``` 

<br />Bağlamak istediğimiz sunucunun ayarlamasını yaptıktan sonra, `bungeecord/config.yml` dosyasını açıyoruz ve;

```yml
# Config Dosyası
servers:
  FakeLobby: # oyun içerisinde bağlantı komutunun ihityaç olduğu için kısa öz ve tek bir değer giriniz (/server FakeLobby)
    motd: '&1FakeLobby'
    address: 0.0.0.0:25000
    restricted: false
  Oyun: #(/server oyun)
    motd: '&1Oyun'
    address: 0.0.0.0:25002
    restricted: false
```
- `Adress: kısmındaki 0.0.0.0` yerine, `bağlamak istediğiniz sunucunun ip adresini`; port kısımına ise `bağlamak istediğiniz sunucunun port` değerini yazıyoruz

Bungeecordun başlama sunucusunu ayarlamak için;
- `force_default_server` ayarını `true` olarak ayarlıyoruz
- Öncelikli sunucuyu belirlemek için `servers` kısmına eklediğimiz sunuculardan birini yazıyoruz
```yml
priorities:
  - FakeLobby
```

# Güvenlik uyarısı

Minecraft sunucularınızın BungeeCord'un çalışması için kimlik doğrulaması olmadan (online-mode=false) çalışması gerektiğinden, bu yeni bir güvenlik riski oluşturur. Kullanıcılar, kullanmak istedikleri herhangi bir kullanıcı adı altında doğrudan sunucularınıza bağlanabilir. "IP iletmeyi kullanmak istiyorsanız, lütfen BungeeCord yapılandırmanızda da etkinleştirin!" Spigot sunucularınızı korumaz.

Bununla mücadele etmek için, örneğin bir güvenlik duvarı ile bu sunuculara erişimi kısıtlamanız gerekir (lütfen [güvenlik duvarı kılavuzuna](https://www.spigotmc.org/wiki/firewall-guide/) bakın).

Kaynak
------
Kaynak kodu şu anda [GitHub](https://www.spigotmc.org/go/bungeecord-git) üzerinde mevcuttur.

Yazar
--------
- [Plugin sahibi](https://github.com/SpigotMC/BungeeCord)
- [Plugin owner](https://github.com/SpigotMC/BungeeCord)
