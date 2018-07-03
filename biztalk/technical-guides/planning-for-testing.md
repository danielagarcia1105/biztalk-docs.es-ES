---
title: Plan de pruebas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca2f5f29-9eea-4f4d-9781-75c231db4605
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b386ee074538af7960ca39bfb50c25ac59df1dbb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010285"
---
# <a name="planning-for-testing"></a>Plan de pruebas
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las pruebas pueden dividirse en varias categorías, incluidas las pruebas unitarias, pruebas funcionales, pruebas de carga y pruebas de disponibilidad. Este tema describe la unidad y las pruebas de carga y cómo planear cada uno.  
  
## <a name="planning-for-unit-testing"></a>Planeación de pruebas unitarias  
 Prueba unitaria es un procedimiento que se usa para validar que las unidades individuales de código está trabajando según lo previsto. ¿Las pruebas unitarias pueden considerarse como "break-fix" pruebas: el software lleva a cabo la funcionalidad deseada en diferentes condiciones y puede el software controlar los errores que se producen en estas condiciones?  
  
 Dado que las pruebas unitarias se suele realizar en componentes individuales, el banco de pruebas asociado no necesita las capacidades de procesamiento de un entorno de producción real. Por este motivo, considere la posibilidad de realizar pruebas unitarias en un entorno de Virtual Server, lo que requiere mucho menos recursos de hardware.  
  
 Otro aspecto de las pruebas unitarias que se puede realizar en un entorno virtualizado de ensayo. Almacenamiento provisional es el proceso de la implementación real de una solución de BizTalk de pruebas unitarias. Para maximizar los recursos de hardware disponible, considere el uso de Virtual Server para su entorno de ensayo.  
  
 Para obtener más información sobre el uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno virtual, consulte [utilizando Virtual Server durante el proceso de administración de versión](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ). Para obtener información acerca de las herramientas que pueden ser útiles para una solución de BizTalk de pruebas unitarias, vea [herramientas para pruebas](~/technical-guides/tools-for-testing.md). Encontrará una lista de comprobación de las consideraciones para realizar las pruebas unitarias [realizar pruebas unitarias](../technical-guides/performing-unit-testing.md).  
  
## <a name="planning-for-load-testing"></a>Plan de pruebas de carga  
 Las pruebas de carga son el proceso de medir el rendimiento máximo sostenible y máxima sostenible seguimiento del rendimiento de una solución de BizTalk y, a continuación, quitar los cuellos de botella que impiden el rendimiento de la solución. Para obtener más información acerca de la carga de prueba y quitar cuellos de botella de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solución, consulte el [Guía de rendimiento de BizTalk Server 2009](http://go.microsoft.com/fwlink/?LinkID=150492) (<http://go.microsoft.com/fwlink/?LinkID=150492>).  
  
 Para obtener información acerca de las herramientas que pueden ser útiles para una solución de BizTalk de la prueba de carga, consulte [herramientas para pruebas](~/technical-guides/tools-for-testing.md). Encontrará una lista de comprobación de las consideraciones para las pruebas de carga [realizar la carga y pruebas de rendimiento](../technical-guides/performing-load-and-throughput-testing.md).  
  
## <a name="plan-to-test-for-the-lifetime-of-the-solution"></a>Plan para la prueba durante la vigencia de la solución  
 Mientras que las pruebas unitarias y pruebas de carga son especialmente importantes durante las primeras fases de la solución, plan de pruebas periódicas durante la vigencia de la solución para detectar posibles problemas que pueden producirse como aumenta la carga o como nuevas funcionalidades o componentes se agregan a la solución.  
  
## <a name="see-also"></a>Vea también  
 [Planificación del nivel de servidor BizTalk Server](../technical-guides/planning-the-biztalk-server-tier.md)   
 [Lista de comprobación: probar la preparación operativa](../technical-guides/checklist-testing-operational-readiness.md)