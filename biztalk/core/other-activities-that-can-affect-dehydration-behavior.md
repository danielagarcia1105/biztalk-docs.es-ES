---
title: Otras actividades que pueden afectar al comportamiento de deshidratación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed940448-d3b1-4308-9b38-887904e03bd0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4622c77876607664b210de2581929154973b45d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264044"
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a>Otras actividades que pueden afectar al comportamiento de deshidratación
Las siguientes actividades afectan de forma directa o indirecta a la deshidratación y al rendimiento general; por tanto, deben tenerse en cuenta en cualquier escenario de pruebas.  
  
-   **Consultas de la consola de administración de BizTalk Server.** Estas consultas consumen recursos y afectan al rendimiento global en función del tipo y la frecuencia de la consulta.  
  
-   **Copia de seguridad, archivado y purga las actividades.** Estas actividades también consumen recursos y deben tenerse en cuenta en cualquier escenario de prueba.  
  
-   **Combinación de hosts de 32 bits y 64 bits.** Hay algunas cuestiones que deben tenerse en cuenta cuando se usa una combinación de hosts de 32 bits y 64 bits:  
  
    -   Procedimos a medir la memoria virtual y física consumida en condiciones de sobrecarga y, a continuación, comparamos los resultados con determinados umbrales. En los sistemas de 64 bits, el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa más memoria y, por tanto, habrá una diferencia en la directiva de deshidratación con respecto a los sistemas de 32 bits que empleen el mismo sistema y los mismos valores predeterminados. Asegúrese de separar los hosts de orquestación, recepción, envío y cuadro de mensajes.  
  
         No se ha encontrado ninguna diferencia obvia al usar los umbrales predeterminados de 32 bits en los sistemas de 64 bits cuando el host de orquestación se encuentra en el cuadro de 64 bits. Sin embargo, en condiciones de sobrecarga, **MemoryThrottlingCriteria** configuración debe estar como mínimo duplicar o triplicar (siempre y cuando tenga suficiente memoria), pero el escenario debe optimizarse para maximizar el rendimiento porque hay muchos factores que entran en juego. Ajuste los umbrales de deshidratación en condiciones de sobrecarga para hallar los valores óptimos.  
  
    -   El comportamiento de deshidratación depende del historial de tiempo de entrega de cada una de las suscripciones; tenga en cuenta que los historiales pueden ser distintos de una a otra suscripción al ajustar los valores de las propiedades de deshidratación.  
  
    -   Cuando el servicio del host de orquestación se recicle en un host, pero no en otro, los historiales serán diferentes.  
  
    -   Cuando los servidores usan diferentes versiones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], habrá una diferencia en la directiva de deshidratación entre los dos.  
  
## <a name="see-also"></a>Vea también  
 [Archivo BTSNTSvc.exe.config](../core/btsntsvc-exe-config-file.md)