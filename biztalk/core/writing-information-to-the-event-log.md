---
title: "Escribir información en el registro de eventos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d7398dc-29d8-4a7a-bab4-c8f128b47dca
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f848cafd6ee9247511db3b9a6dad7dc5da91236b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="writing-information-to-the-event-log"></a><span data-ttu-id="1bdb2-102">Escribir información en el registro de eventos</span><span class="sxs-lookup"><span data-stu-id="1bdb2-102">Writing Information to the Event Log</span></span>
<span data-ttu-id="1bdb2-103">Puede ser interesante supervisar el progreso de los distintos procesos empresariales con la aplicación de BizTalk escribiendo información en el registro de aplicaciones predeterminado o en un registro de eventos personalizado.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-103">You may want to monitor the progress of the different business processes within your BizTalk application by writing information to the default Application log or to a custom event log.</span></span> <span data-ttu-id="1bdb2-104">Escribir en el registro de eventos puede resultar de utilidad en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="1bdb2-104">Writing to the event log can be useful in the following scenarios:</span></span>  
  
-   <span data-ttu-id="1bdb2-105">Si desea tener acceso a los mensajes de la aplicación de una manera estándar con las herramientas proporcionadas por Windows.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-105">You want to access application messages in a standard way using tools supplied by Windows.</span></span>  
  
-   <span data-ttu-id="1bdb2-106">Si desea archivar información con otros mensajes del entorno de servidor para conservar un historial más completo.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-106">You want to archive information with other messages from the server environment for a more complete history.</span></span>  
  
-   <span data-ttu-id="1bdb2-107">Si desea poder supervisar la aplicación mediante herramientas que interactúan con el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-107">You want the ability to monitor your application using tools that interact with the event log.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bdb2-108">El método System.Diagnostics.EventLog.WriteEntry tiene una limitación de tamaño en la cadena de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-108">The System.Diagnostics.EventLog.WriteEntry method has a size limitation on the message string.</span></span> <span data-ttu-id="1bdb2-109">Recibirá una excepción cuando la cadena de mensaje supere los 32.766 bytes.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-109">You will receive exception if the message string exceeds 32766 bytes.</span></span>  
  
## <a name="writing-to-the-application-log"></a><span data-ttu-id="1bdb2-110">Escribir en el registro de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1bdb2-110">Writing to the Application Log</span></span>  
 <span data-ttu-id="1bdb2-111">Puede escribir en el registro de aplicación o cualquier otro registro desde el código mediante el uso de **System.Diagnostics.EventLog** tal y como se muestra en la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1bdb2-111">You can write to the Application log or any other log from your code by using **System.Diagnostics.EventLog** as shown in the following:</span></span>  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 <span data-ttu-id="1bdb2-112">De manera similar, también puede hacerlo así:</span><span class="sxs-lookup"><span data-stu-id="1bdb2-112">Similar, you can also do,</span></span>  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 <span data-ttu-id="1bdb2-113">Si usas un registro personalizado, debe utilizar el **SourceExists** método para asegurarse de que existe antes de escribir en él.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-113">If you are using a custom log, you should use the **SourceExists** method to ensure it exists before you write to it.</span></span>  
  
## <a name="writing-to-a-custom-log"></a><span data-ttu-id="1bdb2-114">Escribir en un registro personalizado</span><span class="sxs-lookup"><span data-stu-id="1bdb2-114">Writing to a Custom Log</span></span>  
 <span data-ttu-id="1bdb2-115">Escribir en un registro personalizado es parecido a hacerlo en el registro de aplicaciones, excepto en que el primero tiene que crearlo antes.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-115">Writing to a custom log is similar to writing to the Application log with the exception that you must first create the custom log.</span></span> <span data-ttu-id="1bdb2-116">El código para crear un registro personalizado es sencillo:</span><span class="sxs-lookup"><span data-stu-id="1bdb2-116">The code to create a custom log is straightforward:</span></span>  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 <span data-ttu-id="1bdb2-117">Sin embargo, no hay que dar por hecho que el código se vaya a ejecutar en una cuenta que dispone de los privilegios de seguridad necesarios para crear un registro de eventos nuevo.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-117">However, you should not assume that your code will be run under an account that has the security privileges to create a new event log.</span></span> <span data-ttu-id="1bdb2-118">Crear un registro de eventos requiere privilegios de administrador y debe realizarse en una utilidad independiente o, en el mejor de los casos, como parte de una instalación .msi.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-118">Creating an event log takes administrator privileges and should be done in a separate utility program or, ideally, as part of an .msi installation.</span></span> <span data-ttu-id="1bdb2-119">Para obtener más información sobre el uso de un script personalizado con una instalación de .msi exportada, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="1bdb2-119">For more information about using custom script with an exported .msi installation, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>