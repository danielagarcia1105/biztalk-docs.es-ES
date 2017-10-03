---
title: RetractByType | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RetractByType function [Business Rules Engine], TypedXMLDocument
- RetractByType function [Business Rules Engine]
- RetractByType function [Business Rules Engine], .NET objects
- RetractByType function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e8867553-ee3c-46be-84cd-d5373eaf3337
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da8cd4581007ad2bd93ed66ebce4f5de6378280c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="retractbytype"></a>RetractByType
El **RetractByType** función extrae todas las instancias de un tipo especificado en la memoria de trabajo, mientras que la **Retract**función retira solo elementos específicos de un tipo determinado. Los siguientes párrafos describen cómo **RetractByType** función funciona con entidades de tipos diferentes.  
  
## <a name="net-objects"></a>Objetos .NET  
 Todos los objetos de una clase determinada se retiran de la memoria de trabajo. Basta con arrastrar la clase desde el panel de datos de las clases de .NET en el **RetractByType** (función).  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 Se retiran todas las instancias. Esto significa que todos los **TypedXmlDocument**s con el mismo **DocumentType.Selector** se retiran. Debe arrastrar el nodo adecuado desde el panel de datos de esquemas XML en la **RetractByType** (función). Coherente con la **Retract** funcione, si lleva a cabo una **RetractByType** en el nodo raíz del documento, no solo serán todos **TypedXmlDocuments** impone con ese  **DocumentType** se retira, pero todos los secundarios **TypedXmlDocuments** (**XmlNode**s en la jerarquía de árbol) asociadas con esos primario **TypedXmlDocuments**  también se puede retirarse.  
  
## <a name="typeddatatable-and-dataconnection"></a>TypedDataTable y DataConnection  
 **Retirar** y **RetractByType** son equivalentes a ambos **TypedDataTable** y **DataConnection**. Dado que **DataSetName.DataTableName** es un identificador único para ambos tipos, hay sólo una instancia del motor de en cualquier momento en el tiempo. Al igual que con **Retract**, arrastre la tabla en la **RetractByType** (función).  
  
## <a name="see-also"></a>Vea también  
 [Funciones de Control del motor](../core/engine-control-functions.md)