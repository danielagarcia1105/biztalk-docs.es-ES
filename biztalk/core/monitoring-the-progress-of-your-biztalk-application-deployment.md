---
title: "Supervisar el progreso de la implementación de aplicaciones de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring, deploying
- applications, monitoring
- deploying [applications], monitoring
- monitoring, applications
ms.assetid: a69a8288-0203-440f-9805-52786525e193
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eaa81067f5a413c689a4a51ac6b102d80782e2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a><span data-ttu-id="6b1e5-102">Supervisar el progreso de implementación de la aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6b1e5-102">Monitoring the Progress of Your BizTalk Application Deployment</span></span>
<span data-ttu-id="6b1e5-103">Es posible supervisar el progreso de implementación de la aplicación de BizTalk de dos formas:</span><span class="sxs-lookup"><span data-stu-id="6b1e5-103">You can monitor the progress of your BizTalk application deployment in two ways:</span></span>  
  
-   <span data-ttu-id="6b1e5-104">**Registro de instalación de BizTalk**: puede consultar la instalación de registro que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-104">**BizTalk installation log**: You can consult the installation log that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates.</span></span> <span data-ttu-id="6b1e5-105">Los registros de instalación se encuentran en %SystemDrive%\Documents and Settings\\<*usuario actual*> \Application Data\Microsoft\\[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]\Deployment.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-105">Installation logs are located in %SystemDrive%\Documents and Settings\\<*current user*>\Application Data\Microsoft\\[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]\Deployment.</span></span>  
  
-   <span data-ttu-id="6b1e5-106">**Registro de eventos local**: puede realizar un seguimiento del progreso de una instalación en el registro de eventos local.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-106">**Local event log**: You can track the progress of an installation in the local event log.</span></span> <span data-ttu-id="6b1e5-107">Por lo tanto, puede hacer un seguimiento de las acciones de instalación personalizadas servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-107">Therefore, you can track custom installation actions on a per-server basis.</span></span>  
  
-   <span data-ttu-id="6b1e5-108">**Registro de Windows Installer**: Microsoft Windows Installer crea un archivo de registro en el equipo local que registra las acciones de una acción personalizada.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-108">**Windows Installer log**: Microsoft Windows Installer creates a log file on the local computer that logs the actions of a custom action.</span></span> <span data-ttu-id="6b1e5-109">Puede especificar este archivo de registro mediante la opción /log del comando msiexec.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-109">You can specify this log file by using the /log option of the msiexec command.</span></span> <span data-ttu-id="6b1e5-110">Para obtener más información, consulte la documentación de Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-110">For more information, see the documentation for Windows Installer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b1e5-111">Al implementar o anular la implementación de un esquema de propiedades, se pueden exponer datos confidenciales y, por lo tanto, información confidencial durante el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-111">Deploying or undeploying a property schema may expose sensitive data, and subsequently expose sensitive information during tracking.</span></span> <span data-ttu-id="6b1e5-112">Siempre que se implemente o se anule la implementación de un ensamblado que contenga un esquema de propiedades, el visor de eventos registrará un evento en el registro de eventos de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-112">Whenever an assembly containing a property schema is deployed or undeployed, the event viewer logs an event in the Windows Application Event Log.</span></span> <span data-ttu-id="6b1e5-113">Debería comprobar el registro de eventos de estos mensajes para asegurarse de que todas las actividades de implementación de ensamblados están en línea con las directivas de datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="6b1e5-113">You should check the event log for these messages to ensure that all assembly deployment activities are in line with your policies for any sensitive data.</span></span> <span data-ttu-id="6b1e5-114">(El mensaje generado en el registro de eventos para la implementación es: "el usuario"{{1}"implementado el ensamblado"{0}"que contiene esquemas de propiedad".</span><span class="sxs-lookup"><span data-stu-id="6b1e5-114">(The message generated to the Event Log for deployment is: "The user "{1}" deployed the assembly "{0}" containing property schemas."</span></span> <span data-ttu-id="6b1e5-115">El mensaje generado en el registro de eventos para la anulación es: "el usuario"{{1}"anularse el ensamblado que contiene esquemas de propiedad" {0}".")</span><span class="sxs-lookup"><span data-stu-id="6b1e5-115">The message generated to the Event Log for undeployment is: "The user "{1}" undeployed the assembly "{0}" containing property schemas.")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b1e5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b1e5-116">See Also</span></span>  
 [<span data-ttu-id="6b1e5-117">Implementar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6b1e5-117">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)