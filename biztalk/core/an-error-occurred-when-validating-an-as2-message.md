---
title: Se produjo un error al validar un mensaje de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cf97c63-2bff-4474-9cd8-f68634493dcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ac51c94b1a414a7cef5d7777eb4dcd08845e5d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996349"
---
# <a name="an-error-occurred-when-validating-an-as2-message"></a>Se produjo un error al validar un mensaje AS2
## <a name="details"></a>Detalles  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                   |
| Versión del producto |                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                               |
|    Identificador del evento     |                                                           -                                                           |
|  Origen del evento   |                EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
|    Componente    |                                                      Motor AS2                                                       |
|  Nombre simbólico  |                                                           -                                                           |
|  Texto del mensaje   | Se produjo un error al validar un mensaje AS2. Asegúrese de que los certificados no han caducado ni se han revocado. |

## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción AS2 o la canalización de envío AS2 no pudo procesar el mensaje AS2. Esto puede tener lugar si el certificado usado en el proceso de comprobación de firma no es válido, no se almacena en la ubicación adecuada o no coincide con el certificado usado en el proceso de firma.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  

- Compruebe que el contenedor de firmas del mensaje AS2 es válido. Si no es así, determine por qué el codificador ha firmado el mensaje de manera incorrecta.  

- Compruebe que coinciden la clave privada usada en el proceso de firma y la clave pública usada en el proceso de comprobación de firma.  

- Compruebe que la propiedad Uso de la clave del certificado usado para firmar y la comprobación de la firma se ha establecido en "Cifrado de datos".  

- Compruebe que no haya ninguna cadena rota de entidades de certificación intermedias. Si es así, borre el certificado antiguo, y cree y use uno nuevo.  

- Compruebe que el certificado no ha expirado. Para ello, compruebe su fecha de expiración en el almacén de certificados (mediante MMC con un complemento de certificados).  

- Compruebe que el certificado no se haya revocado. Para ello, compruebe la lista de revocación de certificados. (Puede tener que BizTalk Server compruebe esto automáticamente mediante la comprobación de la propiedad Comprobar lista de revocación de certificados en las propiedades generales de AS2 en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.)  

- Compruebe que el certificado usado para la comprobación de firmas se almacena en el almacén Equipo local/Otras personas de cada servidor BizTalk que hospeda una canalización del descodificador de MIME/SMIME como cada cuenta de servicio de instancia de host.
