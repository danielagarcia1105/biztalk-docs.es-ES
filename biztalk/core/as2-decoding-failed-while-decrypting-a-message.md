---
title: "Error de descodificación de AS2 al descifrar un mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab6f7ecd-23cf-4f6f-8f63-acc6618dc544
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72ef95ad35e1da933197bac11a9d80f98ddabd6a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="as2-decoding-failed-while-decrypting-a-message"></a>Error de descodificación de AS2 al descifrar un mensaje
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|-|  
|Texto del mensaje|Error de descodificación de AS2 al descifrar un mensaje.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción o el componente de descodificador AS2 no pudo descifrar el mensaje AS2. Esto puede tener lugar si el certificado usado en el proceso de descifrado no es válido, no se almacena en la ubicación adecuada o no coincide con el certificado usado en el proceso de descifrado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Compruebe que el contenedor de cifrado del mensaje AS2 es válido. Si no es así, determine por qué el codificador ha codificado el mensaje de manera incorrecta.  
  
-   Compruebe que coinciden la clave pública usada en el proceso de cifrado y la clave privada usada en el proceso de descifrado.  
  
-   Compruebe que la propiedad Uso de la clave del certificado usado para el cifrado y el descifrado se ha establecido en "Cifrado de datos".  
  
-   Compruebe que no haya ninguna cadena rota de entidades de certificación intermedias. Si es así, borre el certificado antiguo, y cree y use uno nuevo.  
  
-   Compruebe que el certificado no ha expirado. Para ello, compruebe su fecha de expiración en el almacén de certificados (mediante MMC con un complemento de certificados).  
  
-   Compruebe que el certificado no se haya revocado. Para ello, compruebe la lista de revocación de certificados. (Puede tener que BizTalk Server compruebe esto automáticamente mediante la comprobación de la propiedad Comprobar lista de revocación de certificados en las propiedades generales de AS2 en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.)  
  
-   Compruebe que el certificado usado para el descifrado se almacena en el almacén Usuario actual/Personal de cada servidor BizTalk que hospeda una canalización del descodificador de MIME/SMIME como cada cuenta de servicio de instancia de host.