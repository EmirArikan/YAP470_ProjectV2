# YAP470_Project
## Beyin MRI Görüntülerinden Tümör Derecesi Sınıflandırma

Bu projede, beyin tümörü olan hastalara ait MRI görüntülerinden yola çıkarak, tümörün hangi seviyede (derecede) olduğunu sınıflandırmak amaçlanmaktadır.

### Veri Seti

Projemizde kullanılan veri setinde, beyin tümörü olan hastalara ait MRI görüntüleri ve bu görüntülere karşılık gelen tümör derecelerini içeren bir `.csv` dosyası bulunmaktadır.

-[Brain MRI Segmentation](https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation)  
-[Brain Tumor Segmentation](https://www.kaggle.com/datasets/nikhilroxtomar/brain-tumor-segmentation)

Deep Learning modellerinden biri olan CNN kullanılacağı için, modele yeteri kadar veri sağlanması için "data augmentation" yöntemi kullanılıp veri sayısı arttırılmıştır. 

<img width="1575" height="409" alt="aug" src="https://github.com/user-attachments/assets/d2893ede-2be1-4ff8-9a7a-396b73bfc667" />

### Dosyalar ve Kodlar





### Sonuçlar
## CNN Modelinin Karmaşıklığının Sonuca Etkisi
Kullanılacak olan CNN modelinin mimarisi ne çok basit ne de çok karmaşık olmalıdır. Çünkü eğer modelin mimarisi çok basit olursa yeterince öğrenemez ve underfitting (yetersiz öğrenme) durumu ortaya çıkar. Öte yandan, model çok karmaşık olursa bu kez eğitim verilerini ezberleme eğiliminde olur ve overfitting (aşırı öğrenme) gerçekleşir. Bu sebeple, kullanılacak CNN mimarisinin dengeli ve uygun karmaşıklıkta seçilmesi oldukça önemlidir. Yapılan deneylerde elde edilen sonuçlar da bu dengeyi sağlayan mimarilerin daha başarılı olduğunu göstermektedir.

<p align="center">
  <img src="https://github.com/user-attachments/assets/f445f6fe-1a4e-43b4-8b0e-aa29315a6579" alt="image" width="500"/>
</p>

## Epoch Sayısının Sonuca Etkisi
Epoch sayısının düşük olması, modelin verilerden yeterince öğrenememesine neden olabilir. Bu durumda eğitim eksik kalır ve modelin başarımı düşük olur. Ancak epoch sayısının gereğinden fazla artırılması da fayda sağlamaz; çünkü belirli bir noktadan sonra doğruluk artmaz ve eğitim süresi gereksiz yere uzar. Ayrıca bu durum modelin aşırı öğrenmesine (overfitting) yol açabilir. Bu nedenle epoch sayısı belirlenirken doğrulama setindeki başarı dikkatle izlenmelidir.

<p align="center">
  <img src="https://github.com/user-attachments/assets/d90c5cd7-5644-4cdf-9b35-5c5bc93cf9eb" alt="image" width="500"/>
</p>

## Batch Size Değerinin Sonuca Etkisi
Batch size (yani eğitimde kullanılan örneklerin grup büyüklüğü) modelin hem eğitim süresini hem de genel başarımını etkiler. Küçük batch size değerleri daha sık güncelleme yapmayı sağlar, bu da modelin daha kararlı ve genelleştirilebilir öğrenmesine yardımcı olabilir. Ancak çok küçük değerler gürültülü gradyanlar nedeniyle öğrenme sürecini dengesizleştirebilir. Büyük batch size'lar ise daha az güncelleme içerdiğinden daha hızlı eğitim sağlar; fakat bu durumda model daha az genelleştirme yapabilir ve local minima'lara saplanma riski artar.

Yapılan denemelerde, batch size = 16, batch size = 64 ve batch size = 32 olmak üzere üç farklı değer denenmiş ve elde edilen doğruluk değerleri karşılaştırılmıştır. Sonuçlar, en yüksek başarının batch size = 16 ile elde edildiğini göstermektedir. Bu değeri sırasıyla batch size = 64 ve ardından batch size = 32 takip etmiştir. Bu da küçük batch size'ların, özellikle karmaşık olmayan veri setlerinde, daha iyi genelleme ve öğrenme sağlayabileceğini göstermektedir.

<p align="center">
  <img src="https://github.com/user-attachments/assets/413b2fc7-b555-461d-a3a0-d54eae9f8b79" alt="image" width="500"/>
</p>
