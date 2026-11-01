# some-pc-manager (derlenmiş sürümler)

Bu depo **derleme çıktılarını** içerir. Kaynak kod ayrı depoda: `some PC manager-repo`
(derleme: `./scripts/build.sh <çıktı-dizini>`). Hangi kaynak commit'inden üretildiği `BUILD_INFO` içinde yazar.

| Dosya | Ne işe yarar |
|---|---|
| `some-pc-manager-0.1.0-1-any.pkg.tar.zst` | Arch/CachyOS paketi (önerilen; polkit politikası, masaüstü girdisi ve simge dahil) |
| `some_pc_manager-0.1.0-py3-none-any.whl` | Python wheel |
| `some_pc_manager-0.1.0.tar.gz` | Kaynak dağıtımı (sdist) |
| `SHA256SUMS` | Doğrulama için özetler |
| `BUILD_INFO` | Sürüm, kaynak commit ve derleme tarihi |

## Kurulum (Arch / CachyOS)
```bash
sha256sum -c SHA256SUMS
sudo pacman -U some-pc-manager-0.1.0-1-any.pkg.tar.zst
some-pc-manager
```
Bağımlılıklar: `python`, `python-gobject`, `python-cairo`, `gtk4`, `libadwaita`, `polkit`.
İsteğe bağlı: `pacman-contrib` (paket önbelleği temizliği), `clamav` (virüs taraması).

Kaldırmak için: `sudo pacman -R some-pc-manager`

## Not
Wheel yalnızca Python kodunu ve verisini kurar; yetkili işlemler (paket önbelleği, journal, RAM önbelleği) için
root'a ait yardımcı betiği ve polkit politikasını kuran **pacman paketini** tercih et.
