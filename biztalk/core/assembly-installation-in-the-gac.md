---
title: "Instalación de ensamblado en la GAC | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b12d00c-8750-4c6d-8244-e613f955a478
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e48ec0dddcf17be70b915d2beb058f1ab2f6f576
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="assembly-installation-in-the-gac"></a>Instalación de ensamblado en la GAC
Todos los equipos tienen una caché de ensamblados global (GAC) que contiene los ensamblados que una o varias aplicaciones del equipo usan. Para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procese mensajes durante el tiempo de ejecución, los ensamblados incluidos en una aplicación de BizTalk deben estar presente en las GAC de los equipos que ejecutan la aplicación.  
  
 Si la aplicación se encuentra aislada en un servidor, solo será necesario que haya ensamblados en la GAC de ese servidor. En cambio, cuando hay varios servidores que alojan la aplicación, los ensamblados de esa aplicación deben existir en la GAC de cada equipo que necesite obtener acceso a los artefactos que el ensamblado contiene. Por ejemplo, si implementa el ensamblado_a en el servidor_1 y, a continuación, dar de alta ensamblado_a en un host en el servidor_2, ensamblado_a debe instalarse en la GAC en el servidor_2. Si no es así, servidor_2 no podrá tener acceso al ensamblado_a durante el tiempo de ejecución.  
  
 En concreto, los ensamblados que contienen orquestaciones y ensamblados de los que dependen siempre deben estar instalados en la GAC de los servidores que ejecutan instancias del host al que la orquestación está enlazada. Además, los ensamblados que contienen las asignaciones y las canalizaciones que un puerto usa deben estar instalados en los servidores que ejecutan instancias del host que hace de controlador de adaptador para el puerto.  
  
 Puede especificar una opción de implementación para cada ensamblado con el fin de instalarlo en la GAC cuando implemente el ensamblado desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. De forma alternativa, puede instalar ensamblados en la GAC de forma manual. Además, puede especificar opciones de implementación para instalar el ensamblado en la GAC después de que se implemente en una aplicación de BizTalk.  
  
 A continuación, se resumen las herramientas y los métodos disponibles para instalar ensamblados en la GAC:  
  
-   **Microsoft Visual Studio.** Como se mencionó anteriormente, puede establecer propiedades del proyecto para instalar ensamblados en la GAC automáticamente cuando las implemente, como se describe en [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md). Puede instalar manualmente los ensamblados en la GAC mediante el uso de la herramienta de línea de comandos Gacutil incluida con [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [cómo instalar un ensamblado en la GAC](../core/how-to-install-an-assembly-in-the-gac.md).  
  
-   **Herramienta de línea de comandos BTSTask.** Cuando se agrega un ensamblado a una aplicación de BizTalk mediante BTSTask, puede especificar las opciones para instalar el ensamblado en la GAC cuando se importa o instala la aplicación que contiene. Para obtener más información, consulte [comando AddResource: ensamblado de BizTalk](../core/addresource-command-biztalk-assembly.md). Consulte también [comando AddResource: ensamblado .NET](../core/addresource-command-net-assembly.md).  
  
-   **Consola de administración de BizTalk Server.** De la misma manera que con BTSTask, cuando se agrega un ensamblado a una aplicación mediante la consola de administración, puede especificar las opciones para instalar un ensamblado en la GAC cuando se importa o instala la aplicación que contiene. Para obtener más información, consulte [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md). Consulte también [cómo agregar un ensamblado de .NET a una aplicación](../core/how-to-add-a-net-assembly-to-an-application.md).  
  
     Además, puede configurar opciones de implementación en cualquier momento después de que se ha implementado en un ensamblado o se ha agregado a una aplicación, como se describe en [cómo modificar las opciones de implementación de un ensamblado de BizTalk](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md). Cuando los ensamblados se implementan en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] por primera vez, se establecen las opciones de implementación en la consola de administración como se indica a continuación: está habilitado en la instalación y se deshabilita la GAC durante la importación. Si realiza cambios en esta configuración, los cambios seguirán en vigor si se vuelve a implementar el ensamblado de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
-   **Arrastrar y colocar.** Mediante el Explorador de Windows, puede arrastrar y colocar el archivo de ensamblado en el \< *carpeta Windows*> \assembly.  
  
-   **Otros métodos.** Existen otras herramientas y métodos, como el instalador de Windows o herramientas de otros proveedores, que se pueden usar para instalar un ensamblado en la GAC.  
  
> [!IMPORTANT]
>  Para que la aplicación funcione correctamente, asegúrese de que las versiones de los ensamblados son las mismas en la base de datos de administración de BizTalk y en la GAC. Si sigue el procedimiento de no instalar siempre un ensamblado en la GAC cuando lo implementa, es posible que tenga diferentes versiones en la GAC y en la base de datos de administración de BizTalk, hecho que producirá errores de procesamiento durante el tiempo de ejecución.  
  
> [!IMPORTANT]
>  Para obtener información acerca de la numeración de versiones, vea el tema sobre versiones de ensamblados en la ayuda de .NET Framework disponible en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Tenga en cuenta que el uso de archivos de directiva de .NET no es compatible con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [Descripción de la implementación de aplicaciones de BizTalk y administración](../core/understanding-biztalk-application-deployment-and-management.md)