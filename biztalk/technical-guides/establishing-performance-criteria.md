---
title: Establecer los criterios de rendimiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 181011d1-aa74-43fe-b05a-30b043956d70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5317445a5cf7e1e0b3fc07ab6ac301c764501460
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="establishing-performance-criteria"></a>Establecer los criterios de rendimiento
Los objetivos de rendimiento de una solución de BizTalk Server normalmente se dividen en dos categorías, rendimiento o latencia. Este tema describe los factores que deben tenerse en cuenta al evaluar el rendimiento o latencia de una solución de BizTalk Server.  
  
> [!NOTE]  
>  Optimizar el rendimiento o la latencia de una solución de BizTalk Server a menudo representa objetivos en conflicto. Por ejemplo, se podría mejorar el rendimiento del archivo de adaptador de recepción mediante el aumento del tamaño del lote, pero si lo hace podría reducir la latencia. En este escenario, el adaptador tarda más tiempo en acumular mensajes para un tamaño de lote mayor, que a su vez reducirán la latencia de extremo a extremo para un mensaje determinado.  
  
## <a name="factors-affecting-throughput-of-a-biztalk-server-solution"></a>Factores que afectan al rendimiento de una solución de BizTalk Server  
 **Rendimiento**: ampliamente medido como el número de documentos que puede procesar una solución de BizTalk Server dentro de un intervalo de tiempo determinado.  
  
 Factores que afectan al rendimiento son:  
  
-   **Tamaño de mensaje** : mensajes más grandes utilizan más sobrecarga que los mensajes más pequeños, especialmente si los mensajes se transforman con una asignación y son lo suficientemente grandes como para que se almacenan en búfer en el sistema de archivos durante la operación de asignación. Para obtener más información acerca de cómo tamaño del mensaje afecta al rendimiento de BizTalk Server, vea [cómo BizTalk Server procesa grandes mensajes](http://go.microsoft.com/fwlink/?LinkId=139293) (http://go.microsoft.com/fwlink/?LinkId=139293).  
  
-   **Formato de mensaje** -mensajes se reciben en BizTalk Server en uno de dos formatos principales, archivos XML o archivos sin formato. Porque los archivos sin formato deben convertirse en el formato XML para ser procesados por el motor de mensajería de BizTalk, una sobrecarga adicional que por el procesamiento de archivos planos.  
  
-   **Requisitos del adaptador** – diferentes adaptadores suelen incluir capacidades de rendimiento diferentes. Por ejemplo, los adaptadores que requieren compatibilidad con transacciones de MSDTC incurrirán adicionales y reduce la carga de rendimiento en comparación con un adaptador que no utiliza transacciones de MSDTC. Adaptadores utilizados por la solución de BizTalk varían dependiendo de los requisitos y necesidades empresariales internos de su socio comercial.  
  
-   **Requisitos de procesamiento de orquestación** : orquestaciones ofrecen una gran flexibilidad para encapsular y aplicar los procesos empresariales a los mensajes recibidos por BizTalk. Al mismo tiempo, las orquestaciones consumen sobrecarga, lo que debe tenerse en cuenta al calcular el rendimiento de una solución de BizTalk Server.  
  
-   **Requisitos de carga máxima** – más procesamiento de documentos no necesariamente se producen de forma ordenada medida. Por ejemplo, una solución de BizTalk Server puede admitir un gran porcentaje de su carga de procesamiento al final de un día laborable. Por lo tanto, requisitos de carga máxima y el rendimiento sostenible máximo (MST) de una solución de BizTalk Server deben tener en cuenta al establecer los criterios de rendimiento. Para obtener más información acerca de cómo medir el MST de una solución de BizTalk Server, vea [medir el rendimiento máximo sostenible motor](http://go.microsoft.com/fwlink/?LinkID=154388) (http://go.Microsoft.com/fwlink/?) LinkID = 154388) y [medir el rendimiento de seguimiento sostenible máximo](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.Microsoft.com/fwlink/?) LinkID = 153815).  
  
-   **Requisitos de seguimiento de documentos** : seguimiento de documentos impone una sobrecarga adicional en el sistema. Requisitos de seguimiento de documentos deben ser una consideración principal al calcular los objetivos de rendimiento de una solución de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Metodología de pruebas de rendimiento de servidor BizTalk Server](../technical-guides/biztalk-server-performance-testing-methodology.md)