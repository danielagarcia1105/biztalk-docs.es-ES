---
title: Importar aplicaciones PeopleSoft | Documentos de Microsoft
description: Usar un archivo de enlace XML para importar las aplicaciones de adaptador de PeopleSoft en BizTalk Server y leer todas las limitaciones al importar
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f53d1b4-e1df-41ff-b554-1bb1d20b9111
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed076bd238eff5106bb0b2f08449144d922fed4d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-biztalk-adapter-for-peoplesoft-enterprise"></a>Implementar el adaptador de BizTalk para PeopleSoft Enterprise
Esta sección proporciona información acerca de la implementación del adaptador de BizTalk para PeopleSoft Enterprise.  

## <a name="overview"></a>Información general
Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.  
  
 Utilice [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar las siguiente tareas:  
  
-   Implementar o quitar los ensamblados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una base de datos de configuración de BizTalk  
  
-   Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)  
  
-   Importar o exportar información de enlace de ensamblado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde archivos de enlace o a archivos de enlace.  
  
Usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).  
  
> [!NOTE]
>  El adaptador de Microsoft BizTalk para PeopleSoft Enterprise solo necesita que tenga Visual Studio en un equipo de origen (desarrollo). Visual Studio no es necesario en el equipo de producción.  

## <a name="confirm-your-setup"></a>Confirme la configuración
Antes de usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para importar un archivo de enlace, compruebe lo siguiente:  
  
-   CLASSPATH apunta a una ubicación concreta para los archivos específicos de PeopleSoft. Compruebe que la ubicación de estos archivos es el mismo en el nuevo equipo, o editar el archivo de enlace.  
  
-   Las carpetas para las respuestas deben existir y ser idénticas en el equipo nuevo, o editar el archivo de enlace.  
  
-   Las contraseñas del sistema PeopleSoft Enterprise, si están presentes en la configuración, se guardan como ***** en el archivo de enlace. Vea **limitaciones** en este tema.

> [!NOTE]
>  La implementación sobrescribe la configuración de la ubicación de recepción. Al implementar un archivo de enlace y un ensamblado en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.  
  
 Para obtener instrucciones paso a paso acerca de cómo importar archivos de enlace, vea [cómo importar enlaces en un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md). 
  
## <a name="clean-the-target-computer"></a>Limpiar el equipo de destino
Para limpiar el equipo de destino para la implementación de la nueva aplicación, quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.  
  
Si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no está instalado en el equipo de destino, puede ejecutar estos scripts para quitar los puertos:  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove enviar Port\VBScript\RemoveSendPort.vbs**  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove recibir Port\VBScript\RemoveReceivePort.vbs**  
  
Por ejemplo, en un símbolo del sistema, ejecute:  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a>Limitaciones
La contraseña del adaptador de transporte se almacena como asteriscos (*) en el archivo de enlace exportado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y pasa al componente de administración en el mismo formato.  
  
 Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte. También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación.  
  

### <a name="work-around-the-password-limitation"></a>Evitar la limitación de contraseña  

**opción 1**   
  
-   Antes de importar, actualice el archivo de enlace reemplazando los asteriscos por texto sin formato.  
  
    > [!CAUTION]
    >  No se recomienda por motivos de seguridad.  
  
-   Antes de importar, actualice el fileby enlace reemplace los asteriscos por un valor aleatorio (es decir, no la contraseña correcta). Después de importar, escriba la contraseña correcta en el **propiedades de transporte** en administración de BizTalk Server.  
  
    > [!NOTE]
    >  Esta solución solo puede utilizarse si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.  
  
**Opción 2**  
  
-   Use el inicio de sesión único (SSO) empresarial en lugar de utilizar contraseñas. El uso de la opción SSO requiere una importación del archivo de enlace.  
  
- Compruebe el sistema lógico y la transmisión y recepción de servicios. 
  
## <a name="next-steps"></a>Pasos siguientes
[Usar el control de excepciones de BizTalk Server en la orquestación](../core/using-biztalk-server-exception-handling2.md)