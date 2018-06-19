---
title: Mejorar el rendimiento del archivado y purga de proceso | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], system performance
- DTA Purge and Archive job, performance
- purging, limitations
- performance, archiving
- performance, purging
- purging, system performance
ms.assetid: d65da58d-65e0-4f6c-8b15-5d4448049b42
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3876021fec4d604960d672671cab8bf4be1dc0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257844"
---
# <a name="improving-the-performance-of-the-archiving-and-purging-process"></a>Mejorar el rendimiento del proceso de archivo y purga
La cantidad de datos almacenados en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos pueden incrementarse muy rápidamente según cómo se haya diseñado el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] escenario, según el número y tamaño de los mensajes procesados por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] escenario y, en función de cómo disponen de configurar el seguimiento. Al mantener el tamaño de la base de datos en un nivel correcto, el procesamiento será más eficaz y la cantidad de datos estará normalizada en cualquier momento. Con ello, se proporciona un rendimiento eficaz y coherente. Al automatizar este proceso, se libera al usuario de la carga del mantenimiento manual de las bases de datos.  
  
## <a name="configuring-a-healthy-environment"></a>Configurar un entorno correcto  
 La estrategia de mantenimiento de un entorno correcto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] depende en gran medida del escenario y del hardware particulares en los que se ejecuta. Los aspectos clave que hay que supervisar son la tasa de crecimiento y el tamaño de la base de datos de seguimiento de BizTalk (BizTalkDTADb). Algunas tablas de la base de datos de seguimiento admiten un gran tamaño de la base de datos, lo que tiene un impacto en el tiempo de ejecución.  
  
 Se puede configurar el mismo escenario para producir cantidades marcadamente distintas de datos de seguimiento en función del número de puntos de seguimiento, de cuántos mensajes diferentes se utilizan, del tamaño de los mensajes y del nivel de seguimiento de partes de mensaje utilizado. A continuación, se presentan varios factores importantes que es preciso supervisar:  
  
-   Número de puntos de seguimiento (como canalizaciones, orquestaciones y puertos)  
  
-   Número de propiedades de mensaje sometidas a seguimiento  
  
-   Número de mensajes por cada mensaje entrante  
  
-   Tamaño del mensaje  
  
-   Tasa de tráfico (promedio y valor máximo)  
  
-   Configuración del seguimiento de partes de mensaje  
  
 Al considerar la purga y archivo automáticos de datos, estime cuántos datos activos necesita mantener en la base de datos de seguimiento. Tendrá que ajustar los parámetros del trabajo DTA Purge and Archive en función de su entorno para que el rendimiento de la purga admita la cantidad de datos activos buscada sin experimentar degradación.  
  
 El trabajo de archivo y purga de DTA puede purgar una cantidad de datos determinada en un intervalo temporal dado. La capacidad del trabajo depende de los escenarios en ejecución, del tamaño actual de la base de datos y del hardware. Para que el sistema alcance la estabilidad, es preciso garantizar un equilibrio entre la purga y la generación de los datos de seguimiento entrantes. En el entorno de prueba, encontrará el equilibrio variando la ventana de actividad de los datos y la frecuencia del trabajo de purga. En un estado de equilibrio, el sistema ofrecerá un rendimiento sostenible. El objetivo es disponer de búfer suficiente antes de que el tamaño de las tablas de la base de datos de seguimiento de BizTalk ocasione problemas de rendimiento constantes y de importancia.  
  
## <a name="performance-limitations"></a>Limitaciones del rendimiento  
 El rendimiento de la purga no se escalará en todos los escenarios. En cualquier escenario, es posible generar una cantidad creciente de datos de seguimiento. Cuando la tasa de purga de datos de seguimiento disminuye de forma constante, tiene lugar un aumento de la base de datos de seguimiento, lo que empeora aún más el rendimiento de la purga.  
  
 En condiciones de carga no sostenible, la copia de los cuerpos de mensaje también puede ralentizarse y es posible que se convierta en un registro en la base de datos de cuadro de mensajes. En condiciones extremas, el seguimiento y copia diarios de cuerpos de mensaje puede tener como resultado archivos en los que el cuerpo de mensaje no se encuentre disponible aunque contenga información de instancia relacionada. Normalmente, los períodos de cargas altas se alternan con períodos de cargas bajas; en estos últimos, el trabajo puede recuperarse.  
  
 El archivo y la purga de la base de datos de seguimiento de BizTalk deberían reducir considerablemente la posibilidad de que se produzcan condiciones de carga no sostenible, gracias a la continua eliminación de la base de datos y a la compactación de los datos de seguimiento almacenados. Estos procesos reducen en gran medida la necesidad de intervención manual.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)