Hızlı Kurulum - www.hermesabrasive.net GitHub Pages

1) Hazırlandı
- Repo kökünde `CNAME` eklendi: `www.hermesabrasive.net`.

2) DNS (alan adı kayıt sağlayıcınıza ekleyin)
- `www` için: tip `CNAME` → `muratakin-max.github.io` (ya da GitHub Pages hedefiniz). TTL: default.
- Root (apex) için (opsiyonel): tip `A` kayıtları →
  - 185.199.108.153
  - 185.199.109.153
  - 185.199.110.153
  - 185.199.111.153

Not: Registrar `ALIAS`/`ANAME` destekliyorsa root için onu kullanabilirsiniz. Cloudflare kullanıyorsanız CNAME flattening etkinleştirin.

3) GitHub Pages ayarları
- Repo → Settings → Pages
- Source: siteyi hangi branch/klasörden yayınlıyorsanız onu seçin (`main`/`gh-pages`).
- Custom domain bölümüne `www.hermesabrasive.net` yazıp kaydedin.
- HTTPS etkinleştirin (sertifika birkaç dakika–saat içinde çıkar).

4) Doğrulama / test komutları
```bash
dig +short CNAME www.hermesabrasive.net
dig +short A hermesabrasive.net
curl -I https://www.hermesabrasive.net
```

5) Yönlendirme
- `hermesabrasive.net` → `www.hermesabrasive.net` 301 yönlendirmesi önerilir.

6) Otomasyon
- Bu repoya eklenen GitHub Actions workflow, `gh-pages` dalına deploy eder ve Pages API ile custom domain'i `www.hermesabrasive.net` olarak ayarlar.
