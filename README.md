# Garde Manger — Soğuk Mutfak Rehberi

Escoffier, Larousse Gastronomique ve CIA gibi profesyonel kaynaklara dayalı, DeepSeek API ile çalışan tek dosyalık soğuk mutfak (garde manger) tarif asistanı. Vanilla JS, harici build gerektirmez.

## Kullanım

1. Uygulamayı aç (aşağıdaki canlı link veya `index.html` dosyasını tarayıcıda açarak).
2. Sağ üstteki **🔴 API Key** butonuna tıkla ve kendi DeepSeek API anahtarını gir.
   Anahtarını [platform.deepseek.com](https://platform.deepseek.com/api_keys) adresinden alabilirsin.
3. Model seç (`deepseek-chat` hızlı/uygun, `deepseek-reasoner` daha derin akıl yürütür).
4. Bir tarif ara (ör. "Somon Gravlax"). Sonuçları kaydedebilir veya PDF/HTML olarak dışa aktarabilirsin.

## Güvenlik notu

API anahtarın **yalnızca senin tarayıcında** (`localStorage`) saklanır; hiçbir sunucuya gönderilmez ve repoya yazılmaz. Tarayıcıdan doğrudan DeepSeek API'sine istek atılır.

## Teknik

- Tek dosya: `index.html` (HTML + CSS + JS)
- Bağımlılık: çalışma anında DeepSeek API (OpenAI uyumlu, `https://api.deepseek.com/chat/completions`)
