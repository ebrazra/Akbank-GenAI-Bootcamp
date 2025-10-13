# Akbank-GenAI-
# Akbank GenAI Bootcamp Projesi - Biyomedikal Mühendisliği Chatbot'u

## Projenin Amacı
Bu proje, biyomedikal mühendisliği ve ilgili teknolojiler hakkında soruları yanıtlamak için RAG (Retrieval Augmented Generation) mimarisi tabanlı bir chatbot geliştirir. Chatbot, Wikipedia'dan aldığı kapsamlı verileri kullanarak, kullanıcının sorularına en alakalı ve doğru cevapları sunar.

## Geliştirme Ortamı
Bu proje, kurulum ve bağımlılık sorunlarını en aza indirmek için bulut tabanlı bir platform olan **Google Colab**'da geliştirilmiştir. Tüm kodlar, bu notebook dosyasının (`.ipynb`) içinde yer almaktadır.

## Veri Seti Hakkında Bilgi
Proje, veri setini doğrudan Wikipedia'nın **"Biomedical engineering"** sayfasından almaktadır. Bu yöntem, projenin kapsamlı ve güvenilir bir bilgi kaynağına dayanmasını sağlar.

## Kullanılan Yöntemler
1.  **Veri Toplama:** Python'da `wikipedia` kütüphanesi kullanılarak ilgili sayfanın tüm içeriği çekilir.
2.  **Metin Parçalama:** Uzun metin, `LangChain`'in `CharacterTextSplitter` aracıyla daha küçük ve yönetilebilir parçalara ayrılır.
3.  **Vektör Veri Tabanı:** Ayrılan metin parçaları, `HuggingFaceEmbeddings` modeli kullanılarak sayısal verilere (gömülü öğeler) dönüştürülür ve `ChromaDB` adlı vektör veri tabanına kaydedilir.
4.  **Soru-Cevap Mekanizması:** Kullanıcıdan gelen soru, veri tabanında aranır. En alakalı metin parçaları bulunur ve bu parçalar, **OpenAI** (veya Gemini) gibi güçlü bir dil modeline gönderilerek anlamlı bir cevap oluşturulur.

## Projenin Çalıştırılması
Bu projeyi çalıştırmak için aşağıdaki adımları izleyin:

1.  **Google Colab'ı Açın:** Tarayıcınızda [colab.research.google.com](https://colab.research.google.com/) adresine gidin ve yeni bir notebook oluşturun.
2.  **Kodu Yapıştırın:** Bu projenin tüm kodlarını tek bir hücreye yapıştırın.
3.  **API Anahtarını Ekleyin:** Kodun içindeki `openai.api_key = "YOUR_OPENAI_API_KEY"` satırına kendi OpenAI API anahtarınızı ekleyin.
4.  **Çalıştırın:** Kodu çalıştırın. Tüm adımlar otomatik olarak tamamlanacaktır.

## Elde Edilen Sonuçlar
Proje, biyomedikal mühendisliği hakkında yöneltilen sorulara, sağlanan veri setine dayanarak doğru ve anlamlı cevaplar üretebilmektedir. Bu yaklaşım, chatbot'un genel bilgilere değil, spesifik ve güncel verilere dayanmasını sağlar.

## Web Link
(Bu kısım projenin web arayüzü tamamlandığında eklenecektir.)
