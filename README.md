<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Daļa vietnes koda ir atvērtā pirmkoda, laipni lūdzam palīdzēt optimizēt tulkojumu.

## priekšgala kods

* [priekšgala kods](https://github.com/xxai-art/web)
* [Valodu pakotnes visai vietnei](https://github.com/xxai-art/web/tree/main/i18n)
* [Valodu pakotnes pieteikšanās moduļiem](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Vietnes daudzvalodu dokumentācija](https://github.com/xxai-doc)

Priekšgala programmēšanas valoda ir [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , kas pievieno dažas funkcijas, pamatojoties uz coffeescript sintakse, skatiet [./coffee_plus.md](./coffee_plus.md) .

## Vietņu un dokumentu internacionalizācija

Balstieties uz šādiem 3 projektiem

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Sufikss ir `.mdt` , lai atsauktos uz ārējiem failiem, varat izmantot sintaksi, kas līdzīga kā `<+ ./coffee_plus/import.js>` , un ģenerēt atzīmes ar sufiksu `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Markdown tulkojumā netiks tulkoti kodi un saites, un tulkotie teikumi tiks saglabāti kešatmiņā. Ja tulkojums ir pārveidots, bet oriģinālais teksts nav pārveidots, tā atkārtota izpilde nepārrakstīs tulkojuma izmaiņas.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Valodu faili `yaml` ģenerētu vietņu tulkošanai.
