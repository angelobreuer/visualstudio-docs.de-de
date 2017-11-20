---
title: 'How to: Protect Parts of Documents by Using Content Controls | Microsoft Docs'
ms.custom: 
ms.date: 02/02/2017
ms.prod: visual-studio-dev14
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- partial document protection [Office development in Visual Studio]
- content controls [Office development in Visual Studio], protecting documents
- Word [Office development in Visual Studio], partial document protection
- document protection [Office development in Visual Studio]
- Word [Office development in Visual Studio], restricted permissions
- GroupContentControl
ms.assetid: 50d7286a-7746-446f-8eef-06ceeadc94d0
caps.latest.revision: 28
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: e12f7b04a28ddfe5bd8a312d08a82e290bb0a9ce
ms.contentlocale: de-de
ms.lasthandoff: 08/30/2017

---
# <a name="how-to-protect-parts-of-documents-by-using-content-controls"></a>How to: Protect Parts of Documents by Using Content Controls
  When you protect part of a document, you prevent users from changing or deleting the content in that part of the document. There are several ways you can protect parts of a Microsoft Office Word document by using content controls:  
  
-   You can protect a content control.  
  
-   You can protect a part of a document that is not in a content control.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
##  <a name="EditDeleteControl"></a> Protecting a Content Control  
 You can prevent users from editing or deleting a content control by setting properties of the control in a document-level project at design time or at run time.  
  
 You can also protect content controls that you add to a document at run time by using a VSTO Add-in project. For more information, see [How to: Add Content Controls to Word Documents](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
#### <a name="to-protect-a-content-control-at-design-time"></a>To protect a content control at design time  
  
1.  In the document that is hosted in the [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, select the content control that you want to protect.  
  
2.  In the **Properties** window, set one or both of the following properties:  
  
    -   To prevent users from editing the control, set **LockContents** to **True**.  
  
    -   To prevent users from deleting the control, set **LockContentControl** to **True**.  
  
3.  Click **OK**.  
  
#### <a name="to-protect-a-content-control-at-run-time"></a>To protect a content control at run time  
  
1.  Set the `LockContents` property of the content control to **true** to prevent users from editing the control, and set the `LockContentControl` property to **true** to prevent users from deleting the control.  
  
     The following code example demonstrates using the <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> and <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> properties of two different <xref:Microsoft.Office.Tools.Word.RichTextContentControl> objects in a document-level project. To run this code, add the code to the `ThisDocument` class in your project, and call the `AddProtectedContentControls` method from the `ThisDocument_Startup` event handler.  
  
     [!code-csharp[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#2)]  [!code-vb[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#2)]  
  
     The following code example demonstrates using the <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> and <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> properties of two different <xref:Microsoft.Office.Tools.Word.RichTextContentControl> objects in a VSTO Add-in project. To run this code, add the code to the `ThisAddIn` class in your project, and call the `AddProtectedContentControls` method from the `ThisAddIn_Startup` event handler.  
  
     [!code-vb[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#14)]  [!code-csharp[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#14)]  
  
## <a name="protecting-a-part-of-a-document-that-is-not-in-a-content-control"></a>Protecting a Part of a Document That Is Not in a Content Control  
 You can prevent users from changing an area of a document by putting the area in a <xref:Microsoft.Office.Tools.Word.GroupContentControl>. This is useful in the following scenarios:  
  
-   You want to protect an area that does not contain content controls.  
  
-   You want to protect an area that already contains content controls, but the text or other items that you want to protect are not in the content controls.  
  
> [!NOTE]  
>  If you create a <xref:Microsoft.Office.Tools.Word.GroupContentControl> that contains embedded content controls, the embedded content controls are not automatically protected. To prevent users from editing an embedded content control, use the **LockContents** property of the control.  
  
#### <a name="to-protect-an-area-of-a-document-at-design-time"></a>To protect an area of a document at design time  
  
1.  In the document that is hosted in the [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, select the area that you want to protect.  
  
2.  On the Ribbon, click the **Developer** tab.  
  
    > [!NOTE]  
    >  If the **Developer** tab is not visible, you must first show it. For more information, see [How to: Show the Developer Tab on the Ribbon](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
3.  In the **Controls** group, click the **Group** drop-down button, and then click **Group**.  
  
     A <xref:Microsoft.Office.Tools.Word.GroupContentControl> that contains the protected region is automatically generated in the `ThisDocument` class in your project. A border that represents the group control is visible at design time, but there is no visible border at run time.  
  
#### <a name="to-protect-an-area-of-a-document-at-run-time"></a>To protect an area of a document at run time  
  
1.  Programmatically select the area that you want to protect, and then call the <xref:Microsoft.Office.Tools.Word.ControlCollection.AddGroupContentControl%2A> method to create a <xref:Microsoft.Office.Tools.Word.GroupContentControl>.  
  
     The following code example for a document-level project adds text to the first paragraph in the document, selects the first paragraph, and then instantiates a <xref:Microsoft.Office.Tools.Word.GroupContentControl>. To run this code, add the code to the `ThisDocument` class in your project, and call the `ProtectFirstParagraph` method from the `ThisDocument_Startup` event handler.  
  
     [!code-csharp[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#1)]  [!code-vb[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#1)]  
  
     The following code example for a VSTO Add-in project adds text to the first paragraph in the active document, selects the first paragraph, and then instantiates a <xref:Microsoft.Office.Tools.Word.GroupContentControl>. To run this code, add the code to the `ThisAddIn` class in your project, and call the `ProtectFirstParagraph` method from the `ThisAddIn_Startup` event handler.  
  
     [!code-vb[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#15)]  [!code-csharp[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#15)]  
  
## <a name="see-also"></a>See Also  
 [Automating Word by Using Extended Objects](../vsto/automating-word-by-using-extended-objects.md)   
 [Content Controls](../vsto/content-controls.md)   
 [How to: Add Content Controls to Word Documents](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Adding Controls to Office Documents at Run Time](../vsto/adding-controls-to-office-documents-at-run-time.md)  
   