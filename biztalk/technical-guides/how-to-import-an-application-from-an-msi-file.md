---
title: Cómo importar una aplicación desde un archivo .msi | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5472df9-9f1e-42d5-82e0-cc559caf56b3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e1cea55ba50a094258a3fcf07eedf30466566d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004925"
---
# <a name="how-to-import-an-application-from-an-msi-file"></a>Cómo importar una aplicación desde un archivo .msi
Puede usar al Asistente para importación de MSI en la consola de administración de BizTalk Server o BTSTask para importar una aplicación de BizTalk desde un archivo .msi a un grupo de BizTalk en el entorno de destino e instalar la aplicación en instancias de host individual en el grupo. El proceso de importación completa realiza las siguientes operaciones:  
  
- Una implementación de nivel de grupo de la aplicación  
  
- Instalación de una nivel de servidor de la aplicación.  
  
  **Implementación de aplicaciones de nivel de grupo**  
  
  Realizar una implementación de nivel de grupo de una aplicación en un servidor en el grupo, ejecute al Asistente para la importación MIS desde la consola de administración de BizTalk Server o mediante la ejecución de BTSTask. La implementación de nivel de grupo hace lo siguiente:  
  
- Crea la aplicación y sus artefactos en el grupo  
  
- Importa enlaces residentes en el paquete .msi  
  
- Implementa todos los ensamblados de BizTalk Server con sus artefactos en la base de datos de administración de BizTalk para el grupo  
  
- Ejecuta los scripts especificados que ejecutará en el momento de la importación.  
  
  Si ha agregado archivos de enlace específicas del entorno para la aplicación, tendrá que seleccionar los enlaces que se va a aplicar durante la importación.  
  
  **Instalación de la aplicación de nivel de servidor**  
  
  Realizar una instalación de nivel de servidor de una aplicación en cada servidor en un grupo, haga doble clic en el propio archivo .msi o realizar el proceso de instalación al final del Asistente para importación de MSI. En lugar de esto una vez por cada grupo, normalmente se realiza en cada servidor BizTalk server que sea miembro del grupo. La instalación de nivel de servidor hace lo siguiente:  
  
- Instala todos los ensamblados de BizTalk Server y los ensamblados de dependencias en la caché de ensamblados global del servidor, para que este equipo tiene todos los archivos binarios que necesita en tiempo de ejecución  
  
- Revierte los servicios Web relacionados que pueden formar parte de la solución, por ejemplo, publican orquestaciones como servicios Web.  
  
- Aplica los cambios específicos del equipo, como crear previamente las colas de MSMQ o crear las estructuras de carpeta de colocación de archivos y permisos, lo que pueden realizarse con la Ayuda de secuencias de comandos.  
  
  Al ejecutar un archivo .msi para instalar una aplicación, el archivo .msi crea las entradas de registro en la lista Agregar o quitar programas y acelera la implementación al automatizar la implementación de artefactos y sus dependencias en el orden correcto.  
  
  Para obtener más información acerca de cómo instalar una aplicación de BizTalk, consulte [cómo instalar una aplicación](../technical-guides/how-to-install-an-application.md).  
  
  **La implementación de la aplicación completa y el proceso de instalación**  
  
  El Asistente para importación de MSI se implementa la aplicación en el grupo. No se instala la aplicación en los servidores individuales en el grupo. Si la aplicación incluye artefactos basados en archivos, deberá instalar la aplicación en cada instancia de host que se ejecutará los ensamblados en la aplicación (y los equipos que ejecuten aplicaciones que dependen de esta aplicación). Puede hacerlo en el servidor ejecutó el Asistente para importación de MSI, sin embargo, seleccionando la **ejecutar el Asistente para instalación de aplicaciones para instalar la aplicación en el equipo local** casilla de verificación en la página de importación se realizó correctamente mostrada por el Asistente para importación de MSI. Puede hacerlo en los otros servidores del grupo haciendo doble clic en el archivo .msi en cada uno de esos servidores.  
  
  Si está listo para probar la aplicación, puede importarlo en un grupo de BizTalk en un entorno de prueba. Si la aplicación está lista para producción o ensayo, puede importarlo en uno de estos entornos.  
  
## <a name="important-considerations"></a>Consideraciones importantes  
 Al importar una aplicación de BizTalk desde un archivo .msi, tenga en cuenta lo siguiente:  
  
- **Debe especificar que desea que los artefactos que se sobrescriban en un proceso de importación estándar.** Si desea sobrescribir artefactos existentes, seleccione la opción para sobrescribir artefactos existentes al importar el archivo MSI.  
  
- **Los enlaces importados sobrescriben los enlaces existentes.** Al importar un archivo .msi que contenga enlaces en una aplicación existente, los enlaces importados sobrescribirán los existentes que tengan el mismo nombre. Esto ocurre aun si no se ha seleccionado la opción de sobrescritura de los artefactos existentes al importar el archivo .msi. Si no desea que los enlaces de la aplicación que se está exportando sobrescriba los enlaces de la aplicación en la que se está importando el archivo .msi, no seleccione el archivo de enlace como un recurso que es preciso exportar durante la exportación. Para obtener más información sobre la configuración de los recursos para una exportación, consulte [cómo exportar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154848) (http://go.microsoft.com/fwlink/?LinkID=154848).  
  
  A medida que se aplican los enlaces durante el proceso de importación, los enlaces que ya se han aplicado se sobrescriben con enlaces nuevos que tienen el mismo nombre. Es decir, surtirá efecto el último enlace de un nombre concreto que se aplica. Cuando importa una aplicación, los enlaces se aplican en el orden siguiente:  
  
1.  Los enlaces de la aplicación generados por BizTalk Server que no se agregaron explícitamente a la aplicación mediante un archivo de enlace, pero que el usuario seleccionó explícitamente para exportarlos al archivo .msi de la aplicación.  
  
2.  Los archivos de enlace que se han agregado explícitamente y que no tienen especificado un entorno de implementación de destino. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
3.  Los enlaces que se ha agregado explícitamente y que tienen un entorno de implementación de destino asociado que coincide con el entorno de implementación seleccionado para la importación de la aplicación. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
- **El host especificado debe existir.** Para importar una aplicación desde un archivo .msi, ya debe existir un host correspondiente al host especificado en los enlaces de la aplicación contenidos en el archivo .msi en el grupo de BizTalk o se producirá un error en la operación de importación. Además, es necesario que el nivel de confianza del host coincida.  
  
- **Las dependencias pueden tener efectos significativos en las operaciones de importación.** Al importar una aplicación que tiene una dependencia en otra aplicación, se aplican las reglas siguientes:  
  
  -   Si una aplicación que va a importar depende de un artefacto de otra aplicación, debe agregar una referencia de la primera aplicación a la segunda aplicación. La aplicación y el artefacto necesario ya deben existir en el grupo de destino. El Asistente para importación le permite agregar la referencia. Sin embargo, si usa el comando ImportApp de BTSTask, debe agregar la referencia a la aplicación tras la importación. Para obtener más información, consulte [cómo agregar una referencia a otra aplicación](http://go.microsoft.com/fwlink/?LinkId=155011) (http://go.microsoft.com/fwlink/?LinkId=155011). El Asistente para importación hace coincidir las referencias con las aplicaciones existentes en el grupo y proporciona la opción de agregar una nueva referencia o cambiar una referencia existente. Mientras que BizTalk Server comprueba que la aplicación a la que se hace referencia existe, se recomienda seguir los pasos adicionales para comprobar que la aplicación a la que se hace referencia contiene el artefacto necesario.  
  
  -   Cuando instala una aplicación, debe instalar también las aplicaciones de las que depende. Cuando instale una aplicación que tenga dependencia de un artefacto, como de un ensamblado de BizTalk, que está contenido en otra aplicación, también es necesario instalar primero la aplicación que contiene el artefacto. Por ejemplo, si desea instalar la aplicación A y ésta depende de un ensamblado de la aplicación B, debe instalar primer la aplicación B. A continuación, puede instalar r de aplicación. Para obtener más información acerca de cómo instalar una aplicación de BizTalk, consulte [cómo instalar una aplicación](../technical-guides/how-to-install-an-application.md).  
  
  -   Si desea importar una aplicación en un grupo de BizTalk diferente y ejecutarla en dicho grupo, debe importar los artefactos de los que depende esta aplicación. Puede hacerlo mediante la primera importación de una aplicación que contiene el artefacto que se hace referencia, o mediante la adición del artefacto necesario a la aplicación que lo requiera. Para obtener más información sobre cómo importar una aplicación de BizTalk, consulte [cómo importar una aplicación desde un archivo .msi](../technical-guides/how-to-import-an-application-from-an-msi-file.md).  
  
  Para obtener más consideraciones e información sobre cómo importar una aplicación de BizTalk desde un archivo .msi, vea [cómo importar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154827) (http://go.microsoft.com/fwlink/?LinkID=154827).  
  
## <a name="how-to-import-an-application"></a>Cómo importar una aplicación  
 Para obtener instrucciones sobre cómo importar una aplicación de BizTalk desde un archivo .msi, vea [cómo importar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154827) (http://go.microsoft.com/fwlink/?LinkID=154827).