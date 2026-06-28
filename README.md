# Garde Manger — Soğuk Mutfak Rehberi

Escoffier, Larousse Gastronomique ve CIA gibi profesyonel kaynaklara dayalı, Claude API ile çalışan tek dosyalık soğuk mutfak (garde manger) tarif asistanı. Vanilla JS, harici build gerektirmez.

## Kullanım

1. Uygulamayı aç (aşağıdaki canlı link veya `index.html` dosyasını tarayıcıda açarak).
2. Sağ üstteki **🔴 API Key** butonuna tıkla ve kendi Anthropic API anahtarını gir.
   Anahtarını [console.anthropic.com](https://console.anthropic.com/settings/keys) adresinden alabilirsin.
3. Bir tarif ara (ör. "Somon Gravlax"). Sonuçları kaydedebilir veya PDF/HTML olarak dışa aktarabilirsin.

## Güvenlik notu

API anahtarın **yalnızca senin tarayıcında** (`localStorage`) saklanır; hiçbir sunucuya gönderilmez ve repoya yazılmaz. Tarayıcıdan doğrudan Anthropic API'sine istek atılır.

## Teknik

- Tek dosya: `index.html` (HTML + CSS + JS)
- Bağımlılık: çalışma anında Anthropic Messages API
