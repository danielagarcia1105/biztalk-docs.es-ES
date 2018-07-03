---
title: Planificación del seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ffc8573-1b4a-47c7-96ab-0471f43facf5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0c45c61efee90b68efc927d88dbcf6429fe13e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973829"
---
# <a name="planning-for-tracking"></a>Planificación del seguimiento
Seguimiento de mensajes es el proceso por el que las partes de una instancia de mensaje, como el cuerpo del mensaje, propiedades del mensaje y los metadatos se almacenan en una base de datos, normalmente para fines de archivado. Posteriormente se pueden ver partes de la instancia de mensaje que se realiza un seguimiento mediante la ejecución de consultas desde la página concentrador de grupo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Además de acceder a los datos archivados, también puede ver los datos en directo, que pueden ser una herramienta útil para identificar y corregir los problemas en un desarrollo o entorno de ensayo.  
  
 Dado que el proceso de seguimiento de mensajes puede ser consume muchos recursos, debe revisar este tema antes de crear el plan.  
  
 Para obtener más información acerca del seguimiento, vea [seguimiento de estado y actividad](http://go.microsoft.com/fwlink/?LinkId=154187) (http://go.microsoft.com/fwlink/?LinkId=154187).  
  
## <a name="configuring-and-enabling-the-dta-purge-and-archive-sql-agent-job"></a>Configurar y habilitar la DTA Purge and Archive el trabajo del Agente SQL  
 Este trabajo archiva y purga los datos antiguos de la base de seguimiento de BizTalk, evitando se vuelvan demasiado grandes. Esto es esencial para un correcto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema. Se iniciará una base de datos de seguimiento grandes afecta al rendimiento del host de seguimiento y de los demás procesos que consultan la base de datos de seguimiento.  
  
-   **Asegúrese de que el trabajo DTA Purge and Archive SQL Agent está completando correctamente, habilitadas y configuradas correctamente.** Este trabajo no está habilitado de forma predeterminada porque primero debe configurarlo para que incluya un directorio donde se pueden escribir los archivos de almacenamiento.  
  
-   **Asegúrese de que el trabajo está capacitado para purgar los datos de seguimiento tan rápido como el seguimiento de los datos entrantes se generaron.** Es aceptable para el trabajo llegue durante las horas pico de carga, pero siempre debe ser capaz de ponerse al día. Si el trabajo de purga se queda atrás y nunca es capaz de ponerse al día, la base de datos de seguimiento de BizTalk continuará creciendo y rendimiento finalmente se verá afectado negativamente.  
  
-   **Revise la purga condicional y purga incondicional parámetros para asegurarse de que mantienen los datos durante el tiempo suficiente, pero no es demasiado largos.** Para obtener más información acerca de estos parámetros, vea [archivar y purgar la base de datos de seguimiento de BizTalk](http://go.microsoft.com/fwlink/?LinkID=153816) (http://go.microsoft.com/fwlink/?LinkID=153816).  
  
-   **Si solo necesita purgar los datos antiguos y necesita archivarla en primer lugar, después, cambiar el código SQL el trabajo del agente para llamar al procedimiento almacenado "dtasp_PurgeTrackingDatabase".** Esto omite el paso archive y simplemente realiza la purga. Para obtener más información acerca de este procedimiento almacenado y cambiar el trabajo del Agente SQL para usarlo, vea [cómo purgar datos de la base de datos de seguimiento de BizTalk](http://go.microsoft.com/fwlink/?LinkID=153817) (http://go.microsoft.com/fwlink/?LinkID=153817).  
  
-   **Si tiene que mantener archivos de almacenamiento de la base de datos de seguimiento de BizTalk, asegúrese de que tiene un proceso en su lugar para restaurar y usarlas correctamente.**  
  
-   **Si experimenta problemas de rendimiento que se tratan momentáneamente mediante la purga de la base de datos de seguimiento de BizTalk, y desea configurar BizTalk para que ya no recopilar información de seguimiento, puede tener en cuenta al desactivar el seguimiento global.** Para obtener información acerca de cómo desactivar el seguimiento global, vea el tema [cómo desactivar el seguimiento Global](http://go.microsoft.com/fwlink/?LinkID=154193) (http://go.microsoft.com/fwlink/?LinkID=154193).  
  
## <a name="creating-a-dedicated-tracking-host"></a>Creación de un Host de seguimiento dedicado  
 Cuando la opción de **Permitir seguimiento de Host** está habilitada para un host en la consola de administración de BizTalk Server, las instancias de ese host se ejecutará el servicio de seguimiento datos descodificar (TDDS) para mover datos de seguimiento desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox base de datos a la base de datos de seguimiento de BizTalk. Puesto que TDDS pueden consumir muchos recursos, considere la posibilidad de crear un host de seguimiento "dedicado" para que la **Permitir seguimiento de Host** está habilitada y que no ejecuta ningún otro [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesos (por ejemplo, adaptadores u orquestaciones). Si el grupo de BizTalk contiene más de un servidor de BizTalk, también se considera una práctica recomendada para crear una instancia de este host en cada servidor en el grupo para proporcionar alta disponibilidad de TDDS.  
  
## <a name="testing-to-measure-maximum-sustainable-tracking-throughput"></a>Las pruebas para medir el rendimiento de seguimiento sostenible máximo  
 Un mensaje extenso seguimiento es una actividad de uso intensivo de muchos recursos y si no se administra correctamente puede tener un efecto muy negativo en el rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Por lo tanto, debe medir el rendimiento de seguimiento sostenible máximo para su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno para asegurarse de que el sistema es sostenible y se ejecutará indefinidamente con una tasa de flujo de mensaje dado. Para obtener más información sobre cómo medir el rendimiento de seguimiento sostenible máximo, consulte [medir el rendimiento máximo sostenible seguimiento](http://go.microsoft.com/fwlink/?LinkID=153815) (<http://go.microsoft.com/fwlink/?LinkID=153815>).  
  
##  <a name="BKMK_TrackingBP"></a> Procedimientos recomendados para el seguimiento  
  
- **Determinar la información que necesita para realizar un seguimiento durante la planeación** : debe decidir durante la planificación de las etapas de la información que necesita para realizar el seguimiento, por lo que después de implementar el proyecto puede establecer las opciones de seguimiento y limitar la cantidad de datos a Asigne sólo la información que necesita.  
  
- **No realizar seguimiento de todos los mensajes**: se recomienda realizar un seguimiento no todos los mensajes, porque cada vez que se toca un mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea otra copia. En su lugar, puede restringir el ámbito mediante el seguimiento solo a un puerto específico. Esto ayuda a maximizar el rendimiento del sistema y a mantener despejado las bases de datos.  
  
- **Establecer el seguimiento en los puertos de envío y puertos en lugar de en una canalización de recepción**: si configura las opciones de seguimiento de canalizaciones, también establecerá las opciones de seguimiento globalmente para todos los puertos que usa la canalización. Esto puede producir a su vez en muchos más datos de seguimiento que desea, lo que ralentizan el rendimiento del sistema. En su lugar, puede establecer las opciones de seguimiento en el envío de puertos y los puertos de recepción.  
  
- **Tenga en cuenta varios factores cuando el tamaño de la base de datos de seguimiento de BizTalk**:  
  
  -   Al cambiar el tamaño de la base de datos de seguimiento de BizTalk, cuenta los factores de SQL Server, como el tamaño del índice, agregando un multiplicador de contingencia para los cálculos.  
  
  -   Al determinar el tamaño de los mensajes en la base de datos de seguimiento de BizTalk, agregue el tamaño promedio del contexto del mensaje para el tamaño del mensaje si resulta significativo en comparación con el tamaño del mensaje.  
  
  -   Para limitar el tamaño de los mensajes en la base de datos de seguimiento de BizTalk, limite el número de propiedades que promueva. Debe únicas propiedades promocionada de uso si necesita para fines de enrutamiento, en caso contrario, utilice los campos distintivos.  
  
  -   Si la orquestación **forma Inicio y finalización** está habilitada, tenga en cuenta que un evento de inicio y detención para cada forma en cada instancia de orquestación se guarda en la base de datos de seguimiento de BizTalk.