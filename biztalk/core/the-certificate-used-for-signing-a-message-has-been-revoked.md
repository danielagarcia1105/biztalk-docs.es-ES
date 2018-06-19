---
title: Se ha revocado el certificado utilizado para firmar un mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f822235a-8ad8-4b63-94de-9b7f9361a071
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8527f89d03d3250a7685380fcabf484254fbbf86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278236"
---
# <a name="the-certificate-used-for-signing-a-message-has-been-revoked"></a>El certificado usado para firmar un mensaje se ha revocado
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|SigningCertificateHasBeenRevokedError|  
|Texto del mensaje|El certificado usado para firmar un mensaje se ha revocado. Huella digital del certificado: {0}|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el mensaje saliente porque se ha recovado el certificado identificado como certificado de firma.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Cree un certificado nuevo para reemplazar al certificado revocado. Agregue el certificado al almacén de certificados de usuario actual, identifíquelo como certificado de firma en la página Certificado del cuadro de diálogo Propiedades de grupo y envíe la clave pública del certificado al destinatario del mensaje AS2.  
  
-   Deshabilite la comprobación de la lista de revocación. Para ello, abra la consola de administración de BizTalk Server y el cuadro de diálogo Propiedades de AS2 para la entidad resuelta para el mensaje saliente, haga clic en el nodo General y, a continuación, desactive la propiedad Comprobar lista de revocaciones de certificados.