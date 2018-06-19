---
title: El intercambio contenía un error estructural-antes del primer grupo funcional | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12202148-0a32-464e-8dbd-d01b9ba530eb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d5ab490de214f53e85ea32c1b243456f837c72e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278660"
---
# <a name="the-interchange-had-a-structural-error-in-before-the-first-functional-group"></a>El intercambio contenía un error estructural-antes del primer grupo funcional
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12InterchangeStructuralErrorBefore1stGroup|  
|Texto del mensaje|El intercambio con el identificador '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural en o antes del primer grupo funcional|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante por una de las siguientes razones:  
  
-   Se produjo un error estructural en los segmentos ISA o IEA o en el primer grupo funcional del intercambio, de modo que el intercambio no se ajustaba al esquema aplicable.  
  
-   No se ha implementado X12ServiceSchema (en BaseArtifacts.dll).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Pida al remitente del intercambio que cambie los segmentos ISA o IEA, o el primer grupo funcional de modo que se ajuste al esquema aplicable y vuelva a enviar el intercambio.  
  
-   Asegúrese de que BaseArtifacts.dll incluye X12ServiceSchema y está implementado. Para ello, abra la consola de administración de BizTalk Server, abra el nodo aplicación EDI de BizTalk y el nodo de esquemas y compruebe que X12ServiceSchema aparece.