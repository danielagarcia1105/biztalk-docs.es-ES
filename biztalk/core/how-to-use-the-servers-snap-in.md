---
title: "Cómo usar el complemento de servidores | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f520692-9606-41f5-98ed-5a4962bd1f09
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12eb72323a6dcd1132f03febc9b4d9bd75316c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-servers-snap-in"></a><span data-ttu-id="0b61b-102">Cómo usar el complemento de servidores</span><span class="sxs-lookup"><span data-stu-id="0b61b-102">How to Use the Servers Snap-in</span></span>
<span data-ttu-id="0b61b-103">Esta versión de Inicio de sesión único empresarial (SSO) incluye el complemento de servidores ENTSSO, que permite ver, supervisar y realizar determinadas acciones en el servidor ENTSSO mediante la interfaz de Windows.</span><span class="sxs-lookup"><span data-stu-id="0b61b-103">This version of Enterprise Single Sign-On (SSO) includes the ENTSSO Servers Snap-In, which allows you to view, monitor, and perform certain actions on your ENTSSO Server through the Windows interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b61b-104">Si el sistema tiene un servidor de seguridad y el nombre del servidor utiliza el formato FQDN, es posible que no pueda ponerse en contacto con el servidor.</span><span class="sxs-lookup"><span data-stu-id="0b61b-104">If your system has a firewall and your server name uses the FQDN format, you may not be able to contact the server.</span></span> <span data-ttu-id="0b61b-105">En su lugar, debe especificar el nombre NetBIOS o la dirección IP asociada.</span><span class="sxs-lookup"><span data-stu-id="0b61b-105">Instead, you must specify the NetBIOS name or the associated IP address.</span></span>  
  
### <a name="to-use-the-entsso-servers-snap-in"></a><span data-ttu-id="0b61b-106">Para usar el complemento de servidores ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0b61b-106">To use the ENTSSO Servers Snap-In</span></span>  
  
1.  <span data-ttu-id="0b61b-107">Abra el Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="0b61b-107">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="0b61b-108">En el panel de ámbito, haga clic en el **servidores** nodo.</span><span class="sxs-lookup"><span data-stu-id="0b61b-108">In the Scope pane, click the **Servers** node.</span></span>  
  
     <span data-ttu-id="0b61b-109">Aparecerá la siguiente información en el panel Resultados.</span><span class="sxs-lookup"><span data-stu-id="0b61b-109">The following information is displayed in the Results pane.</span></span>  
  
    -   <span data-ttu-id="0b61b-110">**Nombre**: nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="0b61b-110">**Name**: Name specified.</span></span>  
  
    -   <span data-ttu-id="0b61b-111">**Estado**: estado del servicio ENTSSO (en línea, sin conexión, pendiente, iniciado, detenido, Inicio pendiente y detención pendiente).</span><span class="sxs-lookup"><span data-stu-id="0b61b-111">**Status**: Status of the ENTSSO service (Online, Offline, Pending, Started, Stopped, Start Pending, Stop Pending).</span></span>  
  
    -   <span data-ttu-id="0b61b-112">**Fecha**: se obtuvo la información de fecha.</span><span class="sxs-lookup"><span data-stu-id="0b61b-112">**Date**: Date when information was obtained.</span></span>  
  
    -   <span data-ttu-id="0b61b-113">**Tiempo**: se obtuvo la información de tiempo.</span><span class="sxs-lookup"><span data-stu-id="0b61b-113">**Time**: Time when information was obtained.</span></span>  
  
    -   <span data-ttu-id="0b61b-114">**Servidor de SSO**: nombre completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="0b61b-114">**SSO Server**: Fully qualified name of server.</span></span>  
  
    -   <span data-ttu-id="0b61b-115">**Cuenta de servicio**: cuenta de servicio ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="0b61b-115">**Service Account**: ENTSSO service account.</span></span>  
  
    -   <span data-ttu-id="0b61b-116">**Base de datos de SSO**: base de datos de ENTSSO con la que se comunica este servidor.</span><span class="sxs-lookup"><span data-stu-id="0b61b-116">**SSO Database**: ENTSSO Database with which this server is communicating.</span></span>  
  
    -   <span data-ttu-id="0b61b-117">**Servidor secreto**: indica si se está ejecutando el módulo servidor secreto.</span><span class="sxs-lookup"><span data-stu-id="0b61b-117">**Secret Server**: Indicates whether the Secret Server module is running.</span></span>  
  
    -   <span data-ttu-id="0b61b-118">**Sincronización de contraseñas**: indica si la sincronización de contraseñas está instalada.</span><span class="sxs-lookup"><span data-stu-id="0b61b-118">**Password Sync**: Indicates whether Password Sync is installed.</span></span>  
  
    -   <span data-ttu-id="0b61b-119">**Equipo**: nombre NETBIOS del equipo.</span><span class="sxs-lookup"><span data-stu-id="0b61b-119">**Computer**: NETBIOS name of computer.</span></span>  
  
    -   <span data-ttu-id="0b61b-120">**Recuentos de sucesos**: recuento de eventos de información/advertencia/errores.</span><span class="sxs-lookup"><span data-stu-id="0b61b-120">**Event counts**: Info/Warning/Errors event count.</span></span> <span data-ttu-id="0b61b-121">Restablecerlo iniciará el contador desde 0.</span><span class="sxs-lookup"><span data-stu-id="0b61b-121">Resetting this will start the counter from 0.</span></span>  
  
    -   <span data-ttu-id="0b61b-122">**Versión de SSO instalada**: número de versión de ENTSSO.exe.</span><span class="sxs-lookup"><span data-stu-id="0b61b-122">**Version of SSO installed**: Version number of ENTSSO.exe.</span></span> <span data-ttu-id="0b61b-123">Además, indica si se trata de una versión de 32 bits (x86) o de 64 bits (x64).</span><span class="sxs-lookup"><span data-stu-id="0b61b-123">Also indicates whether this is 32-bit (x86) or 64-bit (x64).</span></span>  
  
### <a name="to-start-or-stop-the-server-service"></a><span data-ttu-id="0b61b-124">Para iniciar o detener el servicio de servidor</span><span class="sxs-lookup"><span data-stu-id="0b61b-124">To start or stop the server service</span></span>  
  
-   <span data-ttu-id="0b61b-125">En lo servidores de complemento de ENTSSO, haga clic en el servidor y haga clic en **iniciar** o **detener**.</span><span class="sxs-lookup"><span data-stu-id="0b61b-125">In the ENTSSO Servers Snap-In, right-click the server and click **Start** or **Stop**.</span></span>  
  
### <a name="to-display-information-for-one-server"></a><span data-ttu-id="0b61b-126">Para mostrar la información de un servidor</span><span class="sxs-lookup"><span data-stu-id="0b61b-126">To display information for one server</span></span>  
  
-   <span data-ttu-id="0b61b-127">En el árbol del servidor, haga clic en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0b61b-127">In the Server tree, click the server.</span></span>  
  
     <span data-ttu-id="0b61b-128">Aparecerá la información en el panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="0b61b-128">The information is displayed in the results pane.</span></span>  
  
### <a name="to-add-a-server"></a><span data-ttu-id="0b61b-129">Procedimiento para agregar un servidor</span><span class="sxs-lookup"><span data-stu-id="0b61b-129">To add a server</span></span>  
  
-   <span data-ttu-id="0b61b-130">Haga clic en el panel de ámbito y, a continuación, haga clic en **Agregar servidor**.</span><span class="sxs-lookup"><span data-stu-id="0b61b-130">Right-click in the Scope pane, and then click **Add Server**.</span></span>  
  
     <span data-ttu-id="0b61b-131">El **Agregar servidor** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0b61b-131">The **Add Server** dialog box appears.</span></span> <span data-ttu-id="0b61b-132">Escriba el nombre del servidor que desea agregar o desplácese hasta su ubicación.</span><span class="sxs-lookup"><span data-stu-id="0b61b-132">Type or browse to the server you want to add.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b61b-133">En determinados entornos de grupo de trabajo, haga clic en el **examinar** botón hará que cierre este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0b61b-133">In certain Workgroup environments, clicking the **Browse** button will cause this dialog box to close.</span></span> <span data-ttu-id="0b61b-134">En lugar de utilizar el **examinar** , simplemente escriba el nombre del servidor en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="0b61b-134">Instead of using the **Browse** button, simply type the server name in the box.</span></span>  
  
### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="0b61b-135">Para ver o cambiar las propiedades del servidor</span><span class="sxs-lookup"><span data-stu-id="0b61b-135">To view or change server properties</span></span>  
  
-   <span data-ttu-id="0b61b-136">En el árbol de servidores, haga clic en el servidor y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0b61b-136">In the Server tree, right-click the server, and click **Properties**.</span></span>  
  
     <span data-ttu-id="0b61b-137">El **propiedades del servidor** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0b61b-137">The **Server Properties** dialog box appears.</span></span> <span data-ttu-id="0b61b-138">Puede ver o cambiar la información en las siguientes fichas:</span><span class="sxs-lookup"><span data-stu-id="0b61b-138">You can view or change information in the following tabs:</span></span>  
  
    -   <span data-ttu-id="0b61b-139">**Niveles de auditoría**</span><span class="sxs-lookup"><span data-stu-id="0b61b-139">**Audit Levels**</span></span>  
  
    -   <span data-ttu-id="0b61b-140">**Base de datos SSO**</span><span class="sxs-lookup"><span data-stu-id="0b61b-140">**SSO Database**</span></span>  
  
    -   <span data-ttu-id="0b61b-141">**Servicio SSO**</span><span class="sxs-lookup"><span data-stu-id="0b61b-141">**SSO Service**</span></span>  
  
    -   <span data-ttu-id="0b61b-142">**Sincronización de contraseñas**</span><span class="sxs-lookup"><span data-stu-id="0b61b-142">**Password Sync**</span></span>  
  
    -   <span data-ttu-id="0b61b-143">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="0b61b-143">**Advanced**</span></span>