---
title: El certificado de firma no se configuró para la entidad AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82928a39-3acf-447b-a0e8-f7c25b6f38dc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d26323670f0229377b304e5f51671de8ef10021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967549"
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a>El certificado de firma no se ha configurado para la entidad AS2
## <a name="details"></a>Detalles  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  Nombre del producto   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| Versión del producto |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    Identificador del evento     |                                             -                                             |
|  Origen del evento   |  EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
|    Componente    |                                        Motor AS2                                         |
|  Nombre simbólico  |                               SigningCertNotConfiguredError                               |
|  Texto del mensaje   | El certificado de firma no se ha configurado para la entidad AS2.  AS2-de: {0} AS2-para: {1} |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar el mensaje saliente porque el certificado de firma no se ha configurado para el grupo.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice el procedimiento siguiente para configurar el certificado de firma:  
  
1.  Abra la consola de administración de BizTalk Server.  
  
2.  Vaya al nodo Grupo y haga clic en el nodo Certificado.  
  
3.  Especifique el nombre común y la huella digital del certificado.