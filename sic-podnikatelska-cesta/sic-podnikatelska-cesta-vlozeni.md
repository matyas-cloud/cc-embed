# SIC · Jízda tratí — nastavení bloku Scrollytelling

Platí od 22. 10. 2026 (verze 2, texty čekají na schválení v dokumentu „SIC · Jízda tratí – texty prvku“).

| pole | hodnota |
|---|---|
| URL prvku | `https://matyas-cloud.github.io/cc-embed/sic-podnikatelska-cesta/index.html` |
| Popisek | Podnikatelská cesta od nápadu po rozvoj firmy a programy SIC, které pomohou v každé fázi |
| Délka scroll-dráhy | **800** vh |
| Šířka | **Široký** |

Blok nahrazuje obrázek `sic-podnikatelska-cesta.png`. Mezititulek „Podnikatelská cesta je závod na náročné trati“ nad ním ve speciálu smazat, prvek ho má jako titulek.

## Jak prvek jede

Pixel po pixelu, bez scén a bez držení stránky (`hold` neposílá). Progres od rodiče dohání kriticky tlumenou pružinou (ω 12): zub kolečka se rozloží do plynulého pohybu s náběhem i doběhem. U každé zastávky kamera stojí (8 % dráhy), takže jde text přečíst a kliknout na tlačítko. Světlo na trati nestojí nikdy, u zastávek a v pit-stopu jen zpomalí.

Bez rodiče (samostatně otevřený soubor) si prvek udělá vlastní scroll. Když rodič mlčí 2,5 s, odemkne scroll uvnitř rámu.

## Ověřeno (headless, maketa bloku, rám 1060 × 900)

| test | bez vyhlazení | s pružinou |
|---|---|---|
| 14 zubů kolečka po 100 px | skok až 223 px v jediném snímku, 9 izolovaných skoků | nejvýš 31 px za snímek, 0 izolovaných skoků |
| trackpad, 140 drobných kroků | 39 izolovaných skoků | nejvýš 12 px za snímek, 0 skoků z klidu |

Texty a štítky se vejdou a nepřekrývají v rámech 320 × 568, 375 × 667, 430 × 932, 768 × 1024, 840 × 900, 1060 × 700, 1060 × 900 a 1425 × 900. Konzole čistá.

Ručně zbývá: iOS Safari a Android Chrome dotykem, Windows kolečko bez plynulého scrollu.
