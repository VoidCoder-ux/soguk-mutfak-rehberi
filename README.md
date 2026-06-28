# Garde Manger — Soğuk Mutfak Rehberi

Escoffier, Larousse Gastronomique ve CIA gibi profesyonel kaynaklara dayalı, DeepSeek API ile çalışan tek dosyalık soğuk mutfak (garde manger) tarif asistanı. Vanilla JS, harici build gerektirmez.

## Kullanım

1. Uygulamayı aç (aşağıdaki canlı link veya `index.html` dosyasını tarayıcıda açarak).
2. Sağ üstteki **🔴 API Key** butonuna tıkla ve kendi DeepSeek API anahtarını gir.
   Anahtarını [platform.deepseek.com](https://platform.deepseek.com/api_keys) adresinden alabilirsin.
3. Model seç:
   - `deepseek-chat` / `deepseek-reasoner` — hızlı taslak (DeepSeek anahtarı gerekir).
   - `gemini (web doğrulamalı)` — Google Search ile arar ve **gerçek, tıklanabilir kaynak linkleri** verir (Gemini anahtarı gerekir; [aistudio.google.com](https://aistudio.google.com/apikey) — ücretsiz tier).
4. Bir tarif ara (ör. "Somon Gravlax"). Sonuçları kaydedebilir, panoya kopyalayabilir veya PDF'e aktarabilirsin.

> Her sağlayıcının kendi API anahtarı vardır; modeli değiştirince sağ üstteki gösterge (🟢/🔴) o sağlayıcının anahtarına göre güncellenir. Anahtarlar yalnızca tarayıcında saklanır.

### Doğrulama hakkında

`gemini (web doğrulamalı)` modu cevabı **gerçek web kaynaklarına** dayandırır ve bunları tıklanabilir link olarak gösterir — kendin kontrol edebilirsin. DeepSeek modlarındaki "kaynak" ve doğrulama bilgisi ise modelin kendi atfıdır (canlı doğrulama değildir). Kritik oran/sıcaklık ve gıda güvenliği için kaynakları teyit etmen önerilir.

## Özellikler

- Tarif kaydetme, kayıtlardan silme, son aramalar (tek tek kaldırma + tümünü temizleme)
- **Porsiyon ölçekleme** — malzeme miktarlarını otomatik yeniden hesaplar (yaklaşık)
- Panoya kopyala ve PDF/HTML dışa aktarma
- İstek **iptali** (uzun süren `deepseek-reasoner` sorguları için) ve zaman aşımı
- Mobil uyumlu: kenar menüsü hamburger (☰) ile açılır

## Güvenlik notu

- API anahtarın **yalnızca senin tarayıcında** (`localStorage`) saklanır; hiçbir sunucuya gönderilmez ve repoya yazılmaz. Tarayıcıdan doğrudan DeepSeek API'sine istek atılır.
- Model ve kullanıcı çıktısı DOM'a basılmadan önce **HTML-escape** edilir (XSS koruması).
- `localStorage`'daki anahtar, aynı origin'deki herhangi bir script tarafından okunabilir; bu yüzden anahtarını paylaşılan/güvensiz bir cihazda girme.

## Teknik

- Tek dosya: `index.html` (HTML + CSS + JS)
- Bağımlılık: çalışma anında DeepSeek API (OpenAI uyumlu, `https://api.deepseek.com/chat/completions`)
