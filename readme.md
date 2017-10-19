# dbwebb-stream

"One repo to rule them all"

Detta repo består av denna readme med installationsanvisningar samt en json-fil, `dbws.json` med inställningar för [pm2](http://pm2.keymetrics.io/). Tanken är att detta repo skall underlätta driftsättningen av alla tjänster.

## Krav
För att kunna använda startskriptet i detta repo måste [pm2](http://pm2.keymetrics.io/) installeras globalt.

För att kunna köra de separata tjänsterna måste node (version >= 8.0.0) och npm vara installerat.

## Installation
1. Installera pm2 globalt med `npm install -g pm2`
2. Klona detta repo och cd in.
3. Klona repon för de separata tjänsterna:
    * [https://github.com/dbwebb-stream/dbwsirc](https://github.com/dbwebb-stream/dbwsirc)
    * [https://github.com/dbwebb-stream/dbwsgitter](https://github.com/dbwebb-stream/dbwsgitter)
    * [https://github.com/dbwebb-stream/dbwsfunnel](https://github.com/dbwebb-stream/dbwsfunnel)
    * [https://github.com/dbwebb-stream/dbwsfront](https://github.com/dbwebb-stream/dbwsfront)
4. Kör `npm install` i samtliga subrepon.
5. Konfigurera tjänsterna.
6. Kontrollera konfigurationen i startscriptet `dbws.json`.

## Konfigurering
För att tjänsterna ska ha en chans att fungera och fungera ihop är det nödvändigt att konfigurera några tjänster innan start.

1. Ange adresserna till de tjänster som samlingsservern, dbwsfunnel, ska lyssna på.
2. Om gittertjänsten ska startas behöver ett gitter-token anges i dess konfiguration.

pm2 kommer att starta var tjänst i en egen miljö som kan konfigureras i `dbws.json`.

## Starta samtliga tjänster
`$ pm2 start dbws.json`

## Stoppa samtliga tjänster
`$ pm2 kill`

## pm2-kommandon att utforska
```bash
pm2 list                # lista alla processer
pm2 monit               # monitor för översikt
pm2 restart [ID/Name]   # starta om en process
pm2 show [ID/Name]      # Visa info om en process
```

License
------------------

MIT.

 .
..:  @ 2017 Anders Nygren (litemerafrukt@gmail.com)
```
