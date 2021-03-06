---
title: No se encuentra el certificado usado para firmar un mensaje en el almacén de certificados local | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff3c7a2-954c-4c62-a7b2-06f7a38d61b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feb6a4cc1e5272a4a2c6760ca4585dd0dc10c031
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001365"
---
# <a name="the-certificate-used-for-signing-a-message-cannot-be-located-in-the-local-certificate-store"></a>El certificado usado para firmar un mensaje no puede ubicarse en el almacén local de certificados
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| Versión del producto |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                |
|    Identificador del evento     |                                                            -                                                             |
|  Origen del evento   |                  EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                  |
|    Componente    |                                                        Motor AS2                                                        |
|  Nombre simbólico  |                                                 CertificateMissingError                                                  |
|  Texto del mensaje   | El certificado usado para firmar un mensaje no puede ubicarse en el almacén local de certificados. Huella digital del certificado: {0} |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el mensaje saliente porque el certificado identificado como certificado de firma no se encontraba en el almacén de certificados requerido.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
1.  Identifique el certificado de firma. Para ello, abra la consola de administración de BizTalk Server, haga clic con el botón secundario en Grupo de BizTalk y, a continuación, haga clic en el nodo Certificado.  
  
2.  Abra MMC, agregue el complemento para Mi cuenta de usuario y abra el nodo Certificados, Personal y Certificados.  
  
3.  Asegúrese de que el almacén de certificados Usuario actual contiene la clave privada para dicho certificado de firma y consulte la huella digital identificada en el texto de mensaje de error.