---
title: Cómo funciona el ejemplo de Namespace Remove | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf5834b4-e0fd-4180-9d15-4cdd99f0f353
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e82e4f369d8db2230b44586cbb928ea57b27f462
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294524"
---
# <a name="how-the-remove-namespace-sample-works"></a>Cómo funciona el ejemplo de Namespace Remove
Usan las pruebas de segunda y terceros el **quitar Namespace** componente ubicado en el **NamespaceSampleSendPipeline** canalización. Toma como entrada un documento con un espacio de nombres en el nodo raíz, como la siguiente:  
  
```  
<ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2"   
    xmlns:ns0="http://schemas.microsoft.biztalk.esb.test.com/test">  
```  
  
 El **quitar Namespace** componente simplemente quita este espacio de nombres y devuelve un documento que no tiene un espacio de nombres del nodo raíz, como se muestra aquí:  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```