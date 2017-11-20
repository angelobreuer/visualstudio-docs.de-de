---
title: "Azure SDK für Python | Microsoft-Dokumentation"
ms.custom: 
ms.date: 3/7/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d30fddae-8e2f-4f50-90d3-8ed2cd35c7a6
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 6a91f4d54ce2ef96816787afe1ae8c589f862630
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="azure-sdk-for-python"></a>Azure-SDK für Python

Das Azure SDK für Python vereinfacht die Nutzung und Verwaltung von Microsoft Azure-Diensten in Anwendungen unter Windows, Mac OS X und Linux.

## <a name="installation"></a>Installation

Das Azure SDK wird über den [Python-Paketindex](https://pypi.python.org/pypi/azure) installiert.

Installieren Sie die **neueste stabile Version** (unterstützt Python 2.7 und 3.3+) wie folgt:

```bash
pip install azure
```

Sie können auch den entsprechenden Artikel der Azure-Dokumentation lesen: [Installieren von Python und SDK](https://azure.microsoft.com/documentation/articles/python-how-to-install/).

## <a name="documentation"></a>Dokumentation

Unter [azure-sdk-for-python.readthedocs.org](http://azure-sdk-for-python.readthedocs.org/en/latest/index.html) finden Sie die entsprechende Dokumentation.

Das [Python Developer Center](http://azure.microsoft.com/develop/python/) umfasst ebenfalls eine Reihe nützlicher Ressourcen für das Azure SDK für Python, beispielsweise etwa verschiedene Tutorials:

  - Erstellen von Web-Apps mit [Django](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-django-app) [Flask](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-flask-app) und [Bottle](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-bottle-app).
  - [Blobspeicher](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-blob-storage)
  - [Tabellenspeicher](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-table-storage)
  - [Warteschlangenspeicher](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-queue-storage)
  - [DocumentDB](https://docs.microsoft.com/azure/documentdb/documentdb-python-application)
  - [Service Bus-Warteschlangen](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
  - [Service Bus-Themen/-Abonnements](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
  - [Dienstverwaltung](https://docs.microsoft.com/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Für öffentliche APIs ohne Dokumentation sind die Komponententests im [GitHub-Repository für das SDK](https://github.com/Azure/azure-sdk-for-python) eine gute Informationsquelle:

- [Komponententests für Speicher](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Komponententests für Service Bus](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Komponententests für die Dienstverwaltung](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)
- [Komponententests für die Ressourcenverwaltung](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-mgmt/tests)

## <a name="support"></a>Unterstützung

Das Git-Repository für das SDK befindet sich hier: [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python).

Wenn Ihnen Fehler auffallen oder Sie Fragen zur Verwendung des SDK haben, [melden Sie Probleme im Repository](https://github.com/Azure/azure-sdk-for-python/issues).