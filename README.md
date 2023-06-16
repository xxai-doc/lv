<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Ieteicams vispirms instalēt nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) un pēc tam `direnv allow` pēc ievadīšanas direktorijā ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) tiks izpildīts automātiski pēc ievadīšanas direktorijā).

Nozīme ir: ķīniešu tulkojums japāņu, korejiešu, angļu valodā, tulkojums angļu valodā visās pārējās valodās. Ja vēlaties atbalstīt tikai ķīniešu un angļu valodu, varat vienkārši ierakstīt `zh: en` .

Nozīme ir: ķīniešu tulkojums japāņu, korejiešu, angļu valodā, tulkojums angļu valodā visās pārējās valodās. Ja vēlaties atbalstīt tikai ķīniešu un angļu valodu, varat vienkārši ierakstīt `zh: en` .

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

### Dokumentu tulkošanas automatizācijas instrukcijas

Skatiet kodu krātuvi [xxai-art/doc](https://github.com/xxai-art/doc)

Ieteicams vispirms instalēt nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) un pēc tam `direnv allow` pēc ievadīšanas direktorijā ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) tiks izpildīts automātiski pēc ievadīšanas direktorijā).

Lai izvairītos no lielas koda bāzes, kas tiek tulkota simtiem valodu, es izveidoju atsevišķu kodu bāzi katrai valodai un izveidoju organizāciju koda bāzes glabāšanai.

Iestatot vides mainīgo `GITHUB_ACCESS_TOKEN` un pēc tam palaižot vietni [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) , automātiski tiks izveidota koda krātuve.

Protams, to var ievietot arī koda bāzē.

Tulkošanas skripta atsauce [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Skripta kods tiek interpretēts šādi:

[bunx](https://bun.sh/docs/cli/bunx) aizstāj npx, kas ir ātrāks. Protams, ja jums nav instalēta bulciņa, tā vietā varat izmantot `npx` .

`bunx mdt zh` atveido `.mdt` zh direktorijā kā `.md` , skatiet tālāk 2 saistītos failus

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` ir tulkošanas pamatkods (ja ir instalēts tikai `nodejs` , bet `bun` un `direnv` nav instalēti, varat arī palaist `npx i18n` , lai tulkotu).

Tas parsēs [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , `i18n.yml` konfigurācija šajā dokumentā ir šāda:

```
en:
zh: ja ko en
```

Nozīme ir: ķīniešu tulkojums japāņu, korejiešu, angļu valodā, tulkojums angļu valodā visās pārējās valodās. Ja vēlaties atbalstīt tikai ķīniešu un angļu valodu, varat vienkārši ierakstīt `zh: en` .

Pēdējais ir [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , kas izvelk saturu starp katras valodas `README.md` galveno nosaukumu un pirmo apakšvirsrakstu, lai ģenerētu ierakstu `README.md` . Kods ir ļoti vienkāršs, to varat apskatīt pats.

Google API tiek izmantots bezmaksas tulkošanai. Ja nevarat piekļūt Google, lūdzu, konfigurējiet un iestatiet starpniekserveri, piemēram:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Tulkošanas skripts ģenerēs tulkotu kešatmiņu `.i18n` direktorijā. Lūdzu, pārbaudiet to ar `git status` un pievienojiet to koda krātuvei, lai izvairītos no atkārtotiem tulkojumiem.

Lūdzu, palaidiet `bunx i18n` katru reizi, kad modificējat tulkojumu, lai atjauninātu kešatmiņu.

Ja oriģinālais teksts un tulkojums tiek mainīti vienlaikus, kešatmiņa tiks sajaukta, tādēļ, ja vēlaties modificēt, varat modificēt tikai vienu un pēc tam palaist `bunx i18n` , lai atjauninātu kešatmiņu.
