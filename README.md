# onkanat blog — yazı kaynağı

`onkanat.blogspot.com` yazılarının **kaynağı** bu depodur. Blog artık `.org` / `.net` / `.com`
sitelerinden beslenmiyor; tek kaynak burası.

## Ne var

| Yol | Ne |
|---|---|
| `icerik.json` | Bütün yazılar: `slug · blogger_slug · title · labels · html · url · published` (eskiden yeniye sıralı) |
| `yazilar/<slug>.html` | Aynı gövdenin tek tek okunabilir hâli |
| `img/cad-bridge/` | cad-bridge dizisinin görselleri (5) |
| `img/gezer-kren/` | Gezer köprülü kren hesabı görselleri (10) |

Yayın adresleri (GitHub Pages, `main` dalı kök):

- içerik: `https://onkanat.github.io/blog/icerik.json`
- görsel: `https://onkanat.github.io/blog/img/<klasör>/<dosya>.png`
- tek yazı: `https://onkanat.github.io/blog/yazilar/<slug>.html`

## Hat

1. Yazı gövdesi `icerik.json`'a girer (HTML; Blogger markdown bilmez).
2. Apps Script (`blogger01` projesi) bu dosyayı okur: `aynala()` blogda olmayanı açar,
   `guncelle()` olanı yeniden yazar.
3. Yazının kanoniği kendi Blogger adresidir (`url` alanı).

## Yeni yazı eklemek

1. `yazilar/<slug>.html` + görselleri `img/<klasör>/` altına koy.
2. Aynı kaydı `icerik.json`'a ekle (`published` ile sıralı).
3. Push → Pages (~1 dk) → Apps Script'te `aynala()`.

## Notlar

- Görseller burada tutulur; dış sitelere (`.org` vb.) bağlanılmaz. Üçüncü taraf görseller
  (ör. `magmaweld.com.tr`) olduğu gibi bırakılır.
- `icerik.json` üretimi: `~/MacAir/webmaster/tools/blog_icerik.py` (Blogger feed'inden üretir).
- Bu depo **herkese açıktır** — Apps Script token taşımadan okuyabilsin diye.
