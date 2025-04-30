# CNN ile Maske Tespiti Projesi

Bu proje, görüntülerde **maske takılıp takılmadığını tespit eden** bir derin öğrenme modelini içermektedir. Proje boyunca TensorFlow ve Keras kullanılarak CNN (Convolutional Neural Network) tabanlı bir sınıflandırma modeli eğitilmiştir.


## Kullanılan Teknolojiler

- Python
- TensorFlow / Keras
- OpenCV (canlı video tahmini için)
- Matplotlib & Seaborn (görselleştirme)
- scikit-learn (performans değerlendirme)

## Veri Kümesi

Veri kümesi `dataset` klasörü altında `train`, `valid`, `test` klasörlerine ayrılmıştır. Her klasörde:
- Görseller
- Görsellere ait etiketleri içeren `.csv` dosyası (örneğin `train.csv`) bulunur.
- Veri setine **https://universe.roboflow.com/joseph-nelson/mask-wearing/dataset/19** adresinden erişebilirsiniz.

## Model Mimarisi

Modelde temel olarak şu katmanlar kullanılmıştır:
- 2 x Conv2D + MaxPooling2D
- Flatten
- Dense (128 birim)
- Dense (Çıkış katmanı, 2 sınıf)

Model eğitimi için `categorical_crossentropy` kullanılmış ve `adam` optimizer'ı tercih edilmiştir.

## Başarı Ölçütleri

Modelin doğruluk ve sınıf bazlı performansı aşağıdaki metriklerle ölçülmüştür:
- Doğruluk (accuracy)
- F1-Score
- Precision / Recall
- Confusion Matrix (Karışıklık Matrisi)

## Canlı Tahmin (Real-time Prediction)

Notebook sonunda OpenCV kullanılarak gerçek zamanlı maske tespiti yapılmıştır. Kamera açıldığında yüzünüzde maske olup olmadığı tespit edilip anlık olarak ekranda gösterilir.


# Nasıl Çalıştırılır?
1. Gerekli kütüphaneleri ve veri setini yükleyin:
- pip install tensorflow opencv-python pandas matplotlib seaborn
- https://universe.roboflow.com/joseph-nelson/mask-wearing/dataset/19
2. Notebook’u çalıştırın veya script dosyasını kullanarak modeli eğitin.
3. Eğitilen modeli (mask_model.h5) kullanarak canlı tespit kısmını çalıştırabilirsiniz.
