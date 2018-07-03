---
title: Finalizadores del sistema | Microsoft Docs
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
ms.assetid: 2fd49be9-afe8-47c6-a613-fa469faa2126
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d991125654e04167b026aa98c62c8ffdc7b2b8e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006021"
---
# <a name="system-trailers"></a>Finalizadores del sistema
Finalizadores del sistema proporcionan detalles adicionales o especiales sobre el mensaje SWIFT. Si cualquiera de la primera finalizadores tres del sistema están presentes, se producen en el orden siguiente. Los finalizadores de sistema restantes pueden producirse en cualquier orden.  
  
|Código de finalizador|Nombre|  
|------------------|----------|  
|**"CHK"**|Suma de comprobación|  
|**SYS**|Sistema originó el mensaje|  
|**TNG**|Aprendizaje|  
|**PDM**|Posible mensaje duplicado|  
|**DLM**|Mensaje demorado|  
|**MRF**|Referencia de mensajes|  
  
- **Sistema había originado el finalizador de mensaje (SYS).** El mensaje del sistema o el mensaje de servicio, que es generado por un sistema PLT, tiene un finalizador SYS. Todos solicitado mensajes del sistema con un identificador de servicio de 01, contienen el MIR de la solicitud y pueden contener el tiempo.  
  
   El código siguiente es un ejemplo del formato de finalizador SYS:  
  
  ```  
  {SYS:[<time><mir>]}  
  ```  
  
- **Prueba y entrenamiento de finalizador de mensaje (TNG).** El finalizador TNG es obligatorio para mensajes Finanzas y GPA (con un identificador de servicio de 01) enviados por o entregados a una prueba y entrenamiento lógico Terminal (LT). Este finalizador tiene sólo una etiqueta y ningún valor.  
  
   El código siguiente es un ejemplo del formato TNG finalizador:  
  
  ```  
  {TNG:}  
  ```  
  
- **Finalizador de emisión duplicados posibles (PDE).** El destino del mensaje usa el finalizador PDE. Solo se aplica a mensajes de usuario a FIN (con un identificador de servicio de 01) y las categorías de mensaje reservadas para los mensajes de banca. El sistema puede contener varios PDEs. El sistema no comprueba el orden ni restringir el número (excepto para la longitud máxima de mensajes).  
  
   El sistema acepta con el formato correcto finalizadores PDE aplicados a los mensajes de sistema de usuario, pero no procesarlos. Esto significa que el sistema no se comprueba para ver si existe el mensaje original. Por lo tanto, el sistema puede procesar una solicitud de recuperación que se envían con un finalizador PDE dos veces: si el sistema recibe el mensaje original.  
  
   El código siguiente es un ejemplo del formato de finalizador PDE:  
  
  ```  
  {PDE:[<time><mir>]}  
  where <time><mir> refers to the emission of the previous possible issue  
  ```  
  
- **Finalizador de mensaje demorado (DLM).** El finalizador DLM se agrega a todos los mensajes de salida de usuario a FIN que han superado su período de obsolescencia. Si este finalizador aparece en los mensajes de sistema de GPA o FIN, puede pasar por alto. Este finalizador tiene sólo una etiqueta y ningún valor.  
  
   El período de obsolescencia es como sigue:  
  
  - U = 15 minutos  
  
  - N = 100 minutos  
  
    El código siguiente es un ejemplo del formato de DLM finalizador:  
  
  ```  
  {DLM:}  
  ```  
  
- **Finalizador de mensaje duplicados posibles (PDM).** Se agrega el finalizador PDM por el sistema en cualquier mensaje de salida (GPA y FIN con un identificador de servicio de 01) que se va a reenviar porque una entrega anterior que no sean válida. Si un sistema PLT recibe una solicitud de informe con un finalizador PDM, la respuesta tiene un PDM sin formato (sin la referencia entrega opcional). Puede agregarse otros PDM debido a intentos fallidos de entrega al usuario.  
  
   El código siguiente es un ejemplo del formato de finalizador PDM:  
  
  ```  
  {PDM:[<time><mor>]}  
  where <time> and the Message Output Reference <mor> are that of the previous attempt  
  ```  
  
- **Finalizador de referencia (MRF) del mensaje.** El finalizador MRF especifica la referencia de mensaje del mensaje original de usuario de copia de FIN de MT 096 en mensajes de la entidad Central.  
  
   El código siguiente es un ejemplo del formato MRF finalizador:  
  
  ```  
  {MRF:<date><full-time><mir>}  
  where <mir> is that of the original user message whose fields are copied in the MT 096 FIN  
  Copy to Central Institution Message  
  ```  
  
  > [!NOTE]
  >  El finalizador MRF es específico a FIN copia y se genera automáticamente en la copia de MT 096 FIN al mensaje de entidad Central. Solo puede usar este finalizador en campo 109 de la copia de MT 096 FIN al mensaje de tu institución Central para identificar el 096 MT para que el 097 MT es una respuesta. El formato de la MRF está sujeta a cambios.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)