---
title: Procedimientos recomendados para implementar una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53852303-d368-4f9e-b4e2-f5918f65000b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa55a240669ab9369dd7a1862d3fda055f577edd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010709"
---
# <a name="best-practices-for-deploying-an-application"></a>Prácticas recomendadas para implementar una aplicación
Este tema enumeran las prácticas recomendadas que deben seguirse al implementar aplicaciones de BizTalk.  
  
## <a name="deploying-a-biztalk-application"></a>Implementar una aplicación de BizTalk  
 **Procedimientos de implementación de la aplicación de documento**  
  
-   Asegúrese de que todos los procedimientos utilizados en la implementación de aplicaciones se documentan en profundidad, por lo que tendrá un registro de cómo la implementación se realizó y sabrá cómo implementar más o anular la implementación. Todo lo que no se incluye en el script se debe documentar con los pasos detallados. Esto debe incluir documentar los cambios realizados en los sistemas externos y la implementación de componentes de terceros.  
  
 **Implementación de aplicaciones de script**  
  
-   Secuencia de comandos tantos pasos de implementación de aplicación como sea posible. Secuencias de comandos, reducen el riesgo de error humano durante el proceso de implementación.  
  
## <a name="creating-a-biztalk-application"></a>Crear una aplicación de BizTalk  
 **Secuencia de comandos de la creación de archivos .msi y aplicación de BizTalk**  
  
-   BtsTask.exe puede utilizarse para generar un script la creación de aplicaciones de BizTalk. Si se crea el script la creación de las aplicaciones, a continuación, los paquetes pueden se generan automáticamente mediante un proceso automatizado en un servidor de compilación. Para obtener más información sobre la creación de aplicaciones de secuencias de comandos, consulte [implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md).
  
## <a name="deploying-a-biztalk-assembly"></a>Implementar un ensamblado de BizTalk  
 **No implemente nunca un ensamblado desde Visual Studio en un equipo de producción**  
  
-   Durante el proceso de desarrollo, un programador suele volver a implementar ensamblados desde Visual Studio. Para permitir que se pueda volver a implementar, Visual Studio debe anular la implementación, separar, detener y dar de baja artefactos que están contenidos en los ensamblados. Aunque esto resulta necesario y apropiado en un entorno de desarrollo, puede producir consecuencias inesperadas no deseadas en un entorno de producción. Por este motivo, así como para impedir que se puedan implementar un ensamblado desde Visual Studio en un equipo de producción, se recomienda que nunca instale Visual Studio en un equipo de producción.  
  
-   Asimismo, no haga referencia nunca a una base de datos de producción desde un equipo que ejecute Visual Studio.  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a>Agregar artefactos a una aplicación de BizTalk  
 **Agrupar los artefactos relacionados entre sí en una sola aplicación**  
  
-   Cuando sea posible, coloque los artefactos relacionados en la misma aplicación de BizTalk. Esto le permite administrar e implementar los artefactos como entidad individual, lo que facilita la administración. Puede agrupar artefactos que admitan los mismos artefactos o el mismo proceso empresarial que realicen funciones similares en una única aplicación.  
  
 **Implementar artefactos compartidos en una aplicación diferente**  
  
-   Si dos o más aplicaciones van a compartir los artefactos, implemente los artefactos compartidos en una aplicación diferente. Por ejemplo, si dos aplicaciones comparten un esquema, coloque el esquema en una aplicación diferente. Se recomienda esto porque sólo un artefacto en un grupo de BizTalk puede tener un único identificador local único (LUID). Un LUID está formada por el nombre del artefacto y, opcionalmente, otros atributos. Si incluye un artefacto en una aplicación y, a continuación, cree una referencia a él desde otra aplicación, la aplicación que hace referencia no funcionen correctamente cuando se detiene la aplicación que contiene el artefacto.  
  
     Estas prácticas recomendadas se aplican a todos los tipos de artefactos, salvo para archivos, como las secuencias de comandos y los archivos Léame, que se agregan a la aplicación como un tipo de archivo del artefacto. Esto es porque se puede implementar más de un artefacto de archivo con el mismo nombre en un grupo de BizTalk. Por lo tanto, puede utilizar un archivo que tenga el mismo nombre en dos aplicaciones o más. En este caso, detener una aplicación no afectará a la otra aplicación. Para obtener más información acerca de cómo agregar artefactos de archivo, consulte [cómo agregar un archivo a una aplicación](../core/how-to-add-a-file-to-an-application.md).  
  
 **Implementar un sitio Web compartido en una aplicación diferente**  
  
-   Si una o varias soluciones empresariales van a compartir un sitio Web, implemente el sitio Web en una aplicación diferente. Esto se debe a que cuando desinstala una aplicación de BizTalk, se quita el directorio virtual del sitio Web que forma parte de la aplicación, aunque se esté ejecutando el sitio Web. Si se comparte el sitio Web con otra solución empresarial, el resultado será que la otra solución empresarial dejará de funcionar correctamente.  
  
 **Implementar directivas compartidas en una aplicación diferente**  
  
-   Si una o varias aplicaciones utilizan una directiva, debería implementarla en una aplicación diferente en lugar de crear una referencia de una aplicación a otra. Esto se debe a que cuando detiene la aplicación, se anula la implementación de sus directivas. Si detiene una aplicación que contiene una directiva que utiliza otra aplicación, la directiva dejará de funcionar en las dos aplicaciones.  
  
 **Implementar certificados compartidos en una aplicación diferente**  
  
-   Si una ubicación de recepción o un puerto de envío utiliza un certificado en dos o varias aplicaciones, debería implementar el certificado en una aplicación diferente y, a continuación, hacer referencia a esta aplicación desde las aplicaciones que necesitan utilizar el certificado. Esto es porque sólo un artefacto en un grupo de BizTalk puede tener un LUID único, por lo que no podrá importar el mismo certificado en dos aplicaciones diferentes. Si intenta importar dos aplicaciones que utilicen el mismo certificado, la primera importación se realizará correctamente, pero la segunda no. En este caso, la utilización de la opción Sobrescribir importación no soluciona el problema, ya que otra aplicación contiene el certificado existente que desea sobrescribir.  
  
## <a name="exporting-and-importing-a-biztalk-application"></a>Exportación e importación de una aplicación de BizTalk  
 **Al implementar los archivos .msi de gran tamaño, puede que necesite aumentar el tiempo de espera de transacción predeterminado de los componentes de COM + utiliza BizTalk Server para implementar aplicaciones**  
  
-   Si intenta implementar un archivo .msi que es muy grande (más de 100 MB), a continuación, la aplicación no puede implementarse en el tiempo de espera de transacción predeterminado de los componentes de COM + que se usan por BizTalk Server durante la implementación de la aplicación. Si las transacciones asociadas con estos tiempo de componentes COM + espera antes de que finalice la implementación, se producirá un error en la implementación. Si va a implementar los archivos .msi muy grande, considere la posibilidad de realizar uno de estos enfoques para mitigar este problema:  
  
-   Implemente varios archivos .msi más pequeños en lugar de un archivo .msi de gran tamaño.  
  
    -   Aumentar el tiempo de espera de transacción predeterminado de 3.000 segundos asociados con el Microsoft.BizTalk.ApplicationDeployment.Group y los componentes de Microsoft.BizTalk.Deployment.DeployerComponent de la interfaz de administración de servicios de componentes. Estos componentes pertenecen a las aplicaciones de Microsoft.BizTalk.ApplicationDeployment.Engine y Microsoft.Biztalk.Deployment COM +, respectivamente. Para obtener más información, vea el artículo de Microsoft Knowledge Base 287499, [cómo cambiar el valor de tiempo de espera de transacción para MTS o COM +](https://support.microsoft.com/help/287499/how-to-change-the-transaction-time-out-value-for-mts-or-com).  
  
 **Evitar que se sobrescriban los enlaces**  
  
-   Si no desea que los enlaces de la aplicación que se está exportando sobrescriba los enlaces de la aplicación en la que se está importando el archivo .msi, no seleccione el archivo de enlace como un recurso que es preciso exportar durante la exportación.  
  
 **Asegúrese de que el archivo .msi es seguro**  
  
-   Un archivo .msi puede contener datos confidenciales. Asegúrese de seguir los pasos necesarios para ayudar a garantizar que el archivo es seguro. Para obtener más información acerca de la seguridad del archivo .msi, consulte [seguridad y Windows Installer](../core/security-and-windows-installer.md).  
  
 **Asegúrese de que el archivo de enlace es seguro**  
  
-   Un archivo de enlace puede contener datos confidenciales. Asegúrese de seguir los pasos necesarios para ayudar a garantizar que el archivo es seguro.  
  
 **Programación exporta cuando nadie está realizando cambios a un artefacto**  
  
-   Programar las operaciones de exportación durante horas cuando los usuarios no están probables que esté realizando cambios a artefactos. Esto puede ser importante porque si un usuario modifica un artefacto basado en la base de datos, el directorio virtual, el certificado o la directiva mientras está en curso una operación de exportación, los cambios no se reflejarán en el archivo .msi exportado.  
  
## <a name="importing-a-biztalk-application"></a>Importar una aplicación de BizTalk  
 **La importación de archivos .msi de la secuencia de comandos**  
  
-   BtsTask.exe puede utilizarse para generar script de la importación de los archivos .msi de BizTalk existentes. Para obtener más información acerca del scripting importar de archivo .msi, consulte [implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md). 
  
    > [!NOTE]  
    >  Las notas del producto también se aplica a BizTalk Server.  
  
-   Puede agregar scripts para que se ejecute como secuencias de comandos previas y posteriores al procesamiento. Sin embargo, tendrá que incluir una lógica en las secuencias de comandos para comprobar las variables de entorno para determinar qué contexto se ejecuta la secuencia de comandos en (una importación, instalación o desinstalación) y procesar según corresponda. Para obtener más información sobre el uso de secuencias de comandos previas y posteriores al procesamiento, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md). 
  
 **Comprobar la existencia de artefactos que se hace referencia**  
  
-   Cuando una aplicación que va a importar tiene una referencia a otra aplicación, BizTalk Server comprueba que existe la aplicación que se hace referencia. Sin embargo, no comprueba que se incluyen los artefactos en el que la aplicación tiene dependencias en la aplicación que se hace referencia. Cuando se importa una aplicación que tiene dependencias de artefactos en otra aplicación, se recomienda que compruebe que la aplicación que se hace referencia contiene el artefacto requerido o artefactos.  
  
 **Importar desde un archivo .msi impide almacenar ensamblados que hayan cambiado en la memoria caché global de ensamblados**  
  
-   Para actualizar los artefactos de una aplicación, importar los artefactos modificados o actualizados desde un archivo .msi en la aplicación. Si no utiliza un archivo .msi para importar los artefactos, debe actualizar todos los servidores del grupo de almacenamiento de los ensamblados que hayan cambiado en la memoria caché global de ensamblados.  
  
 **Host procese grupos para actualizar un subconjunto del total de servidores**  
  
-   Al actualizar artefactos de una aplicación, normalmente debe actualizar todos los servidores de un grupo de BizTalk. Sin embargo, si utiliza grupos de procesamiento del host, sólo necesitará actualizar un subconjunto de los servidores en el grupo total.  
  
 **Si se agota el tiempo de espera de una operación de importación, divida la aplicación en archivos .msi adicionales**  
  
-   Una operación de importación agotará el tiempo si supera 3600 segundos de duración. Si está intentando importar un archivo .msi y agota el tiempo de espera de la operación, debería dividir el contenido de la aplicación en más de un archivo .msi exportando de nuevo la aplicación y seleccionando un subconjunto de artefactos para exportarlos. Para obtener más información acerca de cómo exportar una aplicación a un archivo .msi, consulte [exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).