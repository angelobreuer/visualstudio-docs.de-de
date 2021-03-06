---
title: Auswerten eines XPath-Ausdrucks während des Debuggens
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c2e0b6c84fa9447dc38aa7976fa59bb5aa67d5c3
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2020
ms.locfileid: "75592723"
---
# <a name="evaluate-xpath-expressions"></a>Auswerten von XPath-Ausdrücken

Sie können XPath-Ausdrücke auswerten, indem Sie während des Debuggens das Fenster **Schnellüberwachung** verwenden. Der XPath-Ausdruck muss gemäß der W3C-Empfehlung für XPath 1.0 gültig sein. Der aktuelle XSLT-Kontext (d. h. der `self::node()`-Knoten im Fenster **Lokal**) stellt den Auswertungskontext für den XPath-Ausdruck bereit.

Für das Auswerten von XPath-Ausdrücken gilt Folgendes:

- Integrierte XPath-Funktionen werden unterstützt.

- Integrierte XSLT-Funktionen und benutzerdefinierte Funktionen werden nicht unterstützt.

> [!NOTE]
> Das XSLT-Debugging ist nur in der Enterprise-Edition von Visual Studio verfügbar.

## <a name="evaluate-an-xpath-expression"></a>Auswerten eines XPath-Ausdrucks

In der folgenden Prozedur werden die Dateien *below-average.xsl* und *books.xml* aus dem Artikel [Exemplarische Vorgehensweise: Debuggen eines XSLT-Stylesheets](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md#sample-files) verwendet.

1. Fügen Sie einen Haltepunkt am `xsl:if`-Starttag ein.

2. Klicken Sie in der Menüleiste auf **XML** > **XSLT-Debugging starten** aus (oder drücken Sie **ALT**+**F5**), um das Debugging zu starten.

   Der Debugger wird gestartet und am `xsl:if`-Tag unterbrochen.

3. Klicken Sie mit der rechten Maustaste, und wählen Sie die Option **Schnellüberwachung** aus.

   Das Fenster **Schnellüberwachung** wird geöffnet.

4. Geben Sie im Dialogfeld **Schnellüberwachung** in das Feld **Ausdruck** den Ausdruck `./price/text()` ein, und klicken Sie auf **Reevaluate** (Neu auswerten).

   Der Preis des aktuellen Buchknotens wird im Feld **Wert** angezeigt.

   ![Auswerten eines XPath-Ausdrucks im Fenster „Schnellüberwachung“](media/quickwatch-price.png)

5. Ändern Sie den XPath-Ausdruck in `./price/text() < $bookAverage`, und klicken Sie auf **Reevaluate** (Neu auswerten).

   Im Feld **Wert** wird angezeigt, dass der XPath-Ausdruck zu `true` ausgewertet wird.

## <a name="see-also"></a>Siehe auch

- [Debuggen von XSLT](../xml-tools/debugging-xslt.md)
