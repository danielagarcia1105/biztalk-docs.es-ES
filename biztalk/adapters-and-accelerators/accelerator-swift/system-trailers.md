---
title: Finalizadores de sistema | Documentos de Microsoft
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
ms.openlocfilehash: a0a8c5b7be12a90aa2d31e828298cf7b95834036
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214084"
---
# <a name="system-trailers"></a>Finalizadores de sistema
Finalizadores de sistema transmiten los detalles adicionales o especiales sobre el mensaje SWIFT. Si cualquiera de los finalizadores de tres sistema primera están presentes, se producen en el siguiente orden. Los finalizadores de sistema restantes pueden aparecer en cualquier orden.  
  
|Código de finalizador|Nombre|  
|------------------|----------|  
|**DISTRIB**|Suma de comprobación|  
|**SYS**|Mensaje que originó sistema|  
|**TNG**|Aprendizaje|  
|**PDM**|Posibles mensajes duplicados|  
|**DLM**|Mensajes retrasada|  
|**MRF**|Referencia de mensajes|  
  
-   **Sistema que originó finalizador de mensaje (SYS).** El mensaje del sistema o un mensaje de servicio, generada por un sistema PLT, tiene un finalizador SYS. Todos los solicitado mensajes del sistema con un identificador de servicio de 01, contengan el MIR de la solicitud y el tiempo.  
  
     El código siguiente es un ejemplo del formato de finalizador SYS:  
  
    ```  
    {SYS:[<time><mir>]}  
    ```  
  
-   **Prueba y entrenamiento finalizador de mensaje (TNG).** El finalizador TNG es obligatorio para mensajes FINÉS y GPA (con un identificador de servicio de 01) enviado por o entregados a una prueba y entrenamiento lógico Terminal (IL). Este finalizador tiene sólo una etiqueta y ningún valor.  
  
     El código siguiente es un ejemplo del formato de finalizador TNG:  
  
    ```  
    {TNG:}  
    ```  
  
-   **Finalizador de emisión duplicados posibles (PDE).** El destino del mensaje usa el finalizador PDE. Solo se aplica a los mensajes de usuario a otro de FINÉS (con un identificador de servicio de 01) y categorías de mensaje reservados para banca mensajes. El sistema puede contener varios PDEs. El sistema no comprueba el orden ni restringir el número (excepto para la longitud máxima de mensajes).  
  
     El sistema acepta con el formato correcto finalizadores PDE aplicados a los mensajes de sistema de usuario, pero no procesarlos. Esto significa que el sistema no realiza una comprobación para ver si existe el mensaje original. Por lo tanto, el sistema puede procesar una solicitud de recuperación que se envía con un finalizador PDE dos veces: si el sistema recibe el mensaje original.  
  
     El código siguiente es un ejemplo del formato de finalizador PDE:  
  
    ```  
    {PDE:[<time><mir>]}  
    where <time><mir> refers to the emission of the previous possible issue  
    ```  
  
-   **Finalizador de mensaje diferida (DLM).** El finalizador DLM se agrega a todos los mensajes de salida de usuario a otro FIN que han superado el período de obsolescencia. Si aparece este finalizador en GPA o FINÉS mensajes del sistema, puede pasar por alto. Este finalizador tiene sólo una etiqueta y ningún valor.  
  
     El período de obsolescencia es como sigue:  
  
    -   U = 15 minutos  
  
    -   N = 100 minutos  
  
     El código siguiente es un ejemplo del formato de finalizador DLM:  
  
    ```  
    {DLM:}  
    ```  
  
-   **Finalizador de mensaje duplicados posibles (PDM).** El sistema agrega el finalizador PDM a cualquier mensaje de salida (GPA y FINÉS con un identificador de servicio de 01) que se va a reenviar porque una entrega anterior puede no ser válida. Si un sistema PLT recibe una solicitud de informe con un finalizador PDM, la respuesta tiene un PDM sin formato (sin la referencia de entrega opcional). Se pueden agregar otros PDMs debido a intentos fallidos de entrega al usuario.  
  
     El código siguiente es un ejemplo del formato de finalizador PDM:  
  
    ```  
    {PDM:[<time><mor>]}  
    where <time> and the Message Output Reference <mor> are that of the previous attempt  
    ```  
  
-   **Finalizador de referencia (MRF) del mensaje.** El finalizador MRF especifica la referencia de mensaje del mensaje de usuario original en la copia de FIN de 096 MT para mensajes de entidad Central.  
  
     El código siguiente es un ejemplo del formato de finalizador MRF:  
  
    ```  
    {MRF:<date><full-time><mir>}  
    where <mir> is that of the original user message whose fields are copied in the MT 096 FIN  
    Copy to Central Institution Message  
    ```  
  
    > [!NOTE]
    >  El finalizador MRF es específico a FIN copia y se genera automáticamente en la copia MT 096 FINÉS mensajes entidad Central. Sólo se puede utilizar este finalizador en campo 109 de la copia de FINÉS 096 MT para mensajes de entidad Central para identificar el 096 MT a la que el 097 MT es una respuesta. El formato de la MRF está sujeta a cambios.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)