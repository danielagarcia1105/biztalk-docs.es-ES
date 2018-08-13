---
title: Procedimientos recomendados para actualizar aplicaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 072eaf25-a1ee-4af3-b034-525a04260ef4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75dbde61369cdc8658dd9b39fa75fe2655225222
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001733"
---
# <a name="best-practices-for-updating-applications"></a>Procedimientos recomendados para actualizar las aplicaciones
En este tema se describe los procedimientos recomendados que debe considerar el uso al actualizar artefactos y aplicaciones de BizTalk.  
  
## <a name="versioning"></a>Creación de versiones  
 **Implementar una estrategia de control de versiones**  
  
- Una estrategia de control de versiones buena es esencial si se utilizan las transacciones o la aplicación de BizTalk no puede desactivarse para realizar actualizaciones o correcciones de errores de larga ejecución. Debe planear la estrategia de control de versiones de todos los artefactos de BizTalk: llama esquemas, mapas, adaptadores personalizados, canalizaciones, los componentes de canalización, orquestaciones, las reglas de negocios, BAM y las clases personalizadas en las orquestaciones y los mapas.  
  
  **Coincide con los ensamblados en la base de datos de administración de BizTalk y la caché global de ensamblados (GAC)**  
  
- Asegúrese de que son las mismas versiones de ensamblados en la base de datos de administración de BizTalk en la GAC, por lo que la aplicación funcione correctamente. Si sigue el procedimiento de no instalar siempre un ensamblado en la GAC cuando lo implementa, es posible que tenga diferentes versiones en la GAC y en la base de datos de administración de BizTalk, hecho que producirá errores de procesamiento durante el tiempo de ejecución.  
  
  **Utilice la herramienta Comprobador de ensamblados de BizTalk y GAC remota para comprobar el control de versiones**  
  
- El **herramienta Comprobador de ensamblados de BizTalk y GAC remoto** (BTSAssemblyChecker.exe) comprueba las versiones de ensamblados implementados en la base de datos de administración de BizTalk y que están registrados correctamente en la GAC en todos los BizTalk Equipos de servidor. Puede usar esta herramienta para comprobar que todos los ensamblados que contienen los artefactos de una aplicación de BizTalk están instalados en todos los nodos de BizTalk. La herramienta es especialmente útil en combinación con una estrategia de control de versiones sólido para comprobar que la versión correcta de un conjunto de ensamblados está instalada en cada equipo de BizTalk, especialmente cuando se usa el enfoque de implementación en paralelo.  
  
- La herramienta está disponible con los medios de instalación de BizTalk Server en Support\Tools\x86\BTSAssemblyChecker.exe.  
  
  **Usar un producto de control de versiones**  
  
- Debe usar un producto de control de versiones, como Microsoft Visual Studio® Team Foundation Server 2010 para seguimiento y control de versiones de artefactos de BizTalk. Para obtener más información acerca de Microsoft Visual Studio® Team Foundation Server 2010 consulte [Microsoft Visual Studio® Team Foundation Server 2010](http://go.microsoft.com/fwlink/?LinkId=210637) (http://go.microsoft.com/fwlink/?LinkId=210637)  
  
  **Artefactos de factor en varias aplicaciones de BizTalk**  
  
- Para poder realizar versiones de los ensamblados de artefactos de BizTalk, los ensamblados de la solución de BizTalk deben crearse (empaquetado) de forma para permitir el control de versiones de BizTalk Server. Para obtener más información acerca de factorización, consulte [agregar artefactos a una aplicación](../technical-guides/adding-artifacts-to-an-application.md).  
  
## <a name="updating-an-application"></a>Actualización de una aplicación  
 **Usar un archivo .msi para actualizar una aplicación**  
  
-   Actualizar aplicaciones suele ser una operación intencionada y precisa en producción. Al actualizar una aplicación, normalmente debe usar una lista de comprobación manual. Sin embargo, es posible que pueda optimizar algunos pasos mediante el uso de un archivo .msi. Cuando se usa un archivo .msi, puede concluir sus artefactos de la aplicación en un paquete de distribución. Un archivo .msi es especialmente útil al implementar archivos DLL actualizados en varios cuadros en tiempo de ejecución o realizar una implementación de nivel de grupo. Cuando se crea un archivo .msi, debe excluir todos los demás recursos sin cambios y los enlaces del paquete.  
  
-   Si actualiza un ensamblado de BizTalk, debe detener, dar de baja, volver a dar de alta y, a continuación, iniciar los artefactos de BizTalk manualmente antes y después de importar e instalar el archivo .msi. Para obtener más información acerca de cómo actualizar un ensamblado de BizTalk, consulte [lista de comprobación: actualización de un ensamblado](../technical-guides/checklist-updating-an-assembly.md).  
  
-   Si actualiza un ensamblado de BizTalk Server utiliza las versiones en paralelo, tendrá que realizar pasos manuales antes y después con el archivo MSI. Para obtener más información acerca de los pasos manuales que son necesarios, consulte [lista de comprobación: actualización de un control de versiones de aplicaciones mediante Side-by-Side](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md).  
  
## <a name="updating-an-assembly"></a>Actualización de un ensamblado  
 **Incremento de la versión de un ensamblado en un entorno de producción**  
  
- Si va a actualizar un ensamblado que se ejecuta en un entorno de producción, siempre debe incrementar el número de versión del ensamblado.  
  
  **Actualización de la GAC a un ensamblado actualizado**  
  
- Cuando se actualiza un ensamblado que contiene una orquestación, el esquema o el mapa, debe actualizar la GAC con el ensamblado que contiene la nueva versión. En caso contrario, BizTalk Server usará la versión no actualizada. Para ello, en los equipos que ejecuten una instancia del host con una aplicación enlazada, desinstale de la GAC la versión no actualizada del ensamblado que contiene el artefacto actualizado y asegúrese de que está instalada la versión nueva.  
  
  **Reiniciar una instancia de host después de actualizar un ensamblado**  
  
- Si se actualiza un ensamblado de BizTalk en una aplicación existente, deberá reiniciar instancias de host para que los cambios surtan efecto. Al reiniciar una instancia de host detiene todas las demás aplicaciones que se ejecutan en la instancia de host.  
  
## <a name="updating-an-artifact"></a>Actualizar un artefacto  
 **Anular la implementación de un artefacto dependiente antes el artefacto que depende**  
  
- Si anular la implementación de un artefacto del que depende otro artefacto, debe anular la implementación del artefacto dependiente en primer lugar.  
  
  > [!NOTE]  
  >  Si no anular la implementación del artefacto dependiente en primer lugar, la consola de administración de BizTalk Server mostrará una advertencia y no podrá anular implementación de artefactos en el orden incorrecto.  
  
  **No detenga un artefacto que depende otra aplicación**  
  
- Si detiene un artefacto en una aplicación (que puede derivar de la detención de la aplicación completa) de la que depende otra aplicación, la aplicación dependiente no funcionará correctamente. Para obtener más información acerca de cómo detener una aplicación, consulte [cómo iniciar y detener una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154729) (http://go.microsoft.com/fwlink/?LinkID=154729).  
  
  **Agregue una referencia a un ensamblado antes de mover un artefacto**  
  
- Cuando mueve un artefacto a una aplicación nueva, se mueven también los artefactos con los que tiene relaciones de dependencia a no ser que la aplicación nueva tenga una referencia a las aplicaciones que contienen los artefactos de los que depende el artefacto movido. Asimismo, se mueven los artefactos que tengan relaciones de dependencia con el artefacto movido a no ser que las aplicaciones que los contienen tengan una referencia a la aplicación nueva. Al mover un artefacto, se muestra la lista de otros artefactos que también se moverán.  
  
## <a name="updating-bindings"></a>Actualizando enlaces  
 **Automatizar la reconfiguración de enlaces**  
  
-   Al actualizar un ensamblado en una aplicación, a menudo se sobrescriben sus enlaces o bien no se puede enlazar el ensamblado, de modo que es necesario volver a configurar los enlaces de forma manual. Puede automatizar este proceso mediante el uso de un archivo de enlace. Si va a actualizar la misma versión de un ensamblado, primero exporte un archivo de enlace para el ensamblado, a continuación, actualiza el ensamblado, a continuación, importar el ensamblado en la aplicación y, a continuación, volver a aplicar los enlaces anteriores al importar el archivo de enlace. Si va a actualizar un ensamblado con una versión más reciente, puede exportar un archivo de enlace, edite el archivo para reflejar la nueva versión de ensamblado, importar el nuevo ensamblado en la aplicación y, a continuación, aplicar los nuevos enlaces importando el archivo de enlace. Para obtener más información acerca de los archivos de enlace, consulte [cómo exportar enlaces a un archivo de enlace](../technical-guides/how-to-export-bindings-to-a-binding-file.md). Para obtener más información acerca de cómo editar un archivo de enlace, consulte [personalizar archivos de enlace](http://go.microsoft.com/fwlink/?LinkID=155000) (http://go.microsoft.com/fwlink/?LinkID=155000).  
  
## <a name="starting-or-stopping-an-application"></a>Iniciar o detener una aplicación  
 **Detener una aplicación para actualizar artefactos**  
  
-   Si no se detiene una aplicación para actualizar artefactos de la aplicación, deberá detener la publicación a la base de datos de cuadro de mensajes al deshabilitar los puntos de conexión y detener temporalmente y dar de baja cualquier instancia en ejecución. Para detener y dar de baja las instancias en ejecución, todas las instancias suspendidas o deshidratadas deben se manualmente reanudar y completadas o finalizadas.  
  
-   Aunque no es obligatorio detener una aplicación para actualizar un artefacto o instalar la aplicación, recomendamos detenerla siempre que actualice un artefacto.  
  
## <a name="see-also"></a>Vea también  
 [Cómo exportar enlaces a un archivo de enlace](../technical-guides/how-to-export-bindings-to-a-binding-file.md)