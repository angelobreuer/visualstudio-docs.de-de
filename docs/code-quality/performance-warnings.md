---
title: Leistungswarnungen
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.performancerules
helpviewer_keywords:
- warnings, performance
- performance warnings
- performance, warnings
- managed code analysis warnings, performance warnings
ms.assetid: e014ac3a-02e6-46d9-942c-3491dd63782f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e578bedf3e6b784321ffb14628ebbe10bc45dc20
ms.sourcegitcommit: 93859158465eab3423a0c0435f06490f0a456a57
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167345"
---
# <a name="performance-warnings"></a>Leistungswarnungen
Leistungs Warnungen unterstützen Hochleistungs Bibliotheken und-Anwendungen.

## <a name="in-this-section"></a>In diesem Abschnitt

| Regel | BESCHREIBUNG |
| - | - |
| [CA1800: Keine unnötigen Umwandlungen](../code-quality/ca1800.md) | Doppelte Umwandlungen beeinträchtigen die Leistung, insbesondere wenn die Umwandlungen in kompakten Iterationsanweisungen ausgeführt werden. |
| [CA1801: Nicht verwendete Parameter überprüfen](../code-quality/ca1801.md) | Eine Methodensignatur enthält einen Parameter, der nicht im Methodentext verwendet wird. |
| [CA1802: Nach Möglichkeit Literale verwenden](../code-quality/ca1802.md) | Ein Feld wird als statisch und schreibgeschützt deklariert (Shared und Read only in [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) und wird mit einem Wert initialisiert, der zur Kompilierzeit berechnet werden kann. Da der Wert, der dem Zielfeld zugewiesen ist, zur Kompilierzeit komprimiert werden kann, ändern Sie die Deklaration in ein Konstantenfeld (Konstanten in [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]), sodass der Wert zur Kompilierzeit anstelle der Laufzeit berechnet wird. |
| [CA1804: Nicht verwendete lokale Variablen entfernen](../code-quality/ca1804.md) | Nicht verwendete lokale Variablen und unnötige Zuweisungen vergrößern die Assembly unnötig und beeinträchtigen die Leistung. |
| [CA1806: Methodenergebnisse nicht ignorieren](../code-quality/ca1806.md) | Ein neues-Objekt wird erstellt, aber nie verwendet, oder eine Methode, die eine neue Zeichenfolge erstellt und zurückgibt, wird aufgerufen, und die neue Zeichenfolge wird nie verwendet, oder eine Component Object Model (com)-oder P/aufrufen-Methode gibt ein HRESULT oder einen Fehlercode zurück, das nie verwendet wird. |
| [CA1809: Übermäßige lokale Variablen vermeiden](../code-quality/ca1809.md) | Zur Leistungsoptimierung wird ein Wert häufig in einem Prozessorregister statt im Speicher gespeichert. Dieser Vorgang wird als Registrierung des Werts bezeichnet.  Um die Wahrscheinlichkeit zu erhöhen, dass alle lokalen Variablen registriert werden, müssen Sie die Anzahl der lokalen Variablen auf 64 beschränken. |
| [CA1810: Statische Felder von Verweistypen inline initialisieren](../code-quality/ca1810.md) | Wenn ein Typ einen expliziten statischen Konstruktor deklariert, überprüft der JIT-Compiler (Just in Time) jede statische Methode und jeden Instanzenkonstruktor des Typs. Dadurch wird sichergestellt, dass der statische Konstruktor zuvor aufgerufen wurde. Durch die Überprüfung statischer Konstruktoren kann die Leistung herabgesetzt werden. |
| [CA1811: Nicht aufgerufenen privaten Code vermeiden](../code-quality/ca1811.md) | Ein privater oder interner Member (auf Assemblyebene) verfügt nicht über Aufrufer in der Assembly, er wird nicht vom Common Language Runtime aufgerufen und wird nicht von einem Delegaten aufgerufen. |
| [CA1812: Nicht instanziierte interne Klassen vermeiden](../code-quality/ca1812.md) | Eine Instanz eines Typs auf Assemblyebene wird nicht durch Code in der Assembly erstellt. |
| [CA1813: Nicht versiegelte Attribute vermeiden](../code-quality/ca1813.md) | .NET stellt Methoden zum Abrufen von benutzerdefinierten Attributen bereit. Standardmäßig wird mit diesen Methoden die Attributvererbungshierarchie durchsucht. Durch Verwendung eines versiegelten Attributs wird das Durchsuchen der Vererbungshierarchie unterbunden und die Leistung u. U. verbessert. |
| [CA1814: Verzweigte Arrays mehrdimensionalen Arrays vorziehen](../code-quality/ca1814.md) | Ein verzweigtes Array ist ein Array, dessen Elemente wiederum Arrays sind. Die Arrays, aus denen die Elemente bestehen, können unterschiedlich groß sein, was zu weniger Verlust von Speicherplatz für einige Datenmengen führen kann. |
| [CA1815: Equals und Gleichheitsoperator für Werttypen überschreiben](../code-quality/ca1815.md) | Bei Werttypen wird die Reflection-Bibliothek von der geerbten Implementierung von Equals verwendet und der Inhalt aller Felder verglichen. Reflection ist rechenintensiv, und das Überprüfen eines jeden Felds auf Gleichheit ist eventuell unnötig. Wenn Sie erwarten, dass die Benutzer Instanzen vergleichen oder sortieren bzw. dass sie die Instanzen als Schlüssel für Hashtabellen verwenden, sollte der Werttyp Equals implementieren. |
| [CA1816: GC.SuppressFinalize korrekt aufrufen](../code-quality/ca1816.md) | Eine Methode, bei der es sich um eine-Implementierung handelt, ruft keine GC auf. SuppressFinalize oder eine Methode, die keine Implementierung von verwerfen ist, ruft GC auf. SuppressFinalize oder eine Methode ruft GC auf. SuppressFinalize und übergibt etwas anderes als dieses (ich in [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]). |
| [CA1819: Eigenschaften sollten keine Arrays zurückgeben](../code-quality/ca1819.md) | Arrays, die von Eigenschaften zurückgegeben werden, sind nicht schreibgeschützt, auch wenn die Eigenschaft schreibgeschützt ist. Damit das Array gegen Manipulationen geschützt bleibt, muss die Eigenschaft eine Kopie des Arrays zurückgeben. Normalerweise verstehen die Benutzer nicht, welche negativen Auswirkungen der Aufruf einer solchen Eigenschaft auf die Leistung hat. |
| [CA1820: Mithilfe der Zeichenfolgenlänge auf leere Zeichenfolgen prüfen](../code-quality/ca1820.md) | Der Vergleich von Zeichenfolgen mit der String.Length-Eigenschaft oder der String.IsNullOrEmpty-Methode führt erheblich schneller zu Ergebnissen als das Verwenden von Equals. |
| [CA1821: Leere Finalizer entfernen](../code-quality/ca1821.md) | Finalizer sollten möglichst vermieden werden, da durch Verfolgung der Objektlebensdauer zusätzliche Leistung beansprucht wird. Ein leerer Finalizer verursacht zusätzlichen Aufwand ohne jeglichen Vorteil. |
| [CA1822: Member als statisch markieren](../code-quality/ca1822.md) | Member, die nicht auf Instanzdaten zugreifen oder keine Instanzmethoden aufrufen, können als static markiert werden (Shared in [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]). Danach gibt der Compiler nicht virtuelle Aufrufsites an diese Member aus. Dies kann zu einer messbaren Leistungssteigerung für leistungsabhängigen Code führen. |
| [CA1823: Nicht verwendete private Felder vermeiden](../code-quality/ca1823.md) | Es wurden private Felder erkannt, auf die in der Assembly anscheinend kein Zugriff erfolgt. |
| [CA1824: Assemblys mit NeutralResourcesLanguageAttribute markieren](../code-quality/ca1824.md) | Mit dem NeutralResourcesLanguage-Attribut wird dem ResourceManager die Sprache mitgeteilt, in der die Ressourcen einer neutralen Kultur für eine Assembly angezeigt wurden. Auf diese Weise wird die Suchleistung für die erste zu ladende Ressource verbessert und Ihr Workingset kann sich verkleinern. |
| [CA1825: Array Zuordnungen der Länge 0 (null) vermeiden](../code-quality/ca1825.md) | Die Initialisierung eines Arrays der Länge 0 (null) führt zu einer unnötigen Speicher Belegung. Verwenden Sie stattdessen die statisch zugeordnete leere Array Instanz, indem <xref:System.Array.Empty%2A?displayProperty=nameWithType>Sie aufrufen. Die Speicher Belegung wird für alle Aufrufe dieser Methode freigegeben. |
| [CA1826: Eigenschaft anstelle der LINQ-Enumerable-Methode verwenden](../code-quality/ca1826.md) | <xref:System.Linq.Enumerable>Die LINQ-Methode wurde für einen Typ verwendet, der eine äquivalente, effizientere Eigenschaft unterstützt. |
| [CA1827: Verwenden Sie count/LongCount nicht, wenn ein beliebiges verwendet werden kann.](../code-quality/ca1827.md) | <xref:System.Linq.Enumerable.Count%2A>die <xref:System.Linq.Enumerable.LongCount%2A> -Methode oder die <xref:System.Linq.Enumerable.Any%2A> -Methode wurde verwendet, wenn die Methode effizienter wäre. |
| [CA1828: Verwenden Sie "count Async/longcountrytasync" nicht, wenn "anyasync" verwendet werden kann.](../code-quality/ca1828.md) | <xref:Microsoft.EntityFrameworkCore.EntityFrameworkQueryableExtensions.CountAsync%2A>die <xref:Microsoft.EntityFrameworkCore.EntityFrameworkQueryableExtensions.LongCountAsync%2A> -Methode oder die <xref:Microsoft.EntityFrameworkCore.EntityFrameworkQueryableExtensions.AnyAsync%2A> -Methode wurde verwendet, wenn die Methode effizienter wäre. |
| [CA1829: Verwenden Sie die length/Count-Eigenschaft anstelle der Enumerable. Count-Methode.](../code-quality/ca1829.md) | <xref:System.Linq.Enumerable.Count%2A>Die LINQ-Methode wurde für einen Typ verwendet, der eine äquivalente `Length` , `Count` effizientere oder-Eigenschaft unterstützt. |
