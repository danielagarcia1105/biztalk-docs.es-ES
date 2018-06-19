---
title: Supervisión de la actividad de negocio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83b3c92f-3062-413e-8d89-797f1c7ea7ab
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9003c89f7e1e3491ff343078936a9f22e6a41ef1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232732"
---
# <a name="business-activity-monitoring"></a>Supervisión de la actividad económica
Los trabajadores de la información necesitan cierta flexibilidad a la hora de observar y evaluar los procesos empresariales. Por ejemplo, es posible que un administrador de pedidos necesite saber cuántos pedidos se han aprobado y denegado cada día y que un administrador de ventas desee obtener una actualización cada hora de los productos que se han pedido. Para poder satisfacer necesidades tan dispares se necesita un marco de trabajo general que efectúe un seguimiento de lo que ocurre en un proceso empresarial determinado. Esto es exactamente lo que ofrece el componente de Supervisión de la actividad económica (SAE) de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 ![Diagrama de BAM](../core/media/bam-diagram.gif "bam_diagram")  
  
 Como indica la ilustración anterior, el componente de SAE permite la supervisión de los sucesos y los datos que se producen en una aplicación de BizTalk. El acceso a esta información, que puede efectuarse de distintas formas, es posible gracias a los servicios Web conocidos como SOAP. Las formas de acceso son las siguientes:  
  
-   A través de Microsoft Excel u otros clientes de escritorio, como, por ejemplo, una aplicación de escritorio personalizada.  
  
-   Mediante el portal de BAM, un componente de BizTalk Server que permite que los usuarios empresariales analicen y configuren información de BAM. Gracias al portal de SAE, los trabajadores de la información pueden seleccionar una instancia concreta de un proceso empresarial y, a continuación, elegir una vista de SAE específica en el proceso. Cada una de estas vistas ofrece una perspectiva distinta, como, por ejemplo, una representación gráfica de las tendencias de ventas por productos, de los niveles de inventario actuales o de otros indicadores clave de rendimiento. La información de estas vistas se puede actualizar cada día, cada hora o con mayor frecuencia. Por medio del portal de SAE, los trabajadores de la información también pueden definir agregaciones de datos como, por ejemplo, el número de pedidos completados, cancelados o en curso durante la última hora. El portal de SAE también puede alojarse como un sitio Web dentro de Windows SharePoint Services si se especifica como un conjunto de páginas de ASP.NET.  
  
-   A través de los Servicios de notificación de SQL Server, lo que hace posible entregar la información de SAE en forma de notificación. Mientras que las dos primeras opciones permiten que los trabajadores de la información analicen la información de SAE, esta tercera opción crea una notificación cuando ocurre algo interesante. Gracias al administrador de alertas del portal de SAE, los trabajadores de la información pueden definir alertas para cuando se produzcan determinados sucesos. Por ejemplo, es posible que un usuario de BAM desee enviar un mensaje de correo electrónico a un administrador determinado siempre que el número de pedidos cancelados sea superior a diez, o que desee informar a ciertos vendedores asociados cuando reciba un pedido de su mayor cliente.  
  
 Estrictamente hablando, cada vista de SAE está basada en una o varias actividades de SAE. Una actividad de SAE representa un proceso empresarial específico, como la administración de pedidos o el envío de un producto, y cada una de ellas tiene un conjunto definido de hitos y datos económicos. Por ejemplo, una actividad de pedido puede disponer de hitos como Aprobado, Denegado y Entregado, junto con datos económicos como Nombre de cliente y Producto.  
  
 Para aquellos trabajadores de la información que obtienen acceso a BAM a través de Excel, las actividades de BAM y las vistas de BAM se pueden crear como un complemento de Excel. El Asistente para actividad de BAM de este complemento permite definir actividades, mientras el Asistente para vistas de BAM permite definir vistas en función de esas actividades. De hecho, el Asistente para vistas de SAE sólo ayuda a un trabajador de la información a generar una tabla dinámica de Excel con la información incluida en una o varias actividades de SAE. La información que la vista ofrece puede mostrarse directamente en Excel, tal y como se expresa en la ilustración siguiente.  
  
 ![](../core/media/understandingbts-12-bam2.gif "UnderstandingBTS_12_BAM2")  
  
 En este sencillo ejemplo, dos gráficos de Excel muestran información sobre las ventas y el progreso del pedido. Una vista de SAE puede ser más compleja, y el autor puede restringir a los usuarios que desee el acceso a los datos de la vista. Por ejemplo, es posible que un administrador de pedidos tenga acceso a elementos de la vista del proceso de pedido que están ocultos para los empleados.  
  
 Así, mientras que los trabajadores de la información pueden crear sus propias vistas y actividades de SAE, estas vistas y actividades van a depender de la información que proporcionen las orquestaciones que los trabajadores supervisan. Por consiguiente, la función de los trabajadores aún no ha terminado. Por medio de una herramienta denominada Editor de perfiles de seguimiento (TPE), los programadores deben configurar una orquestación para que proporcione la información que una actividad de SAE determinada necesita y, con ella, las vistas de SAE dependientes. Esta herramienta permite que los programadores asocien gráficamente los sucesos y campos de mensaje adecuados de una orquestación con los hitos y los datos económicos correspondientes de la actividad de SAE. A continuación, como queda reflejado en la ilustración anterior, el motor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía los valores de estos eventos y campos de mensajes a la base de datos de seguimiento, desde donde se podrá obtener acceso a ellos por medio del componente de BAM. No obstante, aunque los programadores deban cumplir una función en este aspecto, no tienen que hacerse cargo de las actividades y las vistas de SAE; la creación, el mantenimiento y la utilización de estos servicios de tipo empresarial son una tarea específica de los trabajadores de la información.  
  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el TPE también sirve para especificar la forma en la que las canalizaciones generan eventos. Y lo que es más importante; ahora SAE puede aceptar y mostrar los sucesos generados por códigos de usuario, independientemente de que se hayan creado como una orquestación o no. Cualquier aplicación generada con .NET Framework podría supervisarse con el componente de BAM de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Tecnologías de trabajador de información](../core/information-worker-technologies.md)