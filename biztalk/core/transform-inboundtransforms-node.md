---
title: "Transformación (nodo InboundTransforms) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transform node [binding file]
ms.assetid: c1bad23e-78a4-4fd4-95ef-30601393d53c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 705b1b04b8305330ab1d5ff705c5025f24b0685c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transform-inboundtransforms-node"></a>Transformación (nodo InboundTransforms)
El nodo Transformación del nodo InboundTransforms de un archivo de enlace contiene información específica acerca de una asignación de BizTalk Server que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-transform-node"></a>Nodos del nodo Transformación  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|Attribute|xs:string|Especifica el nombre completo de la asignación.|No requerido|Valor predeterminado: vacío|  
|AssemblyQualifiedName|Attribute|xs:string|Especifica el nombre completo del ensamblado de la asignación.|No requerido|Valor predeterminado: vacío|