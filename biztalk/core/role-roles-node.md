---
title: Rol (nodo Roles) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Role node [binding file]
ms.assetid: dfe2a579-7090-4d85-87e5-d627598c4ee8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d70e99568db262ef5abd5b0885cb814c722347f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="role-roles-node"></a>Rol (nodo Roles)
El nodo Rol del nodo Roles de un archivo de enlace especifica información acerca de un rol enlazado a un servicio que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-role-node"></a>Nodos del nodo Rol  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del rol.|No requerido|Valor predeterminado: vacío|  
|RoleLinkTypeName|Attribute|xs:string|Especifica el nombre del tipo de vínculo de rol asociado al rol.|No requerido|Valor predeterminado: vacío|  
|RoleType|Attribute|RoleRefType (SimpleType)|Especifica el tipo de rol asociado al rol.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles incluyen:<br /><br /> : Desconocido<br />: Implementa<br />-Usa|  
|[Entidades dadas de alta](../core/enlisted-parties-role-node.md)|Grabar|ArrayOfEnlistedParty (ComplexType)|Nodo contenedor para las entidades dadas de alta enlazadas a ese rol.|No requerido|Valor predeterminado: ninguno|