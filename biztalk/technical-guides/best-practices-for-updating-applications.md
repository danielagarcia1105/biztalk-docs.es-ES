---
title: "Prácticas recomendadas para actualizar aplicaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 072eaf25-a1ee-4af3-b034-525a04260ef4
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01cf54454866eadbd70de7ef30439a0e7068cb1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="best-practices-for-updating-applications"></a>Prácticas recomendadas para actualizar las aplicaciones
Este tema describe los procedimientos recomendados que considere la posibilidad de usar al actualizar artefactos y aplicaciones de BizTalk.  
  
## <a name="versioning"></a>Creación de versiones  
 **Implementar una estrategia de control de versiones**  
  
-   Una estrategia de control de versiones buena es fundamental si se utilizan las transacciones o la aplicación de BizTalk no puede desactivarse para realizar actualizaciones o correcciones de errores de larga duración. Debe planear la estrategia de control de versiones de todos los artefactos de BizTalk: llama a esquemas, mapas, adaptadores personalizados, canalizaciones, los componentes de canalización, orquestaciones, las reglas de negocios, BAM y las clases personalizadas en las orquestaciones y los mapas.  
  
 **Coincide con los ensamblados en la base de datos de administración de BizTalk y la caché de ensamblados global (GAC)**  
  
-   Asegúrese de que las mismas versiones de ensamblados en la base de datos de administración de BizTalk en la GAC, por lo que la aplicación funcione correctamente. Si sigue el procedimiento de no instalar siempre un ensamblado en la GAC cuando lo implementa, es posible que tenga diferentes versiones en la GAC y en la base de datos de administración de BizTalk, hecho que producirá errores de procesamiento durante el tiempo de ejecución.  
  
 **Utilice la herramienta Comprobador de ensamblado de BizTalk y GAC remoto para comprobar el control de versiones**  
  
-   El **herramienta Comprobador de ensamblado de BizTalk y GAC remoto** (BTSAssemblyChecker.exe) comprueba las versiones de ensamblados implementados en la base de datos de administración de BizTalk y que están registrados correctamente en la GAC en todos los BizTalk Equipos de servidor. Puede usar esta herramienta para comprobar que todos los ensamblados que contienen los artefactos de una aplicación de BizTalk están instalados en todos los nodos de BizTalk. La herramienta es especialmente útil en combinación con una estrategia de control de versiones sólido para comprobar que la versión correcta de un conjunto de ensamblados está instalada en cada equipo de BizTalk, sobre todo cuando se utiliza el enfoque de implementación en paralelo.  
  
-   La herramienta está disponible con los medios de instalación de BizTalk Server en Support\Tools\x86\BTSAssemblyChecker.exe.  
  
 **Usar un producto de control de versiones**  
  
-   Debe usar un producto de control de versiones, como Microsoft Visual Studio® Team Foundation Server 2010, para los artefactos de BizTalk de seguimiento y control de versiones. Para obtener más información acerca de Microsoft Visual Studio® Team Foundation Server 2010, consulte [Microsoft Visual Studio® Team Foundation Server 2010](http://go.microsoft.com/fwlink/?LinkId=210637) (http://go.microsoft.com/fwlink/?LinkId=210637)  
  
 **Artefactos de factor en varias aplicaciones de BizTalk**  
  
-   Para llevar a cabo las versiones de ensamblado de artefactos de BizTalk, los ensamblados de la solución de BizTalk deben tenerse en cuenta (empaquetar) como para permitir el control de versiones de BizTalk Server. Para obtener más información acerca de factorización, consulte [agregar artefactos a una aplicación](../technical-guides/adding-artifacts-to-an-application.md).  
  
## <a name="updating-an-application"></a>Actualizar una aplicación  
 **Usar un archivo .msi para actualizar una aplicación**  
  
-   Actualizar aplicaciones normalmente es una operación deliberada y precisa en producción. Cuando se actualiza una aplicación, normalmente, debe usar una lista de comprobación manual. Sin embargo, es posible que pueda simplificar ciertos pasos mediante el uso de un archivo MSI. Cuando se usa un archivo .msi, puede resumir los artefactos de la aplicación en un paquete de distribución. Un archivo .msi es especialmente útil cuando se implantará dll actualizadas en varios cuadros en tiempo de ejecución o realizar una implementación de nivel de grupo. Cuando se crea un archivo .msi, debe excluir todos los otros recursos sin cambios y los enlaces del paquete.  
  
-   Si actualiza un ensamblado de BizTalk, debe detener, dar de baja, volver a dar de alta y, a continuación, iniciar los artefactos de BizTalk manualmente antes y después de importar e instalar el archivo MSI. Para obtener más información acerca de cómo actualizar un ensamblado de BizTalk, consulte [lista de comprobación: actualización de un ensamblado](../technical-guides/checklist-updating-an-assembly.md).  
  
-   Si actualiza un ensamblado de BizTalk Server utiliza las versiones en paralelo, tendrá que realizar pasos manuales antes y después con el archivo MSI. Para obtener más información acerca de los pasos manuales que son necesarios, consulte [lista de comprobación: actualización de un control de versiones de Side-by-Side aplicación usando](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md).  
  
## <a name="updating-an-assembly"></a>Actualizar un ensamblado  
 **Incrementar la versión de un ensamblado en un entorno de producción**  
  
-   Si va a actualizar un ensamblado que se ejecuta en un entorno de producción, siempre debe incrementar el número de versión del ensamblado.  
  
 **Actualización de la GAC con un ensamblado actualizado**  
  
-   Cuando se actualiza un ensamblado que contiene una orquestación, el esquema o el mapa, debe actualizar la GAC con el ensamblado que contiene la nueva versión. En caso contrario, BizTalk Server usará la versión no actualizada. Para ello, en los equipos que ejecuten una instancia del host con una aplicación enlazada, desinstale de la GAC la versión no actualizada del ensamblado que contiene el artefacto actualizado y asegúrese de que está instalada la versión nueva.  
  
 **Reiniciar una instancia de host después de actualizar un ensamblado**  
  
-   Si se actualiza un ensamblado de BizTalk en una aplicación existente, debe reiniciar instancias de host para que los cambios surtan efecto. Al reiniciar una instancia de host detiene todas las demás aplicaciones que se ejecutan en la instancia de host.  
  
## <a name="updating-an-artifact"></a>Actualizar un artefacto  
 **Anular la implementación de un artefacto dependiente antes el artefacto que depende**  
  
-   Si se anular la implementación de un artefacto del que depende otro artefacto, debe anular la implementación del artefacto dependiente en primer lugar.  
  
    > [!NOTE]  
    >  Si no anula la implementación del artefacto dependiente en primer lugar, la consola de administración de BizTalk Server se muestre una advertencia y podrá anular implementación de artefactos en el orden incorrecto.  
  
 **No detenga un artefacto que depende de otra aplicación**  
  
-   Si detiene un artefacto en una aplicación (que puede derivar de la detención de la aplicación completa) de la que depende otra aplicación, la aplicación dependiente no funcionará correctamente. Para obtener más información acerca de cómo detener una aplicación, consulte [cómo iniciar y detener una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154729) (http://go.microsoft.com/fwlink/?LinkID=154729).  
  
 **Agregue una referencia a un ensamblado antes de mover un artefacto**  
  
-   Cuando mueve un artefacto a una aplicación nueva, se mueven también los artefactos con los que tiene relaciones de dependencia a no ser que la aplicación nueva tenga una referencia a las aplicaciones que contienen los artefactos de los que depende el artefacto movido. Asimismo, se mueven los artefactos que tengan relaciones de dependencia con el artefacto movido a no ser que las aplicaciones que los contienen tengan una referencia a la aplicación nueva. Al mover un artefacto, se muestra la lista de otros artefactos que también se moverán.  
  
## <a name="updating-bindings"></a>Actualizar enlaces  
 **Automatizar la reconfiguración de enlaces**  
  
-   Al actualizar un ensamblado en una aplicación, a menudo se sobrescriben sus enlaces o bien no se puede enlazar el ensamblado, de modo que es necesario volver a configurar los enlaces de forma manual. Puede automatizar este proceso mediante el uso de un archivo de enlace. Si va a actualizar la misma versión de un ensamblado, puede exportar un archivo de enlace para el ensamblado, a continuación, actualiza el ensamblado, a continuación, importar el ensamblado en la aplicación y, a continuación, volver a aplicar los enlaces anteriores importando el archivo de enlace. Si va a actualizar un ensamblado con una versión más reciente, puede exportar un archivo de enlace, edite el archivo para que refleje la nueva versión de ensamblado, importar el nuevo ensamblado en la aplicación y, a continuación, aplicar los nuevos enlaces importando el archivo de enlace. Para obtener más información acerca de los archivos de enlace, vea [cómo exportar enlaces a un archivo de enlace](../technical-guides/how-to-export-bindings-to-a-binding-file.md). Para obtener más información acerca de cómo editar un archivo de enlace, vea [personalizar archivos de enlace](http://go.microsoft.com/fwlink/?LinkID=155000) (http://go.microsoft.com/fwlink/?LinkID=155000).  
  
## <a name="starting-or-stopping-an-application"></a>Iniciar o detener una aplicación  
 **Detener una aplicación para actualizar artefactos**  
  
-   Si no detiene una aplicación para actualizar artefactos de la aplicación, debe detener la publicación a la base de datos de cuadro de mensajes deshabilitando los puntos de conexión, temporalmente, detener y dar de baja las instancias en ejecución. Para detener y dar de baja instancias en ejecución, todas las instancias suspendidas o deshidratadas deben ser manualmente reanudar y completadas o terminadas.  
  
-   Aunque no es obligatorio detener una aplicación para actualizar un artefacto o instalar la aplicación, recomendamos detenerla siempre que actualice un artefacto.  
  
## <a name="see-also"></a>Vea también  
 [Cómo exportar enlaces a un archivo de enlace](../technical-guides/how-to-export-bindings-to-a-binding-file.md)