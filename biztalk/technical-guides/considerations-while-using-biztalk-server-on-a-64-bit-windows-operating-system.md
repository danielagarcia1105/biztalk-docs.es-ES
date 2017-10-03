---
title: Consideraciones al usar BizTalk Server en un sistema operativo Windows de 64 bits | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac630f55-7ebe-4b93-bf98-70b00788520f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71287d29d13406d3f1159054e988ef0e2b98a648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system"></a>Consideraciones al usar BizTalk Server en un sistema operativo Windows de 64 bits
Al utilizar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un sistema operativo de Windows de 64 bits, asegúrese de que tenga en cuenta los problemas descritos en este tema. Para con frecuencia más frecuentes preguntas relacionadas con la compatibilidad con 64 bits para Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], consulte [compatibilidad con BizTalk Server de 64 bits](http://go.microsoft.com/fwlink/?LinkID=155306) (http://go.microsoft.com/fwlink/?LinkID=155306).  
  
## <a name="modify-the-process-memory-usage-throttling-threshold"></a>Modificar el umbral de limitación del uso de memoria de proceso  
 De forma predeterminada, el **uso de memoria del proceso** umbral de limitación de host se establece en 25. Si se supera este valor y el uso de memoria de proceso de BizTalk es de más de 300 MB, puede producirse una condición de limitación. En un servidor de 64 bits, puede aumentar este valor en 100. Esto permite más consumo de memoria por el proceso de BizTalk antes de que se produce una limitación. Para obtener instrucciones sobre cómo modificar el host de uso de memoria de proceso umbral de limitación, consulte [cómo modificar la configuración predeterminada de limitación de Host](http://go.microsoft.com/fwlink/?LinkId=157210) (http://go.microsoft.com/fwlink/?LinkId=157210).  
  
> [!NOTE]  
>  La memoria de proceso máxima disponible está limitada por el tamaño del espacio de una dirección de 2 GB para los fines de este cálculo, aunque el sistema tenga más de 2 GB de memoria física. En los sistemas de 32 bits y de 64 bits, se usa un límite superior a la memoria de proceso de 2 GB para los fines de este cálculo. Para evitar errores de memoria insuficiente, se recomienda que no se especifica un valor que le permitirá host memoria de instancia para superar 1,54 GB cuando se ejecuta una versión de 32 bits de BizTalk Server, independientemente de si el servidor BizTalk Server está instalado en un de 32 bits o 64 bits funciona sy provenir. Por ejemplo, si especifica un valor de 1 a 100 para que este parámetro inicie la limitación en función del porcentaje de memoria de proceso usada, no indique un valor mayor de 75 (0,75 * 2 GB = 1,54 GB). Si especifica un valor mayor que 100 para este parámetro inicie la limitación en función del número especificado en MB, no escriba un valor mayor que 1536.If está ejecutando una versión de 64 bits de BizTalk Server, especifique un valor o 100 (100%) o 2048 (2GB) para iniciar  limitación cuando se usa la memoria de proceso máxima disponible de 2 GB.  
  
## <a name="adapters-that-do-not-support-64-bit-hosts"></a>Adaptadores que son compatibles con Hosts de 64 bits  
 No se admiten los siguientes adaptadores para ejecutarse en instancias de host de 64 bits:  
  
-   Adaptador de FTP  
  
-   Adaptador de POP3  
  
 Asegúrese de que ejecutar estos adaptadores en una instancia de host de 32 bits.  
  
## <a name="configure-the-mimesmime-encoder-to-run-in-32-bit-mode"></a>Configurar el codificador MIME/SMIME para ejecutarse en modo de 32 bits  
 En [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], el agote de componente de canalización de codificador MIME/SMIME no tiene compatibilidad nativa de 64 bits. Esto significa que el componente debe ejecutarse como un proceso en modo de emulación de 32 bits (WOW64). Por lo tanto, la instancia de host en la que se ejecuta este componente de codificador (o la canalización de envío de la que forma parte) debe funcionar en modo de emulación de 32 bits. Tenga en cuenta las implicaciones de rendimiento (entre otras) de esta restricción para otros elementos de BizTalk que se ejecuten en la misma instancia de host.