---
title: Solución de problemas de Internet Information Services | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f77084f1-5797-42ab-bbf6-fe815144232e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f7ca928aa2e47b5c62548aba02834b96d6a3baf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006661"
---
# <a name="troubleshooting-internet-information-services"></a><span data-ttu-id="4cfd5-102">Solución de problemas de Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="4cfd5-102">Troubleshooting Internet Information Services</span></span>
<span data-ttu-id="4cfd5-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa mucho Microsoft Internet Information Services (IIS) para diversas funcionalidades, incluidos los adaptadores de HTTP, SOAP y Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-103">Microsoft Internet Information Services (IIS) is used extensively by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for various functionality including the HTTP, SOAP, and Windows SharePoint Services adapters.</span></span> <span data-ttu-id="4cfd5-104">En esta tema se explican algunos problemas conocidos que se puede encontrar en IIS y las posibles soluciones a estos problemas.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-104">This topic describes some known issues that you may encounter with IIS and possible resolutions to these issues.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="4cfd5-105">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="4cfd5-105">Known Issues</span></span>  
 <span data-ttu-id="4cfd5-106">Es posible que los errores incluidos en este tema no se muestren a menos que configure Internet Explorer para que deshabilite los mensajes de error descriptivos de HTTP.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-106">The errors documented in this topic may not be displayed unless you configure Internet Explorer to disable friendly HTTP error messages.</span></span>  
  
#### <a name="to-configure-internet-explorer-to-disable-friendly-http-error-messages"></a><span data-ttu-id="4cfd5-107">Para configurar Internet Explorer de modo que deshabilite los mensajes de error descriptivos de HTTP</span><span class="sxs-lookup"><span data-stu-id="4cfd5-107">To configure Internet Explorer to disable friendly HTTP error messages</span></span>  
  
1.  <span data-ttu-id="4cfd5-108">En el **herramientas** menú, haga clic en **opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-108">On the **Tools** menu, click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="4cfd5-109">En el **avanzadas** ficha la **exploración** sección, desactive la **mostrar mensajes de error HTTP descriptivos** casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-109">On the **Advanced** tab, in the **Browsing** section, clear the **Show friendly HTTP error messages** check box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="4cfd5-110">Cierre Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-110">Close Internet Explorer.</span></span>  
  
#### <a name="http-404---file-not-found-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="4cfd5-111">Al obtener acceso a una página web en un servidor IIS, se produce el error “HTTP 404 – Archivo no encontrado”</span><span class="sxs-lookup"><span data-stu-id="4cfd5-111">"HTTP 404 - File not found" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="4cfd5-112">Problema</span><span class="sxs-lookup"><span data-stu-id="4cfd5-112">Problem</span></span>  
 <span data-ttu-id="4cfd5-113">Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-113">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="4cfd5-114">No se encontró la página</span><span class="sxs-lookup"><span data-stu-id="4cfd5-114">Page Cannot Be Found</span></span>  
  
 <span data-ttu-id="4cfd5-115">\- O bien</span><span class="sxs-lookup"><span data-stu-id="4cfd5-115">\- or -</span></span>  
  
 <span data-ttu-id="4cfd5-116">HTTP 404 – Archivo no encontrado</span><span class="sxs-lookup"><span data-stu-id="4cfd5-116">HTTP 404 - File not found</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="4cfd5-117">Causa</span><span class="sxs-lookup"><span data-stu-id="4cfd5-117">Cause</span></span>  
 <span data-ttu-id="4cfd5-118">Este error puede producirse por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-118">This error may occur for the following reasons:</span></span>  
  
-   <span data-ttu-id="4cfd5-119">Se ha cambiado el nombre del servicio solicitado.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-119">The requested file has been renamed.</span></span>  
  
-   <span data-ttu-id="4cfd5-120">El archivo solicitado se ha movido a otra ubicación o se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-120">The requested file has been moved to another location or deleted.</span></span>  
  
-   <span data-ttu-id="4cfd5-121">El archivo solicitado no está disponible temporalmente debido a mantenimiento, actualizaciones u otros motivos desconocidos.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-121">The requested file is temporarily unavailable due to maintenance, upgrades, or other unknown causes.</span></span>  
  
-   <span data-ttu-id="4cfd5-122">El archivo solicitado no existe.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-122">The requested file does not exist.</span></span>  
  
-   <span data-ttu-id="4cfd5-123">IIS 6.0: el tipo MIME o la extensión de servicio Web adecuada no están habilitados.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-123">IIS 6.0: The appropriate Web service extension or MIME type is not enabled.</span></span>  
  
-   <span data-ttu-id="4cfd5-124">Un directorio virtual se asigna a la raíz de una unidad en otro servidor.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-124">A virtual directory is mapped to the root of a drive on another server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="4cfd5-125">Solución</span><span class="sxs-lookup"><span data-stu-id="4cfd5-125">Resolution</span></span>  
 <span data-ttu-id="4cfd5-126">Siga los pasos descritos en la sección de solución de Microsoft Knowledge Base artículo 248033, "razones comunes por IIS Server devuelve el error"HTTP 404 – archivo no encontrado"" disponible en [ http://support.microsoft.com/kb/248033 ](http://support.microsoft.com/kb/248033).</span><span class="sxs-lookup"><span data-stu-id="4cfd5-126">Follow the steps in the RESOLUTION section of Microsoft Knowledge Base article 248033, "Common reasons IIS Server returns "HTTP 404 - File not found" error" available at [http://support.microsoft.com/kb/248033](http://support.microsoft.com/kb/248033).</span></span>  
  
#### <a name="cannot-find-server-or-dns-error-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="4cfd5-127">Al obtener acceso a una página web en un servidor IIS, se produce el error “No se pudo encontrar el servidor o error DNS”</span><span class="sxs-lookup"><span data-stu-id="4cfd5-127">"Cannot find server or DNS Error error" occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="4cfd5-128">Problema</span><span class="sxs-lookup"><span data-stu-id="4cfd5-128">Problem</span></span>  
 <span data-ttu-id="4cfd5-129">Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-129">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="4cfd5-130">No se puede mostrar la página</span><span class="sxs-lookup"><span data-stu-id="4cfd5-130">The Page Cannot Be Displayed</span></span>  
  
 <span data-ttu-id="4cfd5-131">\- O bien</span><span class="sxs-lookup"><span data-stu-id="4cfd5-131">\- or -</span></span>  
  
 <span data-ttu-id="4cfd5-132">No se pudo encontrar el servidor o error DNS</span><span class="sxs-lookup"><span data-stu-id="4cfd5-132">Cannot find server or DNS Error</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="4cfd5-133">Causa</span><span class="sxs-lookup"><span data-stu-id="4cfd5-133">Cause</span></span>  
 <span data-ttu-id="4cfd5-134">Este error puede producirse por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-134">This error may occur for the following reasons:</span></span>  
  
-   <span data-ttu-id="4cfd5-135">Su configuración de conexión de Internet Explorer es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-135">Your Internet Explorer connection settings are incorrect.</span></span>  
  
-   <span data-ttu-id="4cfd5-136">Se ha instalado software de servidor de seguridad o proxy incompatible, configurado de forma incorrecta o con funcionamiento incorrecto.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-136">Incorrectly configured, non-functioning, or incompatible firewall or proxy software has been installed.</span></span>  
  
-   <span data-ttu-id="4cfd5-137">Hay una entrada incorrecta en un archivo de hosts.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-137">There is an incorrect entry in a Hosts file.</span></span>  
  
-   <span data-ttu-id="4cfd5-138">Su adaptador de red no está funcionando correctamente o tiene instalados controladores de adaptador de red incompatibles.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-138">Your network adapter is not functioning correctly or you have incompatible network adapter drivers installed.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="4cfd5-139">Solución</span><span class="sxs-lookup"><span data-stu-id="4cfd5-139">Resolution</span></span>  
 <span data-ttu-id="4cfd5-140">Siga los pasos descritos en la sección resolución de artículo de Microsoft Knowledge Base 326155, "mensaje de Error al intentar obtener acceso a un sitio Web en Internet Explorer:"No se puede mostrar la página"" disponible en [ http://support.microsoft.com/kb/326155 ](http://support.microsoft.com/kb/326155).</span><span class="sxs-lookup"><span data-stu-id="4cfd5-140">Follow the steps in the RESOLUTION section of Microsoft Knowledge Base article 326155, "Error message when you try to access a Web site in Internet Explorer: "Page Cannot Be Displayed"" available at [http://support.microsoft.com/kb/326155](http://support.microsoft.com/kb/326155).</span></span>  
  
#### <a name="401---access-denied-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="4cfd5-141">Al obtener acceso a una página Web en un servidor IIS, se produce el error “401 – Acceso denegado”</span><span class="sxs-lookup"><span data-stu-id="4cfd5-141">"401 - Access denied" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="4cfd5-142">Problema</span><span class="sxs-lookup"><span data-stu-id="4cfd5-142">Problem</span></span>  
 <span data-ttu-id="4cfd5-143">Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-143">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="4cfd5-144">401 – Acceso denegado</span><span class="sxs-lookup"><span data-stu-id="4cfd5-144">401 - Access denied</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="4cfd5-145">Causa</span><span class="sxs-lookup"><span data-stu-id="4cfd5-145">Cause</span></span>  
 <span data-ttu-id="4cfd5-146">IIS define varios errores 401 diferentes que indican una causa más específica del error.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-146">IIS defines several different 401 errors that indicate a more specific cause of the error.</span></span> <span data-ttu-id="4cfd5-147">Estos códigos de error específicos se muestran en el explorador:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-147">These specific error codes are displayed in the browser:</span></span>  
  
- <span data-ttu-id="4cfd5-148">401.1 – Error en el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-148">401.1 - Logon failed.</span></span>  
  
- <span data-ttu-id="4cfd5-149">401.2 – Error en el inicio de sesión debido a la configuración del servidor.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-149">401.2 - Logon failed due to server configuration.</span></span>  
  
- <span data-ttu-id="4cfd5-150">401.3 – No autorizado debido a ACL en el recurso.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-150">401.3 - Unauthorized due to ACL on resource.</span></span>  
  
- <span data-ttu-id="4cfd5-151">401.4 – No autorizado: error de autorización debido a un filtro instalado en el servidor web.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-151">401.4 - Authorization failed by filter.</span></span>  
  
- <span data-ttu-id="4cfd5-152">401.5 – Error de autorización debido a una aplicación ISAP o CGI.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-152">401.5 - Authorization failed by ISAPI/CGI application.</span></span>  
  
- <span data-ttu-id="4cfd5-153">401.7 – Acceso denegado por directiva de autorización de URL en el servidor web.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-153">401.7 – Access denied by URL authorization policy on the Web server.</span></span> <span data-ttu-id="4cfd5-154">Este código de error es específico de IIS 6.0.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-154">This error code is specific to IIS 6.0.</span></span>  
  
  <span data-ttu-id="4cfd5-155">Para obtener una lista completa de los códigos de estado de IIS 7.0, vea el artículo 943891, de Microsoft Knowledge Base "Los códigos de estado HTTP en IIS 7.0" disponible en [ http://support.microsoft.com/kb/943891 ](http://support.microsoft.com/kb/943891).</span><span class="sxs-lookup"><span data-stu-id="4cfd5-155">For a complete list of the IIS 7.0 status codes, see Microsoft Knowledge Base article 943891, "The HTTP status codes in IIS 7.0" available at [http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891).</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="4cfd5-156">Solución</span><span class="sxs-lookup"><span data-stu-id="4cfd5-156">Resolution</span></span>  
 <span data-ttu-id="4cfd5-157">Siga los pasos de [directrices para resolver problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md) para resolver los problemas de permisos de IIS.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-157">Follow the steps in [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to resolve IIS permissions problems.</span></span>  
  
#### <a name="500---internal-server-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="4cfd5-158">Al obtener acceso a una página web en un servidor IIS, se produce el error “ 500 – Error interno del servidor”</span><span class="sxs-lookup"><span data-stu-id="4cfd5-158">"500 - Internal server error" occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="4cfd5-159">Problema</span><span class="sxs-lookup"><span data-stu-id="4cfd5-159">Problem</span></span>  
 <span data-ttu-id="4cfd5-160">Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-160">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="4cfd5-161">500 – Error interno del servidor</span><span class="sxs-lookup"><span data-stu-id="4cfd5-161">500 - Internal server error</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="4cfd5-162">Causa</span><span class="sxs-lookup"><span data-stu-id="4cfd5-162">Cause</span></span>  
 <span data-ttu-id="4cfd5-163">Este mensaje de error lo pueden provocar una amplia gama de problemas del servidor.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-163">This error message can be caused by a wide variety of server-side problems.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="4cfd5-164">Solución</span><span class="sxs-lookup"><span data-stu-id="4cfd5-164">Resolution</span></span>  
 <span data-ttu-id="4cfd5-165">Para solucionar el problema, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-165">To resolve the issue, do the following:</span></span>  
  
- <span data-ttu-id="4cfd5-166">Revise el registro de la aplicación del servidor IIS para obtener información acerca de la causa del error.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-166">Review the Application log of the IIS server for information about why this error occurs.</span></span>  
  
- <span data-ttu-id="4cfd5-167">Revise los archivos de registro de IIS o de HTTPERR para obtener información que pueda ser útil a la hora de determinar la causa del error.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-167">Review the IIS log files or HTTPERR log files for information that may be helpful for determining the cause of the error.</span></span> <span data-ttu-id="4cfd5-168">De forma predeterminada, los archivos de registro de IIS se encuentran en el siguiente directorio de un equipo con el sistema operativo [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-168">By default the IIS log files on a computer running [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] operating systems are located in the following directory:</span></span>  
  
   <span data-ttu-id="4cfd5-169"><em>% WinDir %\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="4cfd5-169"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="4cfd5-170">*% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-170">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="4cfd5-171">De forma predeterminada, en un equipo con Windows Server 2008 o Windows Vista, los archivos de registro de IIS se encuentran en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-171">By default the IIS log files on a computer running Windows Server 2008 or Windows Vista are located in the following directory:</span></span>  
  
   <span data-ttu-id="4cfd5-172">C:\inetpub\logs\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="4cfd5-172">C:\inetpub\logs\LogFiles\W3SVC1\\</span></span>  
  
   <span data-ttu-id="4cfd5-173">De forma predeterminada, en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de HTTPERR se encuentran en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-173">By default the HTTPERR log files on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] are located in the following directory:</span></span>  
  
   <span data-ttu-id="4cfd5-174"><em>% WinDir %</em>system32LogFilesHTTPERR</span><span class="sxs-lookup"><span data-stu-id="4cfd5-174"><em>%WinDir%</em>system32LogFilesHTTPERR</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="4cfd5-175">El archivo de registro de HTTPERR solo se encuentra disponible en un equipo con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-175">The HTTPERR log file is only available on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or Windows Vista computer.</span></span>  
  
#### <a name="service-unavailable-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="4cfd5-176">Al obtener acceso a una página web en un servidor IIS, se produce el error “Servicio no disponible”</span><span class="sxs-lookup"><span data-stu-id="4cfd5-176">"Service Unavailable" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="4cfd5-177">Problema</span><span class="sxs-lookup"><span data-stu-id="4cfd5-177">Problem</span></span>  
 <span data-ttu-id="4cfd5-178">Al intentar obtener acceso a una página web en un servidor IIS, se muestra un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cfd5-178">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="4cfd5-179">Servicio no disponible</span><span class="sxs-lookup"><span data-stu-id="4cfd5-179">Service Unavailable</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="4cfd5-180">Causa</span><span class="sxs-lookup"><span data-stu-id="4cfd5-180">Cause</span></span>  
 <span data-ttu-id="4cfd5-181">La causa más común de este error es que el grupo de aplicaciones (IIS 6.0 e IIS 7.0) para la página web se ha detenido.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-181">The most common cause for this error is that the application pool (IIS 6.0 and IIS 7.0) for the Web page is stopped.</span></span> <span data-ttu-id="4cfd5-182">Esto suele ocurrir si el grupo de aplicaciones o la aplicación COM+ están configurados con una identidad para la que el nombre de usuario y la contraseña especificados no son válidos.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-182">This commonly occurs if the application pool or COM+ application is configured with an Identity for which the specified user name and or password is invalid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="4cfd5-183">Solución</span><span class="sxs-lookup"><span data-stu-id="4cfd5-183">Resolution</span></span>  
 <span data-ttu-id="4cfd5-184">Siga los pasos descritos en la sección "Identidad de proceso de Host de configuración IIS aplicación" del tema [directrices para resolver problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md) para establecer la identidad del proceso de host correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4cfd5-184">Follow the steps in the "Setting IIS Application Host Process Identity" section of the topic [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to set the appropriate host process identity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfd5-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cfd5-185">See Also</span></span>  
 [<span data-ttu-id="4cfd5-186">Directrices para solucionar problemas de permisos de IIS</span><span class="sxs-lookup"><span data-stu-id="4cfd5-186">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)