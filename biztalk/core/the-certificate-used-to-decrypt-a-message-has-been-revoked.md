---
title: Se ha revocado el certificado usado para descifrar un mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01767cb2-b16e-4b4b-ac4d-cd79b6c8860a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d23ce9304cf6688c9d81238edefb12b0c5b58fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979701"
---
# <a name="the-certificate-used-to-decrypt-a-message-has-been-revoked"></a>Se ha revocado el certificado usado para descifrar un mensaje
## <a name="details"></a>Detalles  
  
|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    Identificador del evento     |                                            -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  |
|    Componente    |                                       Motor AS2                                        |
|  Nombre simbólico  |                        DecryptionCertificateHasBeenRevokedError                         |
|  Texto del mensaje   | Se ha revocado el certificado usado para descifrar un mensaje. Huella digital del certificado: {0} |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el mensaje entrante porque se ha revocado el certificado que debe usarse para descifrar el mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Crear un certificado nuevo para reemplazar el certificado revocado. Agregue el certificado al almacén de certificados Usuario actual/Personal y envíe la clave pública del certificado a la entidad de envío del mensaje AS2.  
  
-   Deshabilite la comprobación de la lista de revocación. Para ello, abra la consola de administración de BizTalk Server y el cuadro de diálogo Propiedades de AS2 para la entidad resuelta para el mensaje saliente, haga clic en el nodo General y, a continuación, desactive la propiedad Comprobar lista de revocaciones de certificados.