---
title: "Importación de enlace Files1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- CLASSPATH environment variable
- importing binding files
- cleaning target computer
ms.assetid: b2a9b19b-2d3d-45ea-bd92-a2501791b86a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fca64580b692f01834b48085aa2d88085fb743
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a>Importar archivos de enlace
Antes de usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para importar un archivo de enlace, compruebe lo siguiente:  
  
-   CLASSPATH apunta a una ubicación concreta para los archivos específicos de PeopleSoft. Compruebe que la ubicación de estos archivos es el mismo en el nuevo equipo, o editar el archivo de enlace.  
  
-   Las carpetas para las respuestas deben existir y ser idénticas en el equipo nuevo, o editar el archivo de enlace.  
  
-   Las contraseñas del sistema PeopleSoft Enterprise, si están presentes en la configuración, se guardan como ***** en el archivo de enlace. Para obtener más información, consulte [limitaciones de la implementación](../core/deployment-limitations3.md).  
  
> [!NOTE]
>  La implementación sobrescribe la configuración de la ubicación de recepción. Al implementar un archivo de enlace y un ensamblado en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.  
  
 Para obtener instrucciones detalladas sobre la importación de archivos de enlace, consulte el tema "Cómo importar enlaces a un grupo de BizTalk" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="cleaning-the-target-computer"></a>Limpiar el equipo de destino  
 Para limpiar el equipo de destino e implementar la nueva aplicación, lleve a cabo los pasos siguientes.  
  
#### <a name="to-clean-the-target-computer"></a>Para limpiar el equipo de destino  
  
-   Quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.  
  
     Si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no está instalado en el equipo de destino, puede ejecutar estos scripts para quitar los puertos:  
  
     **\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove enviar Port\VBScript\RemoveSendPort.vbs**  
  
     **\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove recibir Port\VBScript\RemoveReceivePort.vbs**  
  
     Por ejemplo, en un símbolo del sistema, ejecute:  
  
     **cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío >**  
  
## <a name="see-also"></a>Vea también  
 [Implementación de puertos y ensamblados](../core/deploying-ports-and-assemblies5.md)