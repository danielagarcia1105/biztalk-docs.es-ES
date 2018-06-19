---
title: PuertosEnvío (nodo DistributionList) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPorts node [binding file]
ms.assetid: 9cb645fa-cb9c-44eb-9f98-2fc507b2be67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9eaf692bd61913e604731fc2e2cea373fd31f48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269636"
---
# <a name="sendports-distributionlist-node"></a>PuertosEnvío (nodo DistributionList)
El nodo SendPorts del nodo DistributionList de un archivo de enlace es el nodo contenedor de las referencias del puerto de envío que aparecen en la lista de distribución.  
  
> [!NOTE]
>  A una lista de distribución se hace referencia como un grupo de puertos de envío en el administrador de BizTalk.  
  
## <a name="nodes-in-the-sendports-node"></a>Nodos del nodo SendPorts  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[SendPortRef](../core/sendportref-sendports-node.md)|Grabar|SendPortRef (ComplexType)|Nodo contenedor de una referencia a un puerto de envío realizada por la lista de distribución.|No requerido|Valor predeterminado: ninguno|