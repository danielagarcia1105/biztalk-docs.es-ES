---
title: "Transformación (nodo OutboundTransforms) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transform node [binding file]
ms.assetid: 928a93cd-7a26-4148-b1af-dc0bc316f8c1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b44dc5ffd444ebaee8f1f3007f27343c389c5e5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transform-outboundtransforms-node"></a>Transformación (nodo OutboundTransforms)
El nodo Transformación del nodo OutboundTransforms de un archivo de enlace contiene información específica acerca de una asignación de BizTalk Server que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-transform-node"></a>Nodos del nodo Transformación  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|Attribute|xs:string|Especifica el nombre completo de la asignación.|No requerido|Valor predeterminado: vacío|  
|AssemblyQualifiedName|Attribute|xs:string|Especifica el nombre completo del ensamblado de la asignación.|No requerido|Valor predeterminado: vacío|