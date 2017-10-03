---
title: "Planeación de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ffc8573-1b4a-47c7-96ab-0471f43facf5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9853fccde9c5fa6e8c223106c8386f19298d0b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-tracking"></a>Planeación de seguimiento
Seguimiento de mensajes es el proceso por el que partes de una instancia de mensaje, como el cuerpo del mensaje, propiedades del mensaje y metadatos se almacenan en una base de datos, normalmente para archivarlo. Partes de la instancia de mensaje que se realiza un seguimiento posteriormente pueden verse mediante la ejecución de consultas desde la página concentrador de grupo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Además de tener acceso a los datos archivados, también puede ver datos en directo, que pueden ser una herramienta útil para identificar y solucionar problemas en el desarrollo de un entorno de ensayo.  
  
 Puesto que el proceso de seguimiento de mensajes puede ser precisa muchos recursos, debe revisar este tema antes de crear el plan.  
  
 Para obtener más información acerca del seguimiento, vea [seguimiento de estado y actividad](http://go.microsoft.com/fwlink/?LinkId=154187) (http://go.microsoft.com/fwlink/?LinkId=154187).  
  
## <a name="configuring-and-enabling-the-dta-purge-and-archive-sql-agent-job"></a>Configurar y habilitar la DTA purgar y archivar el trabajo del Agente SQL  
 Este trabajo archiva y purga los datos antiguos de la base de seguimiento de BizTalk, así se mantienen no sean demasiado grandes. Esto es esencial para un correcto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema. Una base de datos de seguimiento grandes empezarán a afectar al rendimiento del host de seguimiento y los demás procesos que consulta la base de datos de seguimiento.  
  
-   **Asegúrese de que el trabajo DTA Purge and Archive SQL Agent está correctamente configurado, habilitado y se completan correctamente.** Este trabajo no está habilitado de forma predeterminada porque primero debe configurarlo para que incluya un directorio donde se pueden escribir los archivos de almacenamiento.  
  
-   **Asegúrese de que el trabajo está capacitado para purgar los datos de seguimiento de velocidad a la que se generan el seguimiento de los datos entrantes.** Es aceptable para el trabajo obtener durante las horas pico de carga, pero siempre debe ser capaz de ponerse al día. Si el trabajo de purga se queda atrás y nunca es capaz de ponerse al día, la base de datos de seguimiento de BizTalk continuará creciendo y rendimiento finalmente se verá afectado negativamente.  
  
-   **Revise la purga condicional y purga incondicional parámetros para asegurarse de mantiene datos durante el tiempo suficiente pero no demasiado largos.** Para obtener más información acerca de estos parámetros, consulte [archivar y purgar la base de datos de seguimiento de BizTalk](http://go.microsoft.com/fwlink/?LinkID=153816) (http://go.microsoft.com/fwlink/?LinkID=153816).  
  
-   **Si solo necesita purgar los datos antiguos y no necesita archivarla en primer lugar y, después, cambiar el código SQL el trabajo del agente para llamar al procedimiento almacenado "dtasp_PurgeTrackingDatabase".** Esto omite el paso de archivo y solo realiza la purga. Para obtener más información acerca de este procedimiento almacenado y cambiar el trabajo del Agente SQL para utilizarla, vea [cómo purgar datos desde la base de datos de seguimiento de BizTalk](http://go.microsoft.com/fwlink/?LinkID=153817) (http://go.microsoft.com/fwlink/?LinkID=153817).  
  
-   **Si necesita mantener archivos de almacenamiento de la base de datos de seguimiento de BizTalk, asegúrese de que tiene un proceso en su lugar para restaurar y utilizarlos correctamente.**  
  
-   **Si tiene problemas de rendimiento que se tratan en breve mediante la purga de la base de datos de seguimiento de BizTalk y desea configurar BizTalk para que ya no recopilar información de seguimiento, puede que desee tener en cuenta al desactivar el seguimiento global.** Para obtener información acerca de cómo desactivar el seguimiento global, vea el tema [cómo desactivar el seguimiento Global](http://go.microsoft.com/fwlink/?LinkID=154193) (http://go.microsoft.com/fwlink/?LinkID=154193).  
  
## <a name="creating-a-dedicated-tracking-host"></a>Crear un Host de seguimiento dedicado  
 Cuando la opción de **Permitir seguimiento de Host** está habilitada para un host en la consola de administración de BizTalk Server, instancias de ese host se ejecutará el servicio de seguimiento datos descodificar (TDDS) para mover datos de seguimiento desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuadro de mensajes base de datos a la base de datos de seguimiento de BizTalk. Puesto que TDDS pueden consumir muchos recursos, considere la posibilidad de crear un host de seguimiento "dedicado" para que la **Permitir seguimiento de Host** opción está habilitada y que no ejecuta ningún otro [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesos (por ejemplo, adaptadores u orquestaciones). Si el grupo de BizTalk contiene más de un servidor de BizTalk, también se considera una práctica recomendada para crear una instancia de este host en cada servidor en el grupo para proporcionar alta disponibilidad de TDDS.  
  
## <a name="testing-to-measure-maximum-sustainable-tracking-throughput"></a>Pruebas para medir el rendimiento de seguimiento sostenible máximo  
 Mensaje extenso de seguimiento es una actividad de uso intensivo de muchos recursos y si no se administra correctamente puede tener un efecto muy adverso en el rendimiento de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Por lo tanto, se debería medir el rendimiento de seguimiento sostenible máximo para su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno para asegurarse de que el sistema es sostenible y se ejecutará indefinidamente a una velocidad de flujo de mensaje determinado. Para obtener más información acerca de cómo medir el rendimiento de seguimiento sostenible máximo, consulte [medir el rendimiento máximo sostenible de seguimiento](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).  
  
##  <a name="BKMK_TrackingBP"></a>Prácticas recomendadas para seguimiento  
  
-   **Determinar la información que necesita para realizar un seguimiento durante la planeación** : debería decidir durante la planeación cree etapas en la información que necesita para realizar el seguimiento, para que después de implementar el proyecto se puede establecer las opciones de seguimiento y limitar la cantidad de datos a proporcionarle únicamente la información que necesita.  
  
-   **No realizar seguimiento de todos los mensajes**: se recomienda que no realiza el seguimiento todos los mensajes, porque cada vez que se toca un mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea otra copia. En su lugar, puede restringir el ámbito mediante el seguimiento solo un puerto específico. Esto ayuda a maximizar el rendimiento del sistema y mantener las bases de datos ordenado.  
  
-   **Configurar seguimiento de los puertos de envío y puertos en lugar de en una canalización de recepción**: si establece opciones de seguimiento en las canalizaciones, también establecerá las opciones de seguimiento globalmente para todos los puertos que usa la canalización. Esto a su vez puede hacer mucho más datos sometidos a seguimiento que piensa, lo que ralentizan el rendimiento del sistema. En su lugar, puede establecer opciones de seguimiento en el envío de puertos y puertos de recepción.  
  
-   **Tenga en cuenta varios factores cuando el tamaño de la base de datos de seguimiento de BizTalk**:  
  
    -   Al asignar el tamaño de la base de datos de seguimiento de BizTalk, cuenta factores de SQL Server, como el tamaño del índice, agregando un multiplicador de contingencia para los cálculos.  
  
    -   Al determinar el tamaño de los mensajes en la base de datos de seguimiento de BizTalk, agregue el tamaño medio del contexto del mensaje para el tamaño del mensaje si resulta significativo en comparación con el tamaño del mensaje.  
  
    -   Para limitar el tamaño de los mensajes en la base de datos de seguimiento de BizTalk, limite el número de propiedades que se promoción. Solo las propiedades promocionada de uso se deben si necesita para fines de enrutamiento, de lo contrario, utilice los campos distintivos.  
  
    -   Si la orquestación **forma Inicio y finalización** opción está habilitada, tenga en cuenta que un evento de inicio y detención para cada forma de cada instancia de orquestación se guarda en la base de datos de seguimiento de BizTalk.