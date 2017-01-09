Accessing alexa information through Python

**Python aracılığıyla alexa bilgilerine erişme**

Merhabalar, alexa.com dünya çapında siteleri analiz eder. Bu paket sayesinde bu verilere erişim sağlayacaksınız.

# Kullanımı

İlk olarak, paketi yüklemek ile başlayabiliriz.

    pip install git+url

Alexa paketini, kullanacağınız modüle ekleyin.

    import alexa

Constructor'ı çağırıp, "site url" belirtmeniz yeterli olucaktır. Site url belirtirken
**başında** http/https olmadan direk domain adı yazın. Örneğin : python.tc
 
    alexa = AlexaInfo("python.tc")

Şimdi fonksiyonlarımızı çağıralabiliriz.

**Alexa Genel Bilgiler**

Global Rank, Ülke adı , Ülke Rank gibi bilgilere ulaşabildiğiniz fonksiyondur.

    alexa.alexaInfo()
    
 **Alexa Keywords Bilgileri**
 
 5 adet pöpüler aranan kelimeyi yüzde olarak verir.
 
    print(alexa.alaxaKeywords())

**Alexa Ortak Ziyaretçi Siteleri (Rakip Analizi)**

Ortak ziyaretçi aldığınız 5 adet siteleri listeler

    alexa.upstreamSites()
    
 **Alexa Subdomain Analizi**
 
 Subdomain üzerinden aldığınız ziyaretçileri yüzde olarak bilgisini verir.
 
     alexa.subDomain()


# Örnek Kullanım

 alexa = AlexaInfo("python.tc")

    print("Site Genel Bilgiler;")
    print(alexa.alexaInfo())
    print("\nSite 5 popüler keywords")
    print(alexa.alaxaKeywords())
    print("\nRakip Analizi : 5 Adet Rakip Site - Orta Ziyaretçi Aldığın Site ;")
    print(alexa.upstreamSites())
    print("\nSubDomain Ziyaretçi Analizi")
    print(alexa.subDomain())

**Output :**

    Site Genel Bilgiler;
    {'747,709': 'Global Rank', 'Turkey': 'Name of country', '19,718': 'Rank in Country ', '46.20%': 'Bounce Rate', '4.40': 'Daily Pageviews per Visitor', '4:37': 'Daily Time on Site', '16.80%': 'Search Traffic', '84': 'Backlink'}
    
    Site 5 popüler keywords
    {'50.54%': 'python nedir', '21.89%': 'python türkiye', '3.49%': 'python.tc', '2.09%': 'pyton nedir', '1.90%': 'python wordpress'}
    
    Rakip Analizi : 5 Adet Rakip Site - Orta Ziyaretçi Aldığın Site ;
    {'28.4%': 'google.com.tr', '10.5%': 'wmaraci.com', '7.4%': 'facebook.com'}
    
    SubDomain Ziyaretçi Analizi
    {'98.70%': 'python.tc'}
    
 Bilgileri http://www.alexa.com/siteinfo/python.tc üzerinden karşılaştırabilirsiniz.