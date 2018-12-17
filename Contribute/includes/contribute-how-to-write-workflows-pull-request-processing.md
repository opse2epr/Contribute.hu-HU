## <a name="pull-request-processing"></a>A lekéréses kérelem feldolgozása

Az előző szakaszban megismerhette, hogyan küldhet be javasolt módosításait úgy, hogy azokat egyetlen új lekéréses kérelemben gyűjti össze. Az így elkészült lekéréses kérelem felkerül a céltárház lekéréses kérelmi várólistájára. A lekéréses kérelem használata fontos része a GitHub együttműködési modelljének, amelyben a munkaágban történt változtatásokat kérik le egy másik ágban való összefésüléshez. Az összefésülés a legtöbb esetben a fő tárház alapértelmezés szerinti főágában történik.

### <a name="validation"></a>Ellenőrzés

Mielőtt a lekéréses kérelem tartalma összefésülésre kerülne a főágban, a kérelemnek esetenként egy ellenőrzési folyamaton kell átesnie. Ez a folyamat a javasolt változások hatókörének és a céltárház előírásainak függvényében változhat. A lekéréses kérelem elküldését követően az alábbiakban felsorolt események közül egy vagy több is várható:

- **Összefésülhetőség**: Először egy kiinduló GitHub-összefésülhetőségi teszt lesz végrehajtva, amely ellenőrzi, hogy vannak-e összeütközések a saját ágban javasolt változtatások és a célág között. Ha a lekéréses kérelem azt jelzi, hogy a teszt összeütközést talált, akkor a folytatáshoz először meg kell szüntetnie az adott tartalomban az összeütközést kiváltó okokat.
- **Közreműködői licencszerződés (CLA)**: Ha nem Microsoft-alkalmazottként nyilvános tárházhoz küld be közreműködést, akkor a javasolt változtatás mértékétől függően előfordulhat, hogy amikor először küld be lekéréses kérelmet az adott tárházba, a folytatáshoz ki kell töltenie egy rövid Közreműködői licencszerződést (CLA-t). A CLA feldolgozása után a lekéréses kérelem is feldolgozásra kerül.
- **Címkézés**: A lekéréses kérelem automatikusan olyan címkét kap, amely a kérelem állapotát hivatott jelezni az ellenőrzési folyamat során. Az új kérelmek például automatikusan a "do-not-merge" („nem összefésülendő”) címkét kaphatják, ami azt jelzi, hogy a kérelem még nem esett át az ellenőrzési, a felülvizsgálati és az egyesítési jóváhagyási fázisokon.
- **Ellenőrzés és felépítés**: A javasolt változtatások megfelelőségét automatikus ellenőrzések vizsgálják meg. Ha a megfelelőségi ellenőrzés figyelmeztetéssel vagy hibával tér vissza, akkor a lekéréses kérelemben módosítania kell egy vagy több fájlt, mielőtt az összefésülés megtörténhetne. Az megfelelőségi ellenőrzés eredménye megjegyzésként a lekéréses kérelemhez lesz csatolva, és e-mailben is megkaphatja azt.
- **Előkészítés**: A változtatások által érintett cikkek oldalai az ellenőrzést és összeállítást követően egy átmeneti környezetben automatikusan megjelennek felülvizsgálatra. Az előnézeti URL-címek megtalálhatók a lekéréses kérelemhez csatolt megjegyzések között.
- **Automatikus összefésülés**: Ha a lekéréses kérelem sikeresen átment az érvényesítési ellenőrzésen, és bizonyos más feltételeknek is megfelel, akkor az automatikusan is összefésülhető. Ilyen esetben Önnek nincs további teendője.

### <a name="review-and-sign-off"></a>Áttekintés és jóváhagyás

Ha a lekéréses kérelem feldolgozása befejeződött, tekintse át az eredményeket (a kérelemhez csatolt megjegyzések, az előnézeti URL-címek stb.), és ellenőrizze, nincs-e szükség a kérelem fájljainak további módosítására, mielőtt összefésülésre jóváhagyná a kérelmet. Ha a lekéréses kérelmet kérelembíráló is ellenőrizte, akkor előfordulhat, hogy megjegyzésként visszajelzést is küld, amennyiben még függőben lévő problémák vagy kérdések vannak, amelyeket az összefésülés előtt meg kell oldani.

[!INCLUDE[contribute-how-to-pull-requests-apex-automation.md](contribute-how-to-pull-requests-apex-automation.md)]

Ha a lekéréses kérelem problémamentes, és a jóváhagyás is megtörtént, akkor a javasolt változtatások össze lesznek fésülve a szülőágban, a lekéréses kérelem pedig lezárul.

### <a name="publishing"></a>Közzététel

Ahhoz, hogy a javasolt változtatások megjelenjenek a legközelebbi tervezett közzétételkor, a lekéréses kérelmet egy kérelembírálónak kell összefésülnie. A lekéréses kérelmeket általában a beérkezés sorrendjében bírálják el és fésülik össze. Ha fontos, hogy a lekéréses kérelmet egy adott tervezett kiadásnál fésüljék össze, akkor minél hamarabb el kell kezdenie az együttműködést a lekéréses kérelem bírálójával, hogy az összefésülés a kívánt időben megtörténjen.

A Docs.Microsoft.Com kiadási folyamata csak azt követően dolgozza fel a hozzájárulását, amikor azt már elfogadták és összefésülték. A kiadás ideje más-más lehet az illető tárházon dolgozó csapat függvényében is. Az alábbi útvonalakon közzétett cikkek általában hétfőtől péntekig kb. 10:30 és 15:30 között jelennek meg (Csendes-óceáni idő):

- https://docs.microsoft.com/azure/
- https://docs.microsoft.com/aspnet/
- https://docs.microsoft.com/dotnet/
- https://docs.microsoft.com/enterprise-mobility-security

A cikk online megjelenése a közzétételt követően akár 45 percet is igénybe vehet. A cikk közzététele után a változtatásokat a megfelelő URL-címen lehet ellenőrizni: `https://docs.microsoft.com/<path-to-your-article-without-the-md-extension>`.
