---
title: Finalizadores de usuario | Microsoft Docs
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
ms.openlocfilehash: 10bc0d4d0fcdb36311e0590d9ae04239db168ed7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010221"
---
# <a name="user-trailers"></a>Finalizadores de usuario
Finalizadores de usuario, excepto el finalizador "chk", son opcionales y cuando está presente, se producen en el orden siguiente:  
  
|Código de finalizador|Nombre|  
|------------------|----------|  
|MAC|Código de autenticación de mensajes|  
|PAC|Código de autenticación propietario|  
|"CHK"|Suma de comprobación|  
|TNG|Aprendizaje|  
|PDE|Emisión de duplicados posibles|  
  
- **Finalizador de código (MAC) de autenticación de mensaje.** Permite la autenticación del usuario que recibe. El finalizador de MAC seguido de un resultado de la autenticación. Este finalizador es obligatorio para la mayoría de las categorías de mensaje al usuario dentro de la aplicación a FIN.  
  
   Cuando se usa el servicio de FIN, un finalizador de PAC (si existe) sigue el finalizador de MAC. El código siguiente es un ejemplo de un finalizador de MAC:  
  
  ```  
  {MAC:<authentication-result>}  
  where <authentication-result> = 8!h  
  ```  
  
- **Finalizador de código (PAC) de autenticación propietario.** El finalizador de PAC se utiliza en el servicio de FIN solo cuando se usa la opción de doble autenticación. Los mensajes de usuario a otro bloque 5 de FIN incluyen el finalizador de PAC inmediatamente después del finalizador de MAC, si está presente. Este resultado se calcula en los campos extraídos de bloque de 4 del mensaje, el valor del campo 115, si está presente y el \<resultado de la autenticación\> del remolque MAC para los servicios de copia con doble autenticación.  
  
   Como resultado, el indicador de final del bloque (CrLf-) se incluye en el cálculo de PAC y los campos se definen como sigue:  
  
  - Los primeros cuatro caracteres son CrLf:  
  
  - El campo y los delimitadores están presentes, es decir, 32A:, 20:, y así sucesivamente.  
  
  - Todos los subcampos y sus delimitadores están presentes.  
  
    El código siguiente es un ejemplo del formato de finalizador PAC:  
  
  ```  
  {PAC:[<authentication-result>]}  
  where <authentication-result> is mandatory on input messages only and  
  <authentication-result> = 8!h  
  ```  
  
- **Finalizador "chk" (suma de comprobación) (obligatorio para todos los mensajes FIN)**  
  
   El finalizador "chk" es obligatorio para todos los mensajes FIN y se calcula basándose en la dirección del destinatario (12 caracteres con la novena reemplazan por *X* además del bloque de texto). Este finalizador permite que el sistema y el CBT para comprobar que los mensajes no están dañados debido a un error de funcionamiento del sistema o un error de transmisión no detectados.  
  
   El código siguiente es un ejemplo del formato de finalizador "chk":  
  
  ```  
  {CHK:<checksum-result>}  
  where <checksum-result> = 12!h  
  ```  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)