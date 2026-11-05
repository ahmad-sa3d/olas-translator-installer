# OLAS Translator – Enigma2 plugin installer

**OLAS reads a channel's own subtitles and translates them live on your screen, on the Enigma2 receiver you already
own.** Designed first for Arabic, it translates into English too. When a channel shows subtitles (DVB or teletext),
your language appears over the picture by itself.

🌐 Website: **[olas-it.com](https://olas-it.com)** – features, plans, free trial and contact.

## Requirements

- An Enigma2 receiver (OpenATV, OpenPLi, OpenViX, …) with an ARM (armv7 / aarch64) or MIPS CPU and Python 3.8–3.14.
- An internet connection on the receiver.
- Access to the receiver's command line: **telnet** or **SSH** (e.g. PuTTY on Windows, Terminal on macOS / Linux).

## Install or update

Connect to the receiver with telnet or SSH and run:

```sh
wget -qO- https://olas-it.com/plugin/installer.sh | sh
```

The installer picks the right build for your receiver, keeps your settings and restarts Enigma2 at the end. Run the
same command again later to update to the newest version.

## Activate

Open the plugin from the plugins menu. A new receiver starts on the **free trial** right away; to keep translating
after it, enter your **activation key** in the plugin's settings. Plans and keys: [olas-it.com](https://olas-it.com).

## Repair (reinstall the same version)

```sh
wget -qO- https://olas-it.com/plugin/installer.sh | FORCE=1 sh
```

## Uninstall

```sh
wget -qO- https://olas-it.com/plugin/uninstaller.sh | sh
```

It removes the plugin and everything it wrote, then restarts Enigma2.

## Using the scripts in this repository

`olas-installer.sh` and `olas-uninstaller.sh` do the same as the commands above, but download first and say clearly
when the receiver can't reach olas-it.com:

```sh
wget -qO /tmp/olas-installer.sh https://raw.githubusercontent.com/ahmad-sa3d/olas-translator-installer/main/olas-installer.sh
sh /tmp/olas-installer.sh             # FORCE=1 sh /tmp/olas-installer.sh to repair
```

## Troubleshooting

| Message | What to do |
|---|---|
| *could not download …* or no output at all | The receiver can't reach olas-it.com – check its network settings. |
| *The translator isn't available in your country.* | OLAS isn't offered in your country yet – contact us on the website. |
| *This server isn't accepting new receivers right now* | New sign-ups are paused for now – try again later or contact us. |
| *version … is already installed – nothing to do* | You have the newest version; use **Repair** above to reinstall it. |

Questions or problems: the contact form on [olas-it.com/contact](https://olas-it.com/contact).

---

## بالعربية

**يقرأ OLAS ترجمة القناة الأصلية ويترجمها مباشرة على شاشتك، على جهاز Enigma2 الذي تملكه الآن.** صُمّم أولًا للعربية،
ويترجم أيضًا إلى الإنجليزية. الموقع: **[olas-it.com](https://olas-it.com)**

**التثبيت أو التحديث** – اتصل بالجهاز عبر telnet أو SSH ونفّذ:

```sh
wget -qO- https://olas-it.com/plugin/installer.sh | sh
```

**التفعيل** – افتح الإضافة من قائمة الإضافات؛ يبدأ الجهاز الجديد بالفترة التجريبية المجانية، وبعدها أدخل مفتاح التفعيل
في إعدادات الإضافة.

**الإصلاح (إعادة التثبيت):** `wget -qO- https://olas-it.com/plugin/installer.sh | FORCE=1 sh`

**الإزالة:** `wget -qO- https://olas-it.com/plugin/uninstaller.sh | sh`
