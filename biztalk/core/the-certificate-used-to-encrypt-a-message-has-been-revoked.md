---
title: Se ha revocado el certificado usado para cifrar un mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c90690-002a-43bc-85f2-8aa5e7511ffa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4476249160f71e20012ff92f749042775132d5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971437"
---
# <a name="the-certificate-used-to-encrypt-a-message-has-been-revoked"></a>El certificado utilizado para cifrar un mensaje se ha revocado
## <a name="details"></a>Detalles  
  
|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    Identificador del evento     |                                            -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  |
|    Componente    |                                       Motor AS2                                        |
|  Nombre simbólico  |                        EncryptionCertificateHasBeenRevokedError                         |
|  Texto del mensaje   | El certificado utilizado para cifrar un mensaje se ha revocado. Huella digital del certificado: {0} |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el mensaje saliente porque se ha recovado el certificado identificado como certificado de cifrado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Pida al receptor del mensaje que cree un certificado nuevo y le envíe la clave pública. Agregue el certificado al almacén de certificados Equipo local\Otras personas e identifique el certificado como certificado de cifrado en la página Certificado del cuadro de diálogo Propiedades de puerto de envío.  
  
-   Deshabilite la comprobación de la lista de revocación. Para ello, abra la consola de administración de BizTalk Server y el cuadro de diálogo Propiedades de AS2 para la entidad resuelta para el mensaje saliente, haga clic en el nodo General y, a continuación, desactive la propiedad Comprobar lista de revocaciones de certificados.