---
title: Se produjo un error al descifrar un mensaje AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bfb1d2a-c79d-4541-8a6d-bab0986f456b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 183933ae48468569cdd89f1d051f4bf961c71e05
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22230188"
---
# <a name="an-error-occurred-when-decrypting-an-as2-message"></a>Error al descifrar un mensaje AS2
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|-|  
|Texto del mensaje|Error al descifrar un mensaje AS2.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción o el componente de descodificador AS2 no pudo descifrar el mensaje AS2. Esto puede tener lugar si el certificado usado en el proceso de descifrado no es válido, no se almacena en la ubicación adecuada o no coincide con el certificado usado en el proceso de descifrado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Compruebe que el contenedor de cifrado del mensaje AS2 es válido. Si no es así, determine por qué el codificador ha codificado el mensaje de manera incorrecta.  
  
-   Compruebe que coinciden la clave pública usada en el proceso de cifrado y la clave privada usada en el proceso de descifrado.  
  
-   Compruebe que la propiedad Uso de la clave del certificado usado para el cifrado y el descifrado se ha establecido en "Cifrado de datos".  
  
-   Compruebe que no haya ninguna cadena rota de entidades de certificación intermedias. Si es así, borre el certificado antiguo, y cree y use uno nuevo.  
  
-   Compruebe que el certificado no ha expirado. Para ello, compruebe su fecha de expiración en el almacén de certificados (mediante MMC con un complemento de certificados).  
  
-   Compruebe que el certificado no se haya revocado. Para ello, compruebe la lista de revocación de certificados. (Puede hacer que BizTalk Server compruebe esto automáticamente si activa la propiedad Comprobar lista de revocaciones de certificados en las propiedades generales de AS2 de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).  
  
-   Compruebe que el certificado usado para el descifrado se almacena en el almacén Usuario actual/Personal de cada servidor BizTalk que hospeda una canalización del descodificador de MIME/SMIME como cada cuenta de servicio de instancia de host.