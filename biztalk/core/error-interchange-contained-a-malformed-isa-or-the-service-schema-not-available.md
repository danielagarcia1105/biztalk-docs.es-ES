---
title: El intercambio contenía un ISA formado incorrectamente o el esquema servicio no estaba disponible | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d285f6-26fb-4a3b-a959-a17623321b20
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce469b25a2ba15c3038ea9079c3f22fc4f8c0c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010717"
---
# <a name="the-interchange-contained-a-malformed-isa-or-the-service-schema-was-not-available"></a>El intercambio contenía un ISA formado incorrectamente o el esquema Servicio no estaba disponible
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| Versión del producto |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    Identificador del evento     |                                                         -                                                          |
|  Origen del evento   |               EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
|    Componente    |                                                     Motor EDI                                                     |
|  Nombre simbólico  |                                                 MalformedIsaError                                                  |
|  Texto del mensaje   | El intercambio contenía un ISA formado incorrectamente o el esquema Servicio no estaba disponible. Se ha rechazado completamente. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque los segmentos ISA o IEA del intercambio no se ajustaban a X12ServiceSchema, o bien X12ServiceSchema (en BaseArtifacts.dll) no estaba implementado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Pida al remitente del intercambio que cambie los segmentos ISA e IEA de modo que se ajusten a X12ServiceSchema.  
  
-   Asegúrese de que BaseArtifacts.dll incluye X12ServiceSchema y está implementado. Para ello, abra la consola de administración de BizTalk Server, el nodo Aplicación EDI de BizTalk y el nodo Esquemas. A continuación, compruebe que X12ServiceSchema aparece en la lista.