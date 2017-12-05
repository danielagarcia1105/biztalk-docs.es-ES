---
title: "Problemas conocidos con la actualización de las aplicaciones y artefactos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 220ea03c-d453-40cc-8ddb-18a96f8ddfe5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e445ef19a1d65cc97a3603492a1ad9ba0442e9
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-updating-applications-and-artifacts"></a>Problemas conocidos de actualización de las aplicaciones y artefactos
## <a name="updating-an-application"></a>Actualizar una aplicación  
 **Quitar o eliminar un artefacto, no se quita de todas las ubicaciones**  
  
 Al quitar o eliminar un artefacto, se elimina de las bases de datos del servidor BizTalk Server, de modo que ya no aparece en la consola de administración ni en la lista de artefactos de una aplicación generados por el comando BTSTask ListApp. No quita el artefacto desde el registro de Windows, la caché de ensamblados global (GAC), un directorio virtual o el sistema de archivos, si se encuentra en alguna de estas ubicaciones. En el caso de los puertos de envío, grupos de puertos de envío, puertos de recepción y de las ubicaciones de recepción, que solo se encuentran en la base de datos de administración de BizTalk, esta operación elimina el artefacto completamente.  
  
## <a name="updating-an-artifact"></a>Actualizar un artefacto  
 **Quitar o cambiar el estado de un artefacto puede hacer que una aplicación no funcione**  
  
 Cuando agrega una referencia desde una aplicación a otra y realizar cambios en el estado de un artefacto en la que depende de otra aplicación o quita el artefacto, la aplicación que tiene la dependencia no funcionará correctamente. Para obtener más información acerca de cómo cambiar el estado de un artefacto, consulte la sección del artefacto correspondiente en [administrar artefactos](http://go.microsoft.com/fwlink/?LinkID=154725) (http://go.microsoft.com/fwlink/?LinkID=154725).  
  
 **No se admiten archivos de directivas de .NET**  
  
 No se admite el uso de archivos de directiva de .NET en BizTalk Server. ya que es posible que los archivos de directiva no funcionen de la forma esperada. Archivos de directiva redirigen a .NET a una versión de ensamblado especificado en la GAC, pero [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suele tener acceso a los ensamblados y datos de artefactos de una memoria caché o la base de datos de administración de BizTalk. Según el tipo de artefacto, la situación de almacenamiento en caché y el reinicio o no de las instancias de host, es posible que el archivo de directiva no realice lo que se desea.  
  
## <a name="updating-an-assembly"></a>Actualizar un ensamblado  
 **Posible que los cambios a un ensamblado no surtan efecto si el host no se ha detenido**  
  
 Ensamblados de BizTalk deben seguir las reglas de control de versiones. NET. La repercusión principal de esto es que un proyecto de BizTalk, una vez generado con una versión concreta de otro proyecto o ensamblado .NET (incluidos los proyectos de BizTalk), sigue utilizando esa versión hasta que se vuelve a generar con una versión más reciente.  
  
 Durante el desarrollo, se produce un problema común relacionado con el control de versiones .NET cuando los números de versión de un proyecto de BizTalk no cambian y el ensamblado se vuelve a implementar sin detener e iniciar la instancia de host de BizTalk en la que se cargan los tipos.  
  
 Cuando se vuelve a ejecutar el proceso, los cambios no surten efecto. Esto se debe a la forma en la que se cargan los ensamblados .NET en memoria. Dado que el host ya tiene una copia en memoria del ensamblado, vuelve a cargar el ensamblado cuando se coloca una nueva copia en la caché global de ensamblados (GAC). Por ejemplo, si se implementa y ejecuta la versión 1.0.0.0 de un ensamblado con una orquestación y se realizan cambios en la orquestación sin cambiar el número de versión, los cambios no surtirán efecto. Después de detener la instancia de host, la copia en memoria del ensamblado se libera; además, cuando la instancia de host se inicia de nuevo, carga la nueva copia del ensamblado y obtiene los cambios. Si se implementó una nueva versión, por ejemplo versión 2.0.0.0 y se cargó, a continuación, los cambios surtirán efecto.  
  
 **Si cambia la versión de ensamblado puede romper la relación entre un ensamblado y los elementos que hacen referencia a él por versión**  
  
 En el desarrollo de .NET Framework es típico para actualizar el número de versión de ensamblado para el número de compilación actual cuando realiza una compilación. Sin embargo, cuando se desarrolla una solución de BizTalk, al cambiar el número de versión de ensamblado se puede romper la relación entre un ensamblado y los elementos dependientes que hacen referencia a DLL por su número de versión de ensamblado. En la tabla siguiente se enumera los elementos que hacen referencia a un ensamblado de BizTalk Server mediante su número de versión y el efecto del cambio de un número de versión de ensamblado.  
  
|Entidad|Efecto de cambiar el número de versión del ensamblado|  
|------------|------------------------------------------------|  
|Archivos de enlace|Al cambiar el número de versión de ensamblado se producen errores en cualquier archivo de enlace existente que haga referencia al ensamblado. Esto se debe a que el archivo de enlace hace referencia al ensamblado mediante atributos incluyendo el número de versión.<br /><br /> Puede actualizar la información de versión en el archivo de enlace mediante el Bloc de notas u otro editor. Puede volver a implementar la solución y, a continuación, volver a generar el archivo de enlace mediante la consola de administración de BizTalk Server. Por último, puede utilizar las secuencias de comandos para automatizar la implementación y el control de versiones. Para obtener más información acerca de la implementación, consulte [implementar y administrar aplicaciones de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154210) (http://go.microsoft.com/fwlink/?LinkID=154210).|  
|Archivos (.btt) de definición de perfiles de seguimiento de BAM|Al cambiar el número de versión de ensamblado se producen errores en cualquier archivo de definición de perfiles de seguimiento de BAM existente. Los archivos de seguimiento de BAM están en un formato de archivo binario por lo que no se pueden editar y, en su lugar, se deben volver a generar. Si se requieren perfiles de seguimiento de BAM, es posible que sea necesario realizar una de las siguientes acciones:<br /><br /> -Evitar tener que actualizar con frecuencia los números de versión durante el proceso de compilación<br />-Retrasar la creación de perfiles de seguimiento hasta que los números de versión son estables de BAM|  
|Servicios Web publicados mediante el Asistente para publicación de servicios Web|Cuando el Asistente para publicación de Web Services se utiliza para generar una interfaz Web de ASP.NET, la versión del ensamblado del ensamblado de BizTalk Server se incluye en el código fuente ASP.NET. El número de versión de ensamblado se utiliza en tiempo de ejecución mediante la interfaz ASP.NET como parte de la propiedad de bodyTypeAssemblyQualifiedName de la operación del servicio Web. Si cambia el número de versión del ensamblado de BizTalk Server sin actualizar la propiedad de bodyTypeAssemblyQualifiedName, se rechazarán posteriores operaciones del servicio Web por BizTalk Server.<br /><br /> Si la ubicación de recepción utiliza XmlDefaultPipeline, la suscripción se basa en el tipo de documento. Utiliza la información de ensamblado integrada y si el ensamblado no existe, se producirán errores. Si utiliza PassThruPipeline (que es la opción predeterminada si expone un puerto y permite que el asistente cree la ubicación de recepción), la suscripción omite esta información de ensamblado integrada.|