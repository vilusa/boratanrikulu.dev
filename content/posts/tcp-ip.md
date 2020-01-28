---
date: "2018-04-23T00:00:00Z"
description: tcp/ip'in genel bir tanımını yapar.
tags:
- Network
title: TCP/IP
---

**Kaynaklar**    
[kevsersrca.github.io/blog/security/osi-katmanlari-ve-prokolleri/](https://kevsersrca.github.io/blog//security/osi-katmanlari-ve-prokolleri/)    
[en.wikipedia.org/wiki/TCP/IP](https://en.wikipedia.org/wiki/TCP/IP)  
[networkstatic.net (çizimler)](http://networkstatic.net/wp-content/uploads/2012/04/)

---

## TCP/IP Nedir ?

Transmission Control Protocol/Internet Protocol kısa ifadesi ile TCP/IP; bilgisayarların kendileri arasında nasıl iletişim kurduğunu belirleyen bir kurallar dizisidir. Verilerin nasıl paketleneceğini, gönderilmesini, alınmasını belirler ve pakette bozulma olup olmadığını tespit eder.

TCP/IP adından anlaşılacağı gibi TCP ve IP olmak üzere iki ayrı protokolün birleşimidir.

**IP protokolü** paketlere nereye gideceğini ve oraya nasıl gidileceğini söyler. Hedefe (destination) ulaşmak için arada başka bilgisayarı kullanmak gibi bir yönteme sahiptir.

**TCP protokolü** Internet'e bağlı network'lerde verilerin güvenilir şekilde iletilmesini sağlamaktan sorumludur. TCP, paketlerin hatalarını kontrol eder ve varsa yeniden gönderim taleplerini gönderir.

---

## TCP/IP Layers (Katmanlar)

<p align="center">
<img src="/images/posts/tcp-ip/3.png">
</p>

TCP/IP protokolü ile bir paket yollanacağında; gönderici yukardan aşağı olarak katmanları gezer ve paketi sarmallar (encapsulation). Alıcı paket aldığında ise aşağıdan yukarı doğru katmanları gezerek paketi açar.

TCP/IP protokolünün belli katmanları vardır. Bunlar;

- Application Layer (Uygulama)  
- Transport Layer (Taşıma)  
- Internet Layer  
- Link (Veri Bağlantısı)  
- Physical Layer (Fiziksel)  

<p align="center">
<img width="640" src="/images/posts/tcp-ip/4.png">
</p>

### Application Layer

Uygulama katmanı, kullanıcılara servis sağlayan protokolleri içerir. Örneğin HTTP protokolü üzerinden HTML formatında yazılmış bir sayfanın yollanması gibi.

Uygulama katmanı protokollerine; HTTP, FTP, SMTP, DHCP örnek verilebilir.

Uygulama katmanı protokolleri daha düşük katmanlardaki protokollere kara kutuymuş gibi davranır. Yani sadece I/O önemlidir, nasıl işlendiği değil.

Uygulama katmanı protokollerinin belli başlı port'ları vardır. HTTP 80, DNS 53, Telnet 23 gibi..

### Transport Layer

<p align="center">
<img width="640" src="/images/posts/tcp-ip/2.png">
</p>

Taşıma katmanı, uygulama katmanında gelen verinin taşınmasından sorumludur. Sorumluluğu kapsamında hata kontrolünü, akış kontrolünü, tıkanma kontrolünü gibi şeyler yapabilir. Taşıma katmanı protokolleri uygulama katmanı protokolünün port numarasını içerir.

İki tane taşıma katmanı protokolü vardır; TCP ve UDP

* **TCP** ile kurulan bir bağlantılarda verinin hedefe ulaşıp ulaşmadığı kontrol edilir, **veri bozulması minumum seviyededir**. Bozulan paketler tekrar yıllanır. UDP'e göre daha **yavaştır**.  

* **UDP** ile kurulan bağlantılarda verinin hedefe ulaşıp ulaşmadığı kontrol edilmez, **verinin bütünlüğü kontrol edilmez**. TCP'e göre daha **hızlıdır**.

### Internet Layer

<p align="center">
<img width="640" src="/images/posts/tcp-ip/1.png">
</p>

Internet katmanında, paketler birden fazla network arasında taşınır. Bu işleme aynı zamanda **routing** de denir.  
Taşıma katmanından gelen paket alınır, **Kaynak ve Hedef IP adresleri ile sarılır** (encapsulation). Ardından paket hedef gidebileceği network'ler arasından hedef network'e en yakın olanı seçer. Bu işlem hedef network'e varıncaya dek devam eder.

**IPv4** protokolü ile oluşturulan IP'ler 32 bitten oluşur. Başka bir ifadeyle sekiz bitlik 4 rakamdan oluşur. Bu rakamlar, 0 ila 255 arasında değişir. Bu da 2^32 farklı adres demektir.

**IPv6** protokolü IPv4'lerin yetmemesinden dolayı oluşturulmuştur. IPv4’ten farklı olarak IPv6, 128 bit genişliğindedir. Bu da 2^128 farklı adres demektir.


### Link Layer  

Paket kaynak ve hedef sistemin MAC adresleri ile birleştirilir. Ortaya çıkan frame Fiziksel Katmana yollanır.

### Physical Layer

Fiziksel katman veriler sayısal hallerinde kablolar üzerinden aktarımı yapılır. Verilerin elektronik olarak iletimiyle ilgilenir. Veri paketleriyle, frame’lerle, adreslerle ya da verinin ulaşacağı hedef ile ilgilenmez.  

<p align="center">
<img width="640" src="/images/posts/tcp-ip/7.png">
</p>

Bu adımlardan sonra işlemin tam tersi gerçeleşerek hedef sistem veriyi alır.

<p align="center">
<img width="640" src="/images/posts/tcp-ip/5.png">
</p>
