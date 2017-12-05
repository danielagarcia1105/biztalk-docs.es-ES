---
title: Importar enlaces para TIBCO Rendezvous | Documentos de Microsoft
description: "Implementar el adaptador de BizTalk para aplicaciones de TIBCO Rendezvous mediante la característica Importar enlaces en BizTalk Server"
ms.custom: 
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec5751a9-0a08-4cf8-a3ef-e51e488a4180
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dab62d7d7836a59c66329c2c58f7768bc481c036
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="deploy-tibco-rendezvous-ports-and-assemblies"></a>Implementar ensamblados y puertos de TIBCO Rendezvous
  
## <a name="overview"></a>Información general
Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino. El asistente exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.  
  
 Mediante BizTalk Server se pueden realizar las tareas siguientes:  
  
-   Implementar o quitar ensamblados de BizTalk Server en una base de datos de configuración de BizTalk.  
  
-   Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)  
  
-   Importar o exportar información de enlace de ensamblado de BizTalk Server desde archivos de enlace o a archivos de enlace.  
  
 Para obtener información sobre cómo usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).  
  
> [!NOTE]
>  El adaptador de Microsoft BizTalk para TIBCO Rendezvous solo necesita que tenga Visual Studio en un equipo de origen (desarrollo). Visual Studio no es necesario en el equipo de producción.  

## <a name="confirm-your-setup"></a>Confirme la configuración

Antes de usar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para importar un archivo de enlace, confirme que las carpetas para las respuestas existen y que son idénticas en el nuevo equipo o debe editar el archivo de enlace.  
  
## <a name="clean-the-target-computer"></a>Limpiar el equipo de destino
Implementación sobrescribe la configuración de la ubicación de recepción. Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los en el archivo de enlace XML cuando se importan.  
  
Antes de importar, quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.  
  
Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
Por ejemplo, en un símbolo del sistema, ejecute:  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="next-steps"></a>Pasos siguientes
[Usar el control de excepciones de BizTalk Server en la orquestación](../core/using-biztalk-server-exception-handling4.md)  
[Solucionar problemas](../core/troubleshooting-tibco-rendezvous.md)