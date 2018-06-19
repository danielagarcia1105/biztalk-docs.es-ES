---
title: Solucionar problemas de Windows SharePoint Services | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9acf9a0d-2c92-4227-80f8-b2d0cca0c232
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51243216f2adb73454477252c7b54358df229610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286996"
---
# <a name="troubleshooting-windows-sharepoint-services"></a><span data-ttu-id="b8b77-102">Solucionar problemas de Windows Sharepoint Services</span><span class="sxs-lookup"><span data-stu-id="b8b77-102">Troubleshooting Windows SharePoint Services</span></span>
<span data-ttu-id="b8b77-103">El adaptador Windows SharePoint Services usa Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8b77-103">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] is used by the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="b8b77-104">En este tema se explican algunos problemas conocidos que se pueden encontrar con Windows SharePoint Services y las posibles soluciones a estos problemas.</span><span class="sxs-lookup"><span data-stu-id="b8b77-104">This topic describes some known issues that may be encountered with Windows SharePoint Services and possible resolutions to these issues.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="b8b77-105">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b8b77-105">Known Issues</span></span>  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a><span data-ttu-id="b8b77-106">Se produce un error de inicio de sesión del usuario 'NT AUTHORITY\NETWORK SERVICE' al intentar crear una base de datos de contenido</span><span class="sxs-lookup"><span data-stu-id="b8b77-106">Login failed for user 'NT AUTHORITY\NETWORK SERVICE' error occurs when attempting to create content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="b8b77-107">Problema</span><span class="sxs-lookup"><span data-stu-id="b8b77-107">Problem</span></span>  
 <span data-ttu-id="b8b77-108">Cuando se intenta crear una base de datos de contenido mediante el sitio Web de Administración central de SharePoint, se muestra un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8b77-108">When you attempt to create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="b8b77-109">Error de inicio de sesión del usuario 'NT AUTHORITY\NETWORK SERVICE'</span><span class="sxs-lookup"><span data-stu-id="b8b77-109">Login failed for user 'NT AUTHORITY\NETWORK SERVICE'</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="b8b77-110">Causa</span><span class="sxs-lookup"><span data-stu-id="b8b77-110">Cause</span></span>  
 <span data-ttu-id="b8b77-111">Este problema se produce cuando el propietario de la base de datos a la que se está conectando no coincide con la identidad del grupo de aplicaciones en la que se está ejecutando Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="b8b77-111">This issue occurs when the database owner of the database that you are connecting to is different from the application pool identity that Windows SharePoint Services is running under.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="b8b77-112">Solución</span><span class="sxs-lookup"><span data-stu-id="b8b77-112">Resolution</span></span>  
 <span data-ttu-id="b8b77-113">Para resolver este problema, realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b8b77-113">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="b8b77-114">Conceder a la cuenta de servicio de red derechos de creación de bases de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8b77-114">Grant the NETWORK SERVICE account "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="b8b77-115">Cambiar la cuenta de la identidad del grupo de aplicaciones por una cuenta que tenga derechos de creación de bases de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8b77-115">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a><span data-ttu-id="b8b77-116">Se produce un error de tipo "Servicio no disponible" al obtener acceso al sitio Web de Administración central de SharePoint</span><span class="sxs-lookup"><span data-stu-id="b8b77-116">"Service Unavailable" error occurs when accessing the SharePoint Central Administration Web site</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="b8b77-117">Problema</span><span class="sxs-lookup"><span data-stu-id="b8b77-117">Problem</span></span>  
 <span data-ttu-id="b8b77-118">Cuando se intenta abrir el sitio Web de Administración central de SharePoint, se muestra un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8b77-118">When you attempt to open the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="b8b77-119">Servicio no disponible</span><span class="sxs-lookup"><span data-stu-id="b8b77-119">Service Unavailable</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="b8b77-120">Causa</span><span class="sxs-lookup"><span data-stu-id="b8b77-120">Cause</span></span>  
 <span data-ttu-id="b8b77-121">La causa más frecuente de este error es que se detiene el grupo de aplicaciones (IIS 6.0 o IIS 7.0) o la aplicación COM+ (IIS 5.x) de hospedaje del sitio web de Administración central de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b8b77-121">The most common cause for this error is that the application pool (IIS 6.0 or IIS 7.0) or hosting COM+ application (IIS 5.x) for the SharePoint Central Administration Web site is stopped.</span></span> <span data-ttu-id="b8b77-122">Esto suele ocurrir si el grupo de aplicaciones o la aplicación COM+ está configurada con una identidad para la que la contraseña o el nombre de usuario especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="b8b77-122">This commonly occurs if the application pool or COM+ application is configured with an identity for which the specified user name and/or password is invalid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="b8b77-123">Solución</span><span class="sxs-lookup"><span data-stu-id="b8b77-123">Resolution</span></span>  
 <span data-ttu-id="b8b77-124">Siga los pasos descritos en la sección "Identidad de proceso de Host de configuración IIS aplicación" del tema [directrices para resolver problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md) para establecer la identidad del proceso de host correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b8b77-124">Follow the steps in the "Setting IIS Application Host Process Identity" section of the topic [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to set the appropriate host process identity.</span></span>  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a><span data-ttu-id="b8b77-125">Se produce un error de tipo "No se puede conectar a la base de datos de configuración" al intentar expandir y crear una base de datos de contenido</span><span class="sxs-lookup"><span data-stu-id="b8b77-125">"Cannot connect to the configuration database" error occurs when attempting to extend and create a content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="b8b77-126">Problema</span><span class="sxs-lookup"><span data-stu-id="b8b77-126">Problem</span></span>  
 <span data-ttu-id="b8b77-127">Cuando se intenta expandir y crear una base de datos de contenido mediante el sitio Web de Administración central de SharePoint, se muestra un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8b77-127">When you attempt to extend and create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="b8b77-128">No se puede conectar a la base de datos de configuración</span><span class="sxs-lookup"><span data-stu-id="b8b77-128">Cannot connect to the configuration database</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="b8b77-129">Causa</span><span class="sxs-lookup"><span data-stu-id="b8b77-129">Cause</span></span>  
 <span data-ttu-id="b8b77-130">Este problema se produce cuando la cuenta que usa el grupo de aplicaciones que está ejecutando el sitio Web de Administración central de SharePoint no tiene los permisos necesarios para la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8b77-130">This issue occurs when the account that is used by the application pool that is running the SharePoint Central Administration Web site does not have the required permissions to the SQL Server database.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="b8b77-131">Solución</span><span class="sxs-lookup"><span data-stu-id="b8b77-131">Resolution</span></span>  
 <span data-ttu-id="b8b77-132">Para resolver este problema, realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b8b77-132">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="b8b77-133">Conceder a la cuenta que usa el grupo de aplicaciones para el sitio Web de Administración central de SharePoint derechos de creación de bases de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8b77-133">Grant the account that is used by the application pool for the SharePoint Central Administration Web site "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="b8b77-134">Cambiar la cuenta de la identidad del grupo de aplicaciones por una cuenta que tenga derechos de creación de bases de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8b77-134">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a><span data-ttu-id="b8b77-135">En el registro de aplicaciones se produce el error "No se pudo iniciar el servicio Temporizador de extensiones de SharePoint" tras reiniciar el servidor</span><span class="sxs-lookup"><span data-stu-id="b8b77-135">"The SharePoint Timer Service service failed to start" error is generated in the Application log after rebooting server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="b8b77-136">Problema</span><span class="sxs-lookup"><span data-stu-id="b8b77-136">Problem</span></span>  
 <span data-ttu-id="b8b77-137">Tras reiniciar el servidor, aparece el siguiente error en los registros de eventos:</span><span class="sxs-lookup"><span data-stu-id="b8b77-137">After restarting the server, you see the following error in the event logs:</span></span>  
  
 <span data-ttu-id="b8b77-138">No se pudo iniciar el servicio Temporizador de extensiones de SharePoint</span><span class="sxs-lookup"><span data-stu-id="b8b77-138">The SharePoint Timer Service service failed to start</span></span>  
  
 <span data-ttu-id="b8b77-139">Es posible que aparezca también el error siguiente cuando se abra el sitio Web de Administración central de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="b8b77-139">You may also see the following error when you open the SharePoint Central Administration site:</span></span>  
  
 <span data-ttu-id="b8b77-140">No se puede establecer conexión con la base de datos de configuración de WSS STS_Config</span><span class="sxs-lookup"><span data-stu-id="b8b77-140">Unable to connect to the WSS configuration database STS_Config</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="b8b77-141">Causa</span><span class="sxs-lookup"><span data-stu-id="b8b77-141">Cause</span></span>  
 <span data-ttu-id="b8b77-142">Este error se produce cuando el servicio Temporizador de extensiones de SharePoint no puede establecer conexión con la base de datos de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] después de reiniciar.</span><span class="sxs-lookup"><span data-stu-id="b8b77-142">This error occurs when the SharePoint Timer service fails to contact the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] database after rebooting.</span></span> <span data-ttu-id="b8b77-143">El servicio Temporizador de extensiones de SharePoint se usa para enviar notificaciones y realizar las tareas programadas de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8b77-143">The SharePoint Timer service is used to send notifications and perform scheduled tasks for [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span> <span data-ttu-id="b8b77-144">La razón más común de que el servicio Temporizador de extensiones de SharePoint no se pueda iniciar es que la cuenta que se usa para ejecutar el servicio está configurada con una identidad para la que el nombre de usuario o la contraseña ya no es válido.</span><span class="sxs-lookup"><span data-stu-id="b8b77-144">The most common reason that the SharePoint Timer service fails to start is that the account used to run the service is configured with an identity for which the user name and/or password are no longer valid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="b8b77-145">Solución</span><span class="sxs-lookup"><span data-stu-id="b8b77-145">Resolution</span></span>  
 <span data-ttu-id="b8b77-146">Asegúrese de que el nombre de usuario y la contraseña especificados para la cuenta de inicio de sesión del servicio Temporizador de extensiones de SharePoint sean correctos y de que se haya iniciado el servicio.</span><span class="sxs-lookup"><span data-stu-id="b8b77-146">Ensure that the user name and password specified for the SharePoint Timer service logon account are correct and that the service has been started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b77-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8b77-147">See Also</span></span>  
 <span data-ttu-id="b8b77-148">[Cómo configurar un servidor virtual de Windows SharePoint Services](http://support.microsoft.com/kb/832769) </span><span class="sxs-lookup"><span data-stu-id="b8b77-148">[How to configure a Windows SharePoint Services virtual server](http://support.microsoft.com/kb/832769) </span></span>  
 <span data-ttu-id="b8b77-149">[Cómo realizar copias de y restaurar las instalaciones de Windows SharePoint Services que usan Microsoft SQL Server 2000 Desktop Engine (Windows)](http://support.microsoft.com/kb/833797) </span><span class="sxs-lookup"><span data-stu-id="b8b77-149">[How to back up and restore installations of Windows SharePoint Services that use Microsoft SQL Server 2000 Desktop Engine (Windows)](http://support.microsoft.com/kb/833797) </span></span>  
 <span data-ttu-id="b8b77-150">[Recibirá un mensaje de error "No se puede conectar a la base de datos de configuración" cuando se conecta a su sitio Web de Windows SharePoint Services](http://support.microsoft.com/kb/823287) </span><span class="sxs-lookup"><span data-stu-id="b8b77-150">[You receive a "Cannot connect to the configuration database" error message when you connect to your Windows SharePoint Services Web site](http://support.microsoft.com/kb/823287) </span></span>  
 <span data-ttu-id="b8b77-151">[Recibirá un mensaje de Error "Servicio no disponible" al examinar un sitio Web de Windows SharePoint Services](http://support.microsoft.com/kb/823552) </span><span class="sxs-lookup"><span data-stu-id="b8b77-151">[You Receive a "Service Unavailable" Error Message When You Browse a Windows SharePoint Services Web Site](http://support.microsoft.com/kb/823552) </span></span>  
 [<span data-ttu-id="b8b77-152">Recibirá un mensaje de error "Database < nombreDeBaseDeDatos > ya existe" cuando se administra la base de datos de contenido de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="b8b77-152">You receive a "Database <Database_Name> already exists" error message when you manage your Windows SharePoint Services content database</span></span>](http://support.microsoft.com/kb/828815)