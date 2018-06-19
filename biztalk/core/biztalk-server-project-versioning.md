---
title: Las versiones del proyecto de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dcdd5354-6335-4320-adbf-28ac934c9ce6
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1893509d569dc74bf8d6d28680026ebe90ba9149
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234196"
---
# <a name="biztalk-server-project-versioning"></a>Control de versiones del proyecto de BizTalk Server
Al desarrollar con la [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)], control de versiones se rige por un conjunto estándar de reglas que trabajan para minimizar el impacto de los cambios de números de versión. Dependiendo de cómo un [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]se implementa la aplicación o componente, las dependencias se pueden administrar mediante un archivo de configuración de la aplicación, a través de la instalación de XCOPY, o por otro [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] mecanismos de implementación. Tal y como se mostrará en las siguientes secciones, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] agrega una complejidad adicional al control de versiones y dependencias.  
  
## <a name="implications-of-changing-version-numbers"></a>Repercusiones del cambio de los números de versión  
 En [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] número de compilación de desarrollo es habitual para actualizar el número de versión de ensamblado al actual cuando realiza una compilación. Sin embargo, cuando se desarrolla una solución de BizTalk, al cambiar el número de versión de ensamblado se puede romper la relación entre un ensamblado y los elementos dependientes que hacen referencia a DLL por su número de versión de ensamblado. En la tabla siguiente se enumera los elementos que hacen referencia a un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblado mediante su número de versión y el efecto del cambio de un número de versión de ensamblado.  
  
|Entidad|Efecto de cambiar el número de versión del ensamblado|  
|------------|------------------------------------------------|  
|Archivos de enlace|Al cambiar el número de versión de ensamblado se producen errores en cualquier archivo de enlace existente que haga referencia al ensamblado. Esto se debe a que el archivo de enlace hace referencia al ensamblado mediante atributos incluyendo el número de versión.<br /><br /> Puede actualizar la información de versión en el archivo de enlace mediante el Bloc de notas u otro editor. Puede volver a implementar la solución y, a continuación, volver a generar el archivo de enlace mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Por último, puede utilizar las secuencias de comandos para automatizar la implementación y el control de versiones. Para obtener más información acerca de la implementación, consulte [implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md).|  
|Archivos (.btt) de definición de perfiles de seguimiento de BAM|Al cambiar el número de versión de ensamblado se producen errores en cualquier archivo de definición de perfiles de seguimiento de BAM existente. Los archivos de seguimiento de BAM están en un formato de archivo binario por lo que no se pueden editar y, en su lugar, se deben volver a generar. Si se requieren perfiles de seguimiento de BAM, es posible que sea necesario realizar una de las siguientes acciones:<br /><br /> -Evite actualizar con frecuencia los números de versión durante el proceso de compilación.<br />-Retrasar la creación de perfiles de seguimiento hasta que los números de versión son estables de BAM.|  
|Servicios Web publicados mediante el Asistente para publicación de servicios Web|Cuando se utiliza el Asistente para publicación de Web Services para generar una interfaz Web de ASP.NET, la versión del ensamblado de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblado está incluido en el código fuente ASP.NET. La interfaz ASP.NET utiliza el número de versión de ensamblado en tiempo de ejecución como parte de la **bodyTypeAssemblyQualifiedName** propiedad de la operación del servicio Web. Si el número de versión de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cambios de ensamblado sin actualizar la **bodyTypeAssemblyQualifiedName** propiedad y, a continuación, Web posteriores se rechazarán las operaciones de servicio por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].<br /><br /> Si la ubicación de recepción utiliza XmlDefaultPipeline, la suscripción se basa en el tipo de documento. Utiliza la información de ensamblado integrada y si el ensamblado no existe, se producirán errores. Si utiliza PassThruPipeline (que es la opción predeterminada si expone un puerto y permite que el asistente cree la ubicación de recepción), la suscripción omite esta información de ensamblado integrada.|  
  
 Para averiguar más sobre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblados e implementación, vea [ensamblados de BizTalk](../core/biztalk-assemblies.md).  
  
## <a name="approaches-to-versioning"></a>Enfoques para el control de versiones  
 Cuando se planifica un proyecto, tiene las siguientes opciones:  
  
-   Elegir una versión de ensamblado fija para una entrega determinada e incrementar solo el número de versión del archivo.  
  
-   Incrementar tanto la versión de ensamblado como la de archivo durante el desarrollo.  
  
 En la siguiente tabla se comparan estos enfoques.  
  
|Versión de ensamblado fija, versión de ensamblado dinámica|Versión de ensamblado dinámica, versión de archivo fija o dinámica|  
|--------------------------------------------------|-------------------------------------------------------------|  
|Número de versión de ensamblado = Número fijo<br /><br /> Número de versión de archivo = Número de versión de compilación|Número de versión de ensamblado = Número de versión de compilación<br /><br /> Número de versión de archivo = Número de versión de compilación|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Puede seleccionar una versión incorrecta del ensamblado en tiempo de ejecución si se instalan varios ensamblados.|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]siempre se ejecuta la versión más reciente del ensamblado, incluso si se instalan varios ensamblados.|  
|En cualquier momento solo se puede implementar una versión de solución.|Se pueden implementar de forma paralela diferentes versiones de la solución (aunque otros aspectos de la solución, como las definiciones de esquema, pueden entrar en conflicto).|  
|Debe reiniciarse BizTalk Host para forzar la carga de ensamblados actualizados.|Fuerza [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cargar nuevos ensamblados.|  
|Requiere menos trabajo para crear una implementación nueva ya que no es necesario editar los archivos que hacen referencia al número de versión (por ejemplo, archivos de enlace y perfiles de seguimiento).|Requiere más trabajo para la implementación ya que es necesario mantener actualizados con la versión nueva los archivos que hacen referencia al número de versión del ensamblado.|  
  
 Puede elegir utilizar el enfoque de versión de ensamblado fija o de versión de archivo dinámica si va a crear un prototipo de un sistema o a desarrollar cualquier otro tipo de proyecto que no sea de envío. Si no desea entregar la aplicación a un usuario final, puede aumentar la eficacia de las tareas de implementación y reducir las dependencias interrumpidas al fijar la versión de ensamblado e incrementar el número de versión de archivo. Para el seguimiento de versiones, no olvide aumentar el número de versión del archivo de cada compilación.  
  
 Si crea un proyecto que se va a entregar a un usuario final, debería considerar aumentar el número de versión de ensamblado y, de forma opcional, almacenar un número de versión de archivo significativo. Mientras que este enfoque provoca un esfuerzo adicional al tener que modificar los números de versión de compilación y las dependencias asociadas, asegura que se utilizan las últimas versiones de los ensamblados. Al utilizar secuencias de comandos de implementación automatizadas, puede disminuir la influencia del control de versiones. Para ver ejemplos de implementación, consulte [implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](../core/application-deployment-biztalk-server-samples-folder.md).  
  
> [!NOTE]
>  Debería elegir el mecanismo de control de versiones que asegura que se entregan los archivos adecuados y simplifica el mantenimiento y la mejora.  
  
## <a name="map-function-version-numbering"></a>Numeración de versiones en la función de asignación  
 Ensamblados de .NET se pueden invocar desde dentro de un mapa mediante el uso de la **secuencias de comandos** functoid. Esto proporciona una gran flexibilidad y permite al programador resolver problemas de asignación personalizada muy diferentes. También impone una restricción unique en la asignación: internamente debe hacer referencia no solo el nombre de tipo de ensamblado, sino también el número de versión completo del ensamblado que se va a invocar. Como consecuencia, si cambia el número de versión del ensamblado al que llama la asignación, se interrumpirán todos los enlaces que hacen referencia al ensamblado.  
  
 Para evitar este problema recomendamos que si es necesario que una asignación llame a los ensamblados, se cree un ensamblado específico para mantener solo la funcionalidad de asignación y se fije un número de versión de ensamblado para este ensamblado. De este modo, otras funciones auxiliares pueden actualizar la versión de ensamblado sin interrumpir las asignaciones.  
  
 Si se cambia un ensamblado al que hace referencia una asignación tras el desarrollo de la asignación, debería actualizar el archivo de asignaciones fuera del editor de asignaciones para que refleje los números de versiones actualizados.  
  
#### <a name="to-use-notepad-to-modify-the-map-file-to-reflect-updated-version-numbers"></a>Realice lo siguiente para modificar mediante el Bloc de notas el archivo de asignaciones y que refleje los números de versiones actualizados:  
  
1.  Mediante el **iniciar** menú, inicie el Bloc de notas.  
  
2.  En el Bloc de notas, en el **archivo** menú, haga clic en **abiertos**. En el **abiertos** cuadro de diálogo, seleccione la asignación de archivos desea modificar y, a continuación, haga clic en **abiertos**.  
  
3.  En el menú **Edición** , haga clic en **Buscar**. En el **buscar** diálogo cuadro, escriba **ensamblado =** y, a continuación, haga clic en **Buscar siguiente**.  
  
4.  Si hay una referencia de secuencia de comandos a un ensamblado externo, el Bloc de notas debería buscar un elemento XML como el siguiente:  
  
    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c5145e4e089" Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  
  
     Actualice el número de versión. Si hay varias instancias, use **reemplazar** en el **editar** menú.  
  
5.  Guarde el archivo.  
  
     Podrá abrir la asignación mediante el editor de asignaciones.  
  
## <a name="see-also"></a>Vea también  
 [Prácticas recomendadas para implementar una aplicación de BizTalk](../core/best-practices-for-deploying-a-biztalk-application.md)   
 [Admin (carpeta de ejemplos de BizTalk Server)](../core/admin-biztalk-server-samples-folder.md)   
 [Implementar e iniciar una nueva versión de una orquestación mediante programación](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md)