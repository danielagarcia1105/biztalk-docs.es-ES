---
title: 'Inicio de sesión único: Evento 10718 | Documentos de Microsoft'
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
ms.openlocfilehash: 5b4bf86f4db59033b1ee4202c739ffeda43a587e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271788"
---
# <a name="single-sign-on-event-10718"></a>Inicio de sesión único: Evento 10718
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10718|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_REPLAY_INCORRECT_ADAPTER|  
|Texto del mensaje|El archivo de reproducción o progreso está dañado.%r<br /><br /> Nombre de archivo: %1 %r<br /><br /> Borrar nombre de adaptador: %2 %r<br /><br /> Descifrar el nombre del adaptador: %3|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que se detectó que el archivo de reproducción o progreso está dañado.  
  
 El archivo de reproducción se almacena para un determinado adaptador de sincronización de contraseñas, de manera que puede reproducirse en ese adaptador específico. El nombre de adaptador se almacena tanto sin cifrado como cifrado. El mensaje indica que cuando se descifró el archivo de reproducción para su reproducción, el nombre de adaptador descifrado no coincidió con el nombre de adaptador. Esto puede indicar que el archivo de reproducción está dañado o que sufrió algún tipo de alteración.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Determine por qué el contenido del archivo de reproducción podría haberse modificado y consulte si existe una copia de seguridad.  
  
-   Compruebe si se cambió el secreto principal de SSO o la cuenta de servicio SSO, esto podría afectar el comportamiento de cifrado.  
  
-   Elimine el archivo de reproducción.  
  
 Para obtener más información, vea los recursos siguientes:  
  
-   [Cómo configurar la sincronización de contraseña](../core/how-to-configure-password-synchronization.md)  
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)