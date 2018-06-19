---
title: Finalizadores de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff907e262088acd188028282fe2e03441071358a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961986"
---
# <a name="user-trailers"></a>Finalizadores de usuario
Finalizadores de usuario, excepto el finalizador de distrib, son opcionales y cuando está presente, se producen en el orden siguiente:  
  
|Código de finalizador|Nombre|  
|------------------|----------|  
|MAC|Código de autenticación de mensaje|  
|PAC|Código de autenticación propietario|  
|DISTRIB|Suma de comprobación|  
|TNG|Aprendizaje|  
|PDE|Emisión de duplicados posibles|  
  
-   **Finalizador de código (MAC) de autenticación de mensaje.** Permite la autenticación por el usuario que recibe. El finalizador de MAC va seguido de un resultado de la autenticación. Este finalizador es obligatorio para la mayoría de categorías de mensaje de usuario a otro dentro de la aplicación de FIN.  
  
     Cuando se utiliza el servicio de copia de FIN, un finalizador de PAC (si existe) sigue el finalizador de MAC. El código siguiente es un ejemplo de un finalizador de MAC:  
  
    ```  
    {MAC:<authentication-result>}  
    where <authentication-result> = 8!h  
    ```  
  
-   **Finalizador de autenticación propietario código (PAC).** El finalizador de PAC se utiliza en el servicio de copia de FIN solo cuando se utiliza la opción de autenticación dobles. Mensajes de usuario a otro bloque 5 de FINÉS incluyen el finalizador de PAC inmediatamente después del finalizador de MAC, si está presente. Este resultado se calcula en los campos extraídos del bloque 4 del mensaje, el valor del campo 115, si está presente y el \<resultado de la autenticación\> del finalizador de MAC para servicios de copia con doble autenticación.  
  
     Como resultado, el indicador de bloque final (CrLf-) se incluye en el cálculo de PAC y los campos se definen como sigue:  
  
    -   Los primeros cuatro caracteres son CrLf:  
  
    -   El campo y el delimitador están presentes, es decir, 32:, 20:, y así sucesivamente.  
  
    -   Todos los subcampos y sus delimitadores están presentes.  
  
     El código siguiente es un ejemplo del formato de finalizador PAC:  
  
    ```  
    {PAC:[<authentication-result>]}  
    where <authentication-result> is mandatory on input messages only and  
    <authentication-result> = 8!h  
    ```  
  
-   **Finalizador de distrib (suma de comprobación) (obligatorio para todos los mensajes FIN)**  
  
     El finalizador de distrib es obligatorio para todos los mensajes FIN y se calcula basándose en la dirección del destinatario (12 caracteres con el carácter noveno reemplazan por *X* junto con el bloque de texto). Este finalizador, el sistema y el CBT para comprobar que los mensajes no están dañados debido a un fallo en el sistema o un error de transmisión sin detectar.  
  
     El código siguiente es un ejemplo del formato de finalizador distrib:  
  
    ```  
    {CHK:<checksum-result>}  
    where <checksum-result> = 12!h  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)