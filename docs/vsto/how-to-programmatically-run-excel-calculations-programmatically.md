---
title: "Vorgehensweise: Ausführen von Excel-Berechnungen programmgesteuert | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, running calculations
- calculations, running in Excel
- Excel [Office development in Visual Studio], running calculations programmatically
- workbooks, running calculations
ms.assetid: 0bf30d93-8620-43ad-bfb8-f45bf3b5461f
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bf839b6148f9bd5ad9c3953be4cb62cc0c95b7dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-run-excel-calculations"></a>Vorgehensweise: Ausführen von Excel-Berechnungen programmgesteuert  
  Sie verwenden ein ähnliches Verfahren zum Ausführen von Berechnungen in einem <xref:Microsoft.Office.Tools.Excel.NamedRange> Steuerelement oder ein systemeigenes Excel-Range-Objekt.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="running-calculations-in-a-namedrange-control"></a>Ausführen von Berechnungen in einem NamedRange-Steuerelement  
 Das folgende Beispiel erstellt eine <xref:Microsoft.Office.Tools.Excel.NamedRange> Zelle A1 und berechnet dann die Zelle. Dieser Code muss in einer Sheet-Klasse platziert werden und nicht in der `ThisWorkbook` -Klasse.  
  
#### <a name="to-run-calculations-in-a-namedrange-control"></a>Zum Ausführen von Berechnungen in einem NamedRange-Steuerelement  
  
1.  Erstellen Sie den benannten Bereich.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#75)]
     [!code-vb[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#75)]  
  
2.  Rufen Sie die <xref:Microsoft.Office.Tools.Excel.NamedRange.Calculate%2A> Methode des angegebenen Bereichs.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#76)]
     [!code-vb[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#76)]  
  
## <a name="running-calculations-in-a-native-excel-range"></a>Ausführen von Berechnungen in einem systemeigenen Excel-Bereich  
  
#### <a name="to-run-calculations-in-a-native-excel-range"></a>Zum Ausführen von Berechnungen in einem systemeigenen Excel-Bereich  
  
1.  Erstellen Sie den benannten Bereich.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#30)]  
  
2.  Rufen Sie die <xref:Microsoft.Office.Interop.Excel.Range.Calculate%2A> Methode des angegebenen Bereichs.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#31)]  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Bereichen](../vsto/working-with-ranges.md)   
 [NamedRange-Steuerelement](../vsto/namedrange-control.md)   
 [Optionale Parameter in Office-Projektmappen](../vsto/optional-parameters-in-office-solutions.md)  
  
  