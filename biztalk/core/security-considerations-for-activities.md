---
title: Consideraciones de seguridad para las actividades | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fc49afd-a1c3-4ac7-8b89-11be667221e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bca070662feb0731abb5adbf2147a2e24b5a6e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974117"
---
# <a name="security-considerations-for-activities"></a>Consideraciones de seguridad para las actividades
Las funciones de seguridad que usa al interceptar el adaptador de WCF son las mismas que las usadas para las demás soluciones de BAM. Las consideraciones adicionales para la interceptación del adaptador de WCF conllevan la selección del usuario correcto y de qué función de escritor de eventos usar.  
  
 Al usar los servicios WCF y el adaptador de WCF, la función seleccionada escribe todos los datos relacionados con BAM en la base de datos de importación principal de BAM.  
  
 Puede seleccionar la configuración de función de usuario adecuada evaluando su escenario de solución:  
  
- Si su solución requiere muchos servicios nuevos de los que muy diversas actividades realizan un seguimiento, y todos se ejecutan bajo la misma cuenta de usuario, se recomienda usar la superfunción BAM_EVENT_WRITER para escribir los eventos interceptados.  
  
  > [!NOTE]
  >  Los usuarios deben agregarse a la superfunción de escritor de eventos de BAM. Al agregar un usuario a la superfunción, es importante recordar que este usuario podrá escribir en todas las actividades del sistema.  
  
- Si su solución requiere un mayor control de los eventos escritos, deberá usar las funciones específicas de las actividades.  
  
  > [!NOTE]
  >  Los usuarios deben agregarse a la función de escritor de eventos específica de la actividad en concreto.  
  
  Para obtener más información acerca de cómo configurar los roles de sistema de escritura de eventos BAM, consulte [cómo determinar y establecer Roles de escritor de eventos para las actividades](../core/how-to-determine-and-set-event-writer-roles-for-activities.md).  
  
> [!IMPORTANT]
>  Debe ser miembro del grupo Usuarios de la aplicación de BizTalk.  
  
 Al seleccionar qué cuenta de usuario usar en la configuración del interceptor de WCF de BAM para la seguridad para la suplantación de IIS, debe tener en cuenta los siguientes escenarios:  
  
- Autohospedado: Un ejecutable que se ejecute en el equipo que alberga el servicio WCF abierto.  
  
- Adaptador de WCF: soluciones creadas con el **Asistente de publicación de servicio de WCF de Biztalk**.  
  
- Alojado en IIS: una solución hospedada en una aplicación de IIS mediante un servicio WCF.  
  
  Use la siguiente tabla para facilitar la identificación de qué cuenta usar:  
  
|Tipo de solución|Cuenta que usar|  
|-------------------|--------------------|  
|Con alojamiento propio|La cuenta que se usa para ejecutar el ejecutable que contendrá el servicio abierto.|  
|Adaptador de WCF|Use la identidad AppPool: este es el grupo de aplicaciones asociado con el Vroot que aloja la ubicación de recepción. Esta identidad se crea automáticamente cuando se usa el **Asistente de publicación de servicio de WCF de BizTalk** para publicar el sitio. Puede considerar esto como un caso especial de la solución alojada en IIS.|  
|Alojado en IIS|La identidad del usuario AppPool que ejecuta la aplicación o VRoot del Servicio WCF.|  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones de seguridad para los interceptores de BAM](../core/security-considerations-for-bam-interceptors.md)