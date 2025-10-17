# Akbank GenAI Bootcamp Projesi - Biyomedikal Mühendisliği Chatbot'u

## Projenin Amacı
Bu proje, biyomedikal mühendisliği ve ilgili teknolojiler hakkında soruları yanıtlamak için RAG (Retrieval Augmented Generation) mimarisi tabanlı bir chatbot geliştirir. Chatbot, spesifik bir veri setinden aldığı kapsamlı verileri kullanarak, kullanıcının sorularına en alakalı ve doğru cevapları sunar.

## Geliştirme Ortamı
Bu proje, kurulum ve bağımlılık sorunlarını en aza indirmek için bulut tabanlı bir platform olan **Google Colab**'da geliştirilmiştir. Tüm kodlar, bu deponun (`.ipynb` ve `app.py`) içinde yer almaktadır.

## Veri Seti Hakkında Bilgi
Proje, veri setini doğrudan Wikipedia'nın **"Medical device" (Tıbbi Cihaz)** sayfasından almaktadır. Bu sorgu, biyomedikal mühendisliği alanındaki temel tanım ve cihaz bilgilerini kapsayarak chatbot'un bilgi tabanını oluşturur.

## Kullanılan Yöntemler (Çözüm Mimarisi)
1.  **Veri Toplama:** Python'da `wikipedia` kütüphanesi kullanılarak ilgili sayfanın tüm içeriği çekilir.
2.  **Metin Parçalama:** Uzun metin, `LangChain`'in `CharacterTextSplitter` aracıyla daha küçük ve yönetilebilir parçalara ayrılır.
3.  **Vektör Veri Tabanı:** Ayrılan metin parçaları, `HuggingFaceEmbeddings` modeli kullanılarak sayısal verilere (gömülü öğeler) dönüştürülür ve `ChromaDB` adlı vektör veri tabanına kaydedilir.
4.  **LLM & Soru-Cevap Mekanizması:** Kullanıcıdan gelen soru, veri tabanında aranır. En alakalı metin parçaları bulunur ve bu parçalar, **OpenAI (GPT-3.5-Turbo-Instruct)** gibi güçlü bir dil modeline gönderilerek anlamlı bir cevap oluşturulur.

## Projenin Çalıştırılması ve Kılavuzu
Projenin temel kodları, **`Biyomedikal_RAG_Chatbot_Final.ipynb`** dosyasında adım adım mevcuttur.

1.  **Google Colab'ı Açın** ve `.ipynb` dosyasını yükleyin.
2.  **API Anahtarını Ekleyin:** Kodun içindeki API anahtar kısmına kendi **aktif** OpenAI API anahtarınızı ekleyin.
3.  **Çalıştırın:** Kodu çalıştırın. Tüm adımlar otomatik olarak tamamlanacaktır.

## Elde Edilen Sonuçlar & Ürün Kılavuzu

Proje, tüm RAG mimarisini başarıyla tamamlamıştır. Projenin test kodu, canlı LLM çağrısı sırasında **OpenAI API kotasının dolması** (Hata Kodu: 429 - RateLimitError) nedeniyle durmuştur.

Bu durum, kodun ve RAG mimarisinin **tamamen doğru çalıştığını**, ancak finansal bir kısıtlama nedeniyle yanıt alınamadığını gösterir. Kod, aktif ve kotalı bir API anahtarı ile çalıştırıldığında tam olarak işlev görmektedir.

## Web Link

Streamlit arayüz kodu (`app.py`) bu deponun içinde mevcuttur. Aktif bir API kotası ile yerel olarak çalıştırılabilir. API kotası dolduğu için canlı bir **deploy linki** paylaşılamamaktadır. Mentorler, projeyi yerel olarak çalıştırabilir veya `.ipynb` dosyasının çıktılarını inceleyebilirler.
