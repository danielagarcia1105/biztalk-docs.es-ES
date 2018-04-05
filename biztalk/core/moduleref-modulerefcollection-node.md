---
title: ModuleRef (nodo ModuleRefCollection) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRef node [binding file]
ms.assetid: 61787779-33bd-499a-a5c1-c1e0bd306b48
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed580b022e9896ade824c8cf8eccc2458c7ddce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="moduleref-modulerefcollection-node"></a>ModuleRef (nodo ModuleRefCollection)
El nodo ModuleRef de un archivo de enlace contiene información específica acerca de un ensamblado .NET que se exporta con el archivo de enlace. Un nodo ModuleRef puede incluir, entre otros elementos, descripciones de ensamblados que contengan esquemas, orquestaciones y código personalizado.  
  
## <a name="nodes-in-the-moduleref-node"></a>Nodos del nodo ModuleRef  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[Servicios de](../core/services-moduleref-node.md)|Grabar|ArrayOfServiceRef (ComplexType)|Nodo contenedor para servicios asociados a este ensamblado .NET.|No requerido|Valor predeterminado: ninguno|  
|[TrackedSchemas (nodo ModuleRef)](../core/trackedschemas-moduleref-node.md)|Grabar|ArrayOfSchema (ComplexType)|Nodo contenedor para esquemas asociados a este ensamblado .NET.|No requerido|Valor predeterminado: ninguno|