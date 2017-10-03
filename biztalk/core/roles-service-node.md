---
title: Funciones (nodo servicio) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Roles node [binding file]
ms.assetid: 847755c9-1697-41a0-b870-f9e795a1a2a6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b47f5ae94326b0555c0c9cd84752cb9f1c409daa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="roles-service-node"></a>Funciones (nodo Servicio)
El nodo Roles de un archivo de enlace es el nodo primario de todos los nodos de rol que proporcionan información específica acerca del enlazado de cada rol a un servicio que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-roles-node"></a>Nodos del nodo Roles  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[Rol](../core/role-roles-node.md)|Grabar|RoleRef (ComplexType)|Especifica información acerca de un rol que está enlazado a un servicio que se exporta con el archivo de enlace.|No requerido|Valor predeterminado: ninguno|