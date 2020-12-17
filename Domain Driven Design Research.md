# Architecture Notes

## Domain Driven Design (DDD)

DDD yaklaşımı ile hedeflenen;

- Kolay yönetilebilir (light weight) code-base’e sahip olmak
- Test edilebilirliği (testibility) arttırmak,
- Ölçeklenebilirliği (scalability) arttırmak,
- Esnekliği (felxibility) arttırmak,
- Yüksek erişilebilirliği (highly availability) sağlamak,
- Yeni özellikleri hızlıca release edebilmek (time to market),
- Organizasyonel yapı ile yazılım sistemi arasındaki uyumu sağlamaktı.

DDD’nin stratejik ve taktiksel olmak üzere iki ayrı aşaması vardır. Stratejik DDD’de, iş kurallarına bağlı kalarak sistemin büyük ölçekli modelini tanımlarız. Stratejik DDD, birbirine gevşek bağlı birimleri (bounded context) ve bunlar arasındaki ilişkiyi (context map) tasarlamayı sağlayan disiplinleri belirler. Taktik DDD, implementasyona odaklanır ve yazılımsal implementasyonu oluşturmak için kullanabileceğimiz tasarım desenlerini sağlar. Bu tasarım desenleri entity, aggregate, value object, repository ve domain service gibi kavramları içerir.

Stratejik DDD, birbirine gevşek bağlı birimleri (bounded context) ve bunlar arasındaki ilişkiyi (context map) tasarlamayı sağlayan disiplinleri belirler. Taktik DDD, implementasyona odaklanır ve yazılımsal implementasyonu oluşturmak için kullanabileceğimiz tasarım desenlerini sağlar.

 DDD domaini kendine ait ortak bir dil barındıran, sınırları belirli, bağımsız bileşenlere ayıran bir yaklaşımı belirler. Oluşan bu ortak dile **ubiquitous language**, bağımsız birimlere ise bounded context denir.

 Bounded context için karmaşık domain’in -kendi içinde tutarlı ve mümkün olduğunca bağımsız- daha küçük problem parçacıklarını temsil eden mantıksal sınırlardır
 (logical boundry) diyebiliriz.

 Bounded context’lerin belirlenmesi konusu DDD’nin stratejik tasarım (strategic design) evresini ilgilendiren bir konudur. Stratejik tasarım evresi modelleme işnin yapıldığı süreçtir ve implementasyondan bağımsız bir konudur. DDD mecrasında heuristic ifadesini görebilirsiniz. Bu, hissiyati ya da içgüdüsel anlamına gelir.

Bounded context için karmaşık domain’in -kendi içinde tutarlı ve mümkün olduğunca bağımsız- daha küçük problem parçacıklarını temsil eden mantıksal sınırlardır (logical boundry) diyebiliriz.

Modelleme sürecinin tamamı ile belirsiz bir hal almaması için DDD dünyası bazı önemli konulara işaret eder.

**Domain knowledge (Domain yetkinliği)**: Doğru bir model için önce problemin doğru anlaşılması ve analiz edilmesi gerekir.

**Collobration (İşbirliği)**: Doğru modeli bize hazır halde sunan bir araç olmadığına göre, bu süreç insanlar tarafından yürütülecektir. Etkili bir model için sürecin domain uzmanları (domain expert) tarafından yönlendirilmesi önemlidir. Domain expert kavramı bir rol ya da title değildir. Problemi çok iyi anlamış hatta o problemi yaşayan biri olabilir. Buradan yola çıkarak domain expert olarak en iyi örnek aslında müşterinin ta kendisidir diyebiliriz.

**Iteration (Tekerrür)**: Modellemenin bir keşif serüveni olduğundan bahsettik. Ancak bu keşif mükemmeli aramak değildir. Mükemmel modeli aramaktansa, modelimizdeki eksikleri zaman içerisinde iyileştirmek, ürünün pazara daha hızlı çıkması açısından (time to market) akılcı bir yaklaşımdır.

Sonuç

- DDD, kompleks domainlerde uygulandığında fayda üreten bir pratiktir.
- DDD’nin strategic design evresinde domain knowledge, doğru modelleme için büyük önem taşır.
- Domain knowledge açığa çıkarmak için domain expertler ile birlikte çalışmak gerekir.
- DDD, collobrative bir yöntemdir domain expertler ve teknik ekipler arasında güçlü bir iletişim sağlanmalıdır.

Tutarlılık (Consistency): Tutarlılık, sistemi bir durumdan başka bir duruma geçirirken farklı sistem birleşenlerinin o durumla ilgili referans bütünlüğü sağlamasıdır. Örneğin, bir e-ticaret sisteminde kullanıcı bir ürün için başarılı bir sipariş kaydı oluşturdu ise aynı stoğu başka bir kullanıcıya da satmamak adına, ilgili ürüne ait stok bilgisinin sipariş miktarı kadar azaltılması beklenir.

❗ Mikroservisler gibi dağıtık bilgi işlem ortamlarında, CAP teoremi tutarlılık(consistency), erişilebilirlik(availability) ve bölünebilme toleransını(partition tolerance) aynı anda garanti etmenin imkansız olduğunu ve geliştiricinin kendisi için en önemli üç taneden ikisini seçmek zorunda olduğunu varsayar.

**Consistency(Tutarlılık)**: Dağıtık bir sistemde bir bileşene bir veri yazıldıktan sonra diğer bir bileşene bu verinin değeri sorulduğunda, bu bileşenin aynı değeri sağlayabilmesidir.

**Availability(Erişebilirlik)**: Dağıtık bir sistemde, herhangi bir istemci bir değer sorduğunda o değerin herhangi bir versiyonuna mutlaka erişebilmelidir.

**Partition Tolerance (Bölünebilme Toleransı)**: Sistem birbirinden bağımsız çalışabilen birimlere bölünebilmeli ve bu birimlerden birine herhangi bir sebepten erişilemese bile istemci gecikmeyle de olsa cevap alabilmelidir.

### Kaynak:

 [DDD ve Mikroservis kavramları üzerine bounded context - Medium - TrendyolTech](https://medium.com/trendyol-tech/ddd-ve-mikroservis-kavramlar%C4%B1-%C3%BCzerine-bounded-context-629bcf62ea90)