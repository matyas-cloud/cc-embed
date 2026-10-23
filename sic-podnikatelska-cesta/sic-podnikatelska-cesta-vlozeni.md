# SIC · Jízda tratí — nastavení bloku Scrollytelling

Platí od 23. 10. 2026 (verze 3, texty čekají na schválení v dokumentu „SIC · Jízda tratí – texty prvku“).

| pole | hodnota |
|---|---|
| URL prvku | `https://matyas-cloud.github.io/cc-embed/sic-podnikatelska-cesta/index.html` |
| Popisek | Podnikatelská cesta od nápadu po rozvoj firmy a programy SIC, které pomohou v každé fázi |
| Délka scroll-dráhy | **800** vh |
| Šířka | **Široký** |

Blok nahrazuje obrázek `sic-podnikatelska-cesta.png`. Mezititulek „Podnikatelská cesta je závod na náročné trati“ nad ním ve speciálu smazat, prvek ho má jako titulek.

## Jak prvek jede

Pixel po pixelu, bez scén a bez držení stránky (`hold` neposílá). Progres od rodiče dohání kriticky tlumenou pružinou (ω 8): zub kolečka se rozloží do plynulého pohybu s náběhem i doběhem. U každé zastávky kamera stojí (zhruba 8 % dráhy), takže jde text přečíst a kliknout na tlačítko. Světlo na trati nestojí nikdy, u zastávek a v pit-stopu jen zpomalí. Cíl leží na posledních 3 % dráhy, takže se blok pustí hned po dojezdu a poslední obrazovka zůstane vidět, jak stránka odjíždí.

Bez rodiče (samostatně otevřený soubor) si prvek udělá vlastní scroll. Když rodič mlčí 2,5 s, odemkne scroll uvnitř rámu.

## Ověřeno (headless, maketa bloku, rám 1060 × 900)

Pohyb kamery v px za 1/60 s, úsek od startu po druhou zastávku.

| test | v2 (ω 12) | v3 (ω 8) |
|---|---|---|
| 14 zubů kolečka po 100 px, nejvyšší rychlost | 18,3 px | 13,1 px |
| totéž, největší změna rychlosti mezi snímky | 10,9 px | 5,0 px |
| trackpad, 140 drobných kroků, nejvyšší rychlost | 3,2 px | 2,2 px |
| izolované skoky | 0 | 0 |

Pozadí kreslí jen předrozmazané sprity, rastr přechodů (dříve vidět jako mřížka) změřený detektorem šachovnice klesl na méně než polovinu a zbytek připadá na hvězdy a hrany trati.

Texty, štítky, cedule pit-stopu a odkazy v cíli se vejdou a nepřekrývají v rámech 320 × 568, 375 × 667, 430 × 932, 768 × 1024, 840 × 900, 1060 × 700, 1060 × 900 a 1425 × 900. Konzole čistá.

Ručně zbývá: iOS Safari a Android Chrome dotykem, Windows kolečko bez plynulého scrollu.
