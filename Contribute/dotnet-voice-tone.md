---
title: A .NET dokumentációjának stílusa – útmutató szerzőknek
description: Útmutatónkban az elvárásainknak megfelelő és nem megfelelő példákból ismerkedhet meg helyes stílussal és hangvétellel.
ms.date: 11/07/2018
ms.openlocfilehash: cf78bb5d476d35b9b168b619e90e8f372103cb93
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609693"
---
# <a name="voice-and-tone-guidelines"></a>A stílusra és a hangvételre vonatkozó irányelvek

Az Ön által írt dokumentumokat IT-üzemeltetők, fejlesztők és még sokan mások olvassák azért, hogy megismerkedjenek a .NET-tel, illetve segítséget kapjanak a napi munkájukhoz. Önnek olyan kiváló dokumentációt kell készítenie, amely közelebb viszi az olvasót a céljához. Útmutatónk segít ebben. Stíluskalauzunk a következő javaslatokat tartalmazza:

A stíluskalauz olvasása közben mindegyikre fog példát találni. Azért írtuk meg ezt az útmutatót az irányelveink alapján, hogy követhető példákkal segítsük Ön a .NET-dokumentáció elkészítésében. Ellenpéldákat is bemutatunk, amelyekből azt ismerheti meg, hogy milyenek az irányelveinket be nem tartva megírt cikkek.

## <a name="use-a-conversational-tone"></a>Használjon társalgási hangvételt

### <a name="appropriate-style"></a>Megfelelő stílus

Azt a célunk, hogy a dokumentációnk társalgási hangvételű legyen. Az oktatóanyagok és a magyarázatok olvasása közben úgy kell éreznie, mintha beszélgetne a szerzővel. Informálisnak, társalgási hangvételűnek és informatívnak kell lennie a cikknek az Ön számára. Az olvasóknak úgy kell érezniük, mintha élőszóban hallanák azt, ahogyan a szerző elmagyarázza nekik a tudnivalókat.

### <a name="inappropriate-style"></a>Nem megfelelő stílus

Nem nehéz észrevenni a különbséget a társalgási stílus és a műszaki témákról szóló tudományosabb értekezésekben alkalmazott stílus között. Ezen anyagok is rendkívül hasznosak, azonban a szerzők dokumentációnkétól jelentősen eltérő stílusban írták meg az e típussal jellemezhető cikkeket. A tudományos folyóiratok olvasásakor az írás hangvétele és stílusa jelentékeny mértékben különbözik az általunk elvárttól. A tudományos cikkek egy nagyon száraz témát ismertetnek nagyon szárazon.  

A fenti első bekezdés megfelel a társalgási stílusra vonatkozó elvárásunknak. A második tudományosabb stílusú. Azonnal érzékelhető a különbség. 

## <a name="write-in-second-person"></a>Írjon második személyben

### <a name="appropriate-style"></a>Megfelelő stílus

Úgy kell megírnia a cikket, mintha közvetlenül az olvasónak beszélne. Gyakran használjon második személyű alakokat (mint én az előbbi két mondatban). A második személy nem jelenti azt, hogy állandóan az „Ön” névmást kell használnia. Közvetlenül az olvasónak írjon. Írjon felszólító mondatokat. Mondja el az olvasónak, hogy mit szeretne megtanítani neki.

### <a name="inappropriate-style"></a>Nem megfelelő stílus

A szerző a harmadik személyű írásmódot is választhatja. Ez esetben a szerzőnek valamilyen névmást vagy főnevet kell keresnie, hogy utalni tudjon az olvasóra. Az olvasót az ilyen harmadik személyű stílus általában kevésbé köti le, az ilyen cikk olvasása nem túlságosan élvezhető.

Az első bekezdés a javasolt stílusunkat követi. A másodikban harmadik személyt használtunk. Kérjük, hogy második személyben írjon. Valószínűleg Ön is olvasmányosabbnak találta az ilyen bekezdést.

## <a name="use-active-voice"></a>Aktív igealakokat használjon

Aktív igealakokkal írja meg a cikket. Az aktív igealakok azt jelentik, hogy a mondat alanya hajtja végre a mondatban foglalt cselekvést (az ige jelentését). Ellentéte a passzív fogalmazásmód. Ebben a mondat úgy van megszerkesztve, hogy a mondat alanyán végzi el valaki vagy valami a cselekvést. Hasonlítsa össze a következő két példát:

>A fordítóprogram végrehajtható formátumúra alakította át a forráskódot.

>A forráskód átalakításra került végrehajtható formátumra a fordítóprogram által.

Az első program aktív igealakokat használ. A második mondat passzívan van megfogalmazva. (Ez a két mondat újabb példával szolgál a kétféle stílusra).

Azért javasoljuk az aktív fogalmazásmódot, mert érthetőbb. A passzív megfogalmazású mondatok értelmezése nehezebb lehet.

## <a name="target-a-fifth-grade-reading-level"></a>Az ötödik osztálynak megfelelő olvasási szintet célozza meg

Ezt az utóbbi irányelvet azért fogalmaztuk meg, mert nem minden olvasónknak angol az anyanyelve. A cikkek nemzetközi olvasóközönségnek szólnak. Vegye figyelembe, hogy nem mindenkinek olyan gazdag az angol szókincse, mint Önnek.

De arról se feledkezzen meg, hogy műszaki szakembereknek ír. Azt bátran feltételezheti, hogy az olvasók tudnak programozni, és ismerik a programozás szakszókincsét. Az objektumorientált programozás, az objektum, a függvény és a metódus ismerős fogalom számukra. Nincs azonban az olvasóközönség minden tagjának egyetemi diplomája informatikából. Ha például az „idempotens” kifejezést használja, azt alighanem definiálnia kell:

>A `Close()` metódus idempotens, vagyis akárhányszor hívja is meg, ugyanaz lesz a hatása, mintha csak egyszer hívta volna meg.

## <a name="avoid-future-tense"></a>Kerülje a jövő időt

A nyelvek egy részében nagyon másképpen használják a jövő időt, mint az angolban. A jövő idő használatával megnehezítheti a dokumentumok megértését. És a jövő idő használata esetén természetesen felmerül a „mikor?” kérdése is. Ha például azt írja, hogy „A PowerShell megismerése előnyére fog válni”, felvetődik az a kézenfekvő kérdés, hogy mikor fog előnyére válni. Mondja inkább egyszerűen azt, hogy a „PowerShell megismerése előnyére válik”.

## <a name="what-is-it---so-what"></a>Mi ez? És mire jó?

Ahányszor csak bevezet egy fogalmat, amely újdonság az olvasónak, először definiálja, és utána magyarázza el, hogy miért hasznos. Fontos, hogy az olvasó tudja, hogy miről van szó, mert csak így értheti meg az előnyeit (vagy akár a hátrányait).
