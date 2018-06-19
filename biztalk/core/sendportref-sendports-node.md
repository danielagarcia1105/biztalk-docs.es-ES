---
title: SendPortRef (nodo puertosEnvío) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortRef node [binding file]
ms.assetid: 6c799b23-a9a4-4686-a04e-0450b4eef889
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9290a535ebcaf0c23097cacbd3412f64c2808f40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269964"
---
# <a name="sendportref-sendports-node"></a>SendPortRef (nodo SendPorts)
El nodo SendPortRef del nodo SendPorts de un archivo de enlace especifica el nombre del puerto de envío al que hace referencia una lista de distribución.  
  
> [!NOTE]
>  A una lista de distribución se hace referencia como un grupo de puertos de envío en el administrador de BizTalk.  
  
## <a name="nodes-in-the-sendportref-node"></a>Nodos del nodo SendPortRef  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del puerto de envío al que hace referencia la lista de distribución.|No requerido|Valor predeterminado: vacío|