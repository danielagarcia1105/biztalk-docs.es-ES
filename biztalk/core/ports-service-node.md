---
title: Puertos (nodo servicio) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Ports node [binding file]
ms.assetid: 498d4310-4e9e-4e74-bc3d-5cbf1319c4ff
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e09470b9f3287cce5ce15c2941d2165157ec48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ports-service-node"></a>Puertos (nodo Servicio)
El nodo Puertos de un archivo de enlace es el nodo primario de todos los nodos Puerto que contienen información específica acerca de los puertos enlazados a un servicio que se exporta con el archivo de enlace.  
  
## <a name="node-in-the-ports-node"></a>Nodo del nodo Puertos  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[Puerto](../core/port-ports-node.md)|Grabar|ServicePortRef (ComplexType)|Especifica información acerca de un puerto que está enlazado a un servicio que se exporta con el archivo de enlace.|No requerido|Valor predeterminado: ninguno|