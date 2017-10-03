---
title: Esquema no encontrado para CLR Namespace y rootName | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db283d81-1cb0-460d-ace4-49a91ceb4a02
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06db4a89803b8386ccbb45372b72423e83c6ff7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-not-found-for-clr-namespace-and-rootname"></a>Esquema no encontrado para CLR Namespace y rootName
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|SchemaNotFoundForCLRAndRN|  
|Texto del mensaje|Esquema no encontrado para CLR Namespace = {0} y rootName = {1}|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no encontró el esquema del documento mediante el nombre raíz asociado con el intercambio y el espacio de nombres asociado con la entidad que se ha resuelto para el intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el nombre raíz tomado del intercambio y el espacio de nombres determinado a partir de las propiedades de la entidad resuelta se corresponden juntos con un esquema implementado. BizTalk determina el nombre raíz a partir del tipo de documento y la versión del intercambio. BizTalk determina el esquema a partir del campo Espacio de nombres de destino predeterminado (para esquemas predeterminados) o de la cuadrícula "Habilitar definiciones de conjuntos de transacciones personalizadas" (para esquemas personalizados) en las propiedades de procesamiento de intercambio.