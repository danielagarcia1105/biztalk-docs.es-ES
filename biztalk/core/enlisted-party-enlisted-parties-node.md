---
title: Da de alta entidades (nodo entidades dadas de alta) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enlisted Parties node [binding file]
ms.assetid: 2ff7b563-17c5-48e9-b33e-62c821188448
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624f74d3b49b80e8000723c3f7451c52b37c8d3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239956"
---
# <a name="enlisted-party-enlisted-parties-node"></a>Entidad dada de alta (nodo de Entidades dadas de alta)
El nodo Entidad dada de alta de un archivo de enlace contiene información específica acerca de una entidad dada de alta asociada a un rol que se exporta con el archivo de enlace.  
  
## <a name="nodes-in-the-enlisted-party-node"></a>Nodos del nodo Entidad dada de alta  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre de la entidad dada de alta.|No requerido|Valor predeterminado: vacío|  
|[Asignaciones](../core/mappings-enlisted-party-node.md)|Grabar|ArrayOfEnlistedPartyMapping (ComplexType)|Nodo contenedor de las asignaciones entre puertos de entidad y operaciones de tipo de puerto de rol.|No requerido|Valor predeterminado: ninguno|