---
title: 'De sesión único: Evento 10718 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de075c59-8396-48d1-be55-79303f83f984
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 958753d50d15662cd138ea5460c121eefcac8a98
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004989"
---
# <a name="single-sign-on-event-10718"></a>De sesión único: Evento 10718
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                     Inicio de sesión único (SSO) empresarial                                                                     |
| Versión del producto |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    Identificador del evento     |                                                                               10718                                                                               |
|  Origen del evento   |                                                                              ENTSSO                                                                               |
|    Componente    |                                                                                N\D                                                                                |
|  Nombre simbólico  |                                                                SSO_ERROR_REPLAY_INCORRECT_ADAPTER                                                                 |
|  Texto del mensaje   | El archivo de reproducción o progreso está dañado.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> Borrar el nombre de adaptador: %2 %r<br /><br /> Nombre del adaptador puede descifrar: %3 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que se detectó que el archivo de reproducción o progreso está dañado.  

 El archivo de reproducción se almacena para un determinado adaptador de sincronización de contraseñas, de manera que puede reproducirse en ese adaptador específico. El nombre de adaptador se almacena tanto sin cifrado como cifrado. El mensaje indica que cuando se descifró el archivo de reproducción para su reproducción, el nombre de adaptador descifrado no coincidió con el nombre de adaptador. Esto puede indicar que el archivo de reproducción está dañado o que sufrió algún tipo de alteración.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  

- Determine por qué el contenido del archivo de reproducción podría haberse modificado y consulte si existe una copia de seguridad.  

- Compruebe si se cambió el secreto principal de SSO o la cuenta de servicio SSO, esto podría afectar el comportamiento de cifrado.  

- Elimine el archivo de reproducción.  

  Para obtener más información, vea los recursos siguientes:  

- [Cómo configurar la sincronización de contraseñas](../core/how-to-configure-password-synchronization.md)  

- [Sincronización de contraseñas](../core/password-synchronization2.md)
