---
title: "Problemas conocidos con la implementación de una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e5fb4f6-f9bd-4322-93f9-723e9e3c3317
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7fa139469ea8718c3d4430235ffb576195e67a7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-deploying-an-application"></a>Problemas conocidos con la implementación de una aplicación
## <a name="deploying-a-biztalk-application"></a>Implementar una aplicación de BizTalk  
 **Implementar una aplicación actualizada requiere corrección de referencias**  
  
 Si se implementa una aplicación completamente nueva para reemplazar una existente, se debe corregir cualquier referencia existente entre otras aplicaciones y la aplicación que se está reemplazando.  
  
 **Con Visual Studio para implementar una aplicación puede detener aplicaciones**  
  
> [!NOTE]  
>  Se recomienda evitar el uso de Visual Studio para implementar una aplicación en un entorno de producción.  
  
 Si usa Visual Studio para implementar una aplicación en un entorno de producción y la opción reiniciar instancias de Host está establecida en True en Propiedades del proyecto, todas las instancias de host se reiniciará cuando se implementa la aplicación, los que no están asociados a incluidos Esta aplicación. Esto detendrá todas las demás aplicaciones que estén en ejecución en cualquier instancia de host del equipo local.  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a>Agregar artefactos a una aplicación de BizTalk  
 **Mover un artefacto puede mover las dependencias**  
  
 Al mover un artefacto a una nueva aplicación, también se mueven los artefactos en el que tiene dependencias a menos que la nueva aplicación tiene una referencia a las aplicaciones que contienen los artefactos que depende el artefacto movido. Además, los artefactos que tienen dependencias en el artefacto movido también se moverán a menos que las aplicaciones que los contienen tengan una referencia a la nueva aplicación. Al mover un artefacto, aparecerá la lista de los otros artefactos que también se moverán. Para obtener instrucciones acerca de cómo mover un artefacto, consulte [cómo mover un artefacto a una aplicación diferente](http://go.microsoft.com/fwlink/?LinkId=154999) (http://go.microsoft.com/fwlink/?LinkId=154999).  
  
## <a name="exporting-a-biztalk-application"></a>Exportar una aplicación de BizTalk  
 **Se mostrará un error incorrecto al instalar un archivo .msi en Windows Vista**  
  
 Al instalar un paquete .msi exportado mediante [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] en BizTalk Server con Windows Vista®, recibirá el siguiente mensaje de error, "el instalador ha encontrado un error inesperado al instalar este paquete. Esto puede deberse a un problema del paquete. El código de error es 2869". Para corregir este error, primero importe el paquete con BizTalk Server y, a continuación, volver a exportar e instalar el paquete.  
  
## <a name="importing-a-biztalk-application"></a>Importar una aplicación de BizTalk  
 **Las contraseñas no se quitan de archivos que se agrega a una aplicación de enlace**  
  
 Por motivos de seguridad, las contraseñas se quitan de los enlaces de aplicación durante la exportación de la aplicación. No obstante, no se quitan de ningún archivo de enlace que se haya agregado a la aplicación. Después de importar la aplicación, se deberá volver a configurar las contraseñas para que funcione la aplicación. Puede hacerlo modificando el archivo de enlace o mediante la consola de administración. Para obtener más información acerca de cómo editar un archivo de enlace, vea [personalizar archivos de enlace](http://go.microsoft.com/fwlink/?LinkId=155000) (http://go.microsoft.com/fwlink/?LinkId=155000). Para obtener más información acerca de cómo configurar la seguridad de adaptadores, vea [usando adaptadores](http://go.microsoft.com/fwlink/?LinkId=155001) (http://go.microsoft.com/fwlink/?LinkId=155001).  
  
 **BizTalk Server no se revierten imports con scripts o instala**  
  
 Si se producen errores en una importación, BizTalk Server deshace todas las operaciones de importación, excepto las acciones llevadas a cabo mediante secuencias de comandos personalizadas. Esto también es cierto para la instalación y operaciones de desinstalación.  
  
 **No se puede notificar un esquema que falta después de una importación**  
  
 Si crea un filtro para un puerto de envío en una aplicación que utilice un esquema de propiedades en otra aplicación y si, a continuación, importa la primera aplicación en un nuevo grupo de BizTalk, no recibirá ninguna advertencia de la falta del esquema, y el filtrado no se efectuará una vez instalada e iniciada la aplicación. Puede corregir el problema importando la aplicación que contiene el esquema antes de instalar la aplicación que no contiene el esquema.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de una aplicación](../technical-guides/deploying-an-application.md)