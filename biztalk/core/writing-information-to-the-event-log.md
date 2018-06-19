---
title: Escribir información en el registro de eventos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d7398dc-29d8-4a7a-bab4-c8f128b47dca
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f848cafd6ee9247511db3b9a6dad7dc5da91236b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289580"
---
# <a name="writing-information-to-the-event-log"></a>Escribir información en el registro de eventos
Puede ser interesante supervisar el progreso de los distintos procesos empresariales con la aplicación de BizTalk escribiendo información en el registro de aplicaciones predeterminado o en un registro de eventos personalizado. Escribir en el registro de eventos puede resultar de utilidad en los escenarios siguientes:  
  
-   Si desea tener acceso a los mensajes de la aplicación de una manera estándar con las herramientas proporcionadas por Windows.  
  
-   Si desea archivar información con otros mensajes del entorno de servidor para conservar un historial más completo.  
  
-   Si desea poder supervisar la aplicación mediante herramientas que interactúan con el registro de eventos.  
  
> [!NOTE]
>  El método System.Diagnostics.EventLog.WriteEntry tiene una limitación de tamaño en la cadena de mensaje. Recibirá una excepción cuando la cadena de mensaje supere los 32.766 bytes.  
  
## <a name="writing-to-the-application-log"></a>Escribir en el registro de aplicaciones  
 Puede escribir en el registro de aplicación o cualquier otro registro desde el código mediante el uso de **System.Diagnostics.EventLog** tal y como se muestra en la siguiente:  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 De manera similar, también puede hacerlo así:  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 Si usas un registro personalizado, debe utilizar el **SourceExists** método para asegurarse de que existe antes de escribir en él.  
  
## <a name="writing-to-a-custom-log"></a>Escribir en un registro personalizado  
 Escribir en un registro personalizado es parecido a hacerlo en el registro de aplicaciones, excepto en que el primero tiene que crearlo antes. El código para crear un registro personalizado es sencillo:  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 Sin embargo, no hay que dar por hecho que el código se vaya a ejecutar en una cuenta que dispone de los privilegios de seguridad necesarios para crear un registro de eventos nuevo. Crear un registro de eventos requiere privilegios de administrador y debe realizarse en una utilidad independiente o, en el mejor de los casos, como parte de una instalación .msi. Para obtener más información sobre el uso de un script personalizado con una instalación de .msi exportada, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).